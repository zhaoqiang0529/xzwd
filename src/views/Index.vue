<template>
  <div>
    <!-- 顶部开始 -->
    <mt-header title="首页" fixed class="indexindex">
      <!-- logo开始 -->
      <router-link to="/" slot="left">
        <mt-button>logo</mt-button>
      </router-link>
      <!-- logo结束 -->
      <!-- 登录注册开始 -->
      <mt-button class="indexlogin" slot="right">
        <router-link to="/login">登录</router-link>
      </mt-button>
      <mt-button class="indexregister" slot="right">
        <router-link to="/register">注册</router-link>
      </mt-button>
      <!-- 登录注册结束 -->
    </mt-header>
    <!-- 顶部结束 -->
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.indexindex {
  background-color: rgb(94, 128, 223);
  font-size: 16px;
  border-radius: 0 0 5px 5px;
}
.indexindex a {
  color: white;
}
.indexlogin {
  margin-right: 10px;
}
</style>
