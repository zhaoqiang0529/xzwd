<template>
  <div>
    <!-- 登录顶部 -->
    <mt-header title="登录" style="font-size: 16px; border-radius: 2px">
      <router-link to="/" slot="left">
        <mt-button icon="back">返回</mt-button>
      </router-link>
      <router-link to="/register" slot="right">
        <mt-button icon="more">注册</mt-button>
      </router-link>
    </mt-header>
    <!-- 登录内容 -->
    <mt-field
      class="loginname"
      label="用户名"
      placeholder="请输入用户名"
      v-model="username"
      :state="usernameState"
    ></mt-field>
    <mt-field
      class="loginpassword"
      label="密码"
      placeholder="请输入密码"
      type="password"
      v-model="password"
      :state="passwordState"
    ></mt-field>
    <mt-button
      class="loginbutton"
      type="primary"
      size="large"
      @click="checkFrom"
      >登录</mt-button
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
    };
  },
  methods: {
    checkFrom() {
      this.checkName();
      this.checkPassword();
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
        let reg = /^\d{6}$/
        if (reg.test(this.password)) {
        this.passwordState = "success";
        return true;
      } else {
        this.passwordState = "error";
        return false;
      }
    }
  },
};
</script>

<style scoped>
.loginname {
  width: 80vw;
  margin: 50vw auto 0;
  border-bottom: 1px solid black;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
.loginpassword {
  width: 80vw;
  margin: 5px auto 0;
  border-bottom: 1px solid black;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
.loginbutton {
  margin-top: 20px;
  width: 80vw;
  margin: 20px auto 0;
  border-radius: 15px;
  box-shadow: 5px 5px 2px #aaa;
}
</style>
