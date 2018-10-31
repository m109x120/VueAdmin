<template>
<div class="login-wrap">
  <el-form
  class="login-form"
  label-width="80px"
  >
    <h1>用户登录</h1>
    <el-form-item
    label="用户名"
    v-model='formdata.username'
    placeholder="请输入用户名"
    >
      <el-input></el-input>
    </el-form-item>
    <el-form-item
    label="密码"
    v-model='formdata.password'
    placeholder="请输入密码"
    >
      <el-input></el-input>
    </el-form-item>
    <el-button
    type="primary"
    @click='login'
    class="login-button"
    >登录</el-button>
  </el-form>
</div>
</template>

<script>
export default {
  data () {
    return {
      formdata: {
        username: '',
        password: ''
      }
    }
  },
  methods: {
    login () {
      console.log('你点击了登录')
    }
  }
}
</script>

<style>
.login-wrap{
  background-color: #324152;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.login-wrap .login-form{
  background-color: #fff;
  width: 400px;
  padding: 30px;
  border-radius: 5px;
}
.login-wrap .login-form .login-button{
  width: 100%;
}
</style>
