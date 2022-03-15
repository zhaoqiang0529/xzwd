<template>
  <div>
    <!-- 登录顶部 -->
    <mt-header title="注册" style="font-size: 16px; border-radius: 2px">
      <router-link to="/login" slot="left">
        <mt-button icon="back">返回</mt-button>
      </router-link>
    </mt-header>
    <!-- 登录内容 -->
    <mt-field
      class="registername"
      label="用户名"
      placeholder="请输入用户名"
      v-model="username"
      :state="usernameState"
    ></mt-field>
    <mt-field
      class="registerpassword"
      label="密码"
      placeholder="请输入密码"
      type="password"
      v-model="password"
      :state="passwordState"
    ></mt-field>
    <mt-field
      class="registerrepassword"
      label="确认密码"
      placeholder="请确认密码"
      type="password"
      v-model="repassword"
      :state="repasswordState"
    ></mt-field>
    <mt-field
      class="registeremail"
      label="邮箱"
      placeholder="请输入邮箱"
      type="text"
      v-model="email"
      :state="emailState"
    ></mt-field>
    <mt-field
      class="registerphone"
      label="手机"
      placeholder="请输入手机号码"
      type="tel"
      v-model="phone"
      :state="phoneState"
    ></mt-field>
    <mt-button
      class="registerbutton"
      type="primary"
      size="large"
      @click="checkFrom"
      >注册</mt-button
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      usernameState: "",
      password: "",
      passwordState: "",
      repassword: "",
      repasswordState: "",
      email: "",
      emailState: "",
      phone: "",
      phoneState: "",

    };
  },
  methods: {
    checkFrom() {
      if (
        this.checkName() &&
        this.checkPassword() &&
        this.checkrePassword() &&
        this.checkEmail() &&
        this.checkPhone()
      ) {
        setTimeout(() => {
          console.log("表单通过验证，前往首页");
          alert("注册成功,即将跳转到登录页面");
          this.$router.push("/");
        }, 1000);
      }else{
          alert('注册失败，请重新注册')
      }
    },
    checkName() {
      let reg = /^[a-zA-Z]\w{3,15}$/;
      if (reg.test(this.username)) {
        this.usernameState = "success";
        return true;
      } else {
        this.usernameState = "error";
        return false;
      }
    },
    checkPassword() {
      let reg = /^\d{6}$/;
      if (reg.test(this.password)) {
        this.passwordState = "success";
        return true;
      } else {
        this.passwordState = "error";
        return false;
      }
    },
    checkrePassword() {
      let reg = /^\d{6}$/;
      if (reg.test(this.repassword) && this.repassword == this.password) {
        this.repasswordState = "success";
        return true;
      } else {
        this.repasswordState = "error";
        return false;
      }
    },
    checkEmail() {
      let reg =
        /^[a-z]([a-z0-9]*[-_]?[a-z0-9]+)*@([a-z0-9]*[-_]?[a-z0-9]+)+[\.][a-z]{2,3}([\.][a-z]{2})?$/i;
      if (reg.test(this.email)) {
        this.emailState = "success";
        return true;
      } else {
        this.emailState = "error";
        return false;
      }
    },
    checkPhone() {
      let reg = /^[1]([3-9])[0-9]{9}$/;
      if (reg.test(this.phone)) {
        this.phoneState = "success";
        return true;
      } else {
        this.phoneState = "error";
        return false;
      }
    },
  },
};
</script>

<style scoped>
.registername {
  width: 80vw;
  margin: 10vw auto 0;
  border-bottom: 1px solid black;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
.registerpassword {
  width: 80vw;
  margin: 5px auto 0;
  border-bottom: 1px solid black;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
.registerrepassword {
  width: 80vw;
  margin: 5px auto 0;
  border-bottom: 1px solid black;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
.registeremail {
  width: 80vw;
  margin: 5px auto 0;
  border-bottom: 1px solid black;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
.registerphone {
  width: 80vw;
  margin: 5px auto 0;
  border-bottom: 1px solid black;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
.registerbutton {
  margin-top: 20px;
  width: 80vw;
  margin: 20px auto 0;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
</style>
