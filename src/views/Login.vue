<template>
<div class="login-wrap">
  <el-form
  class="login-form"
  label-width="80px"
  >
    <h1>用户登录</h1>
    <el-form-item
    label="用户名"
    >
      <el-input
      v-model='formdata.username'
      placeholder="请输入用户名"
      ></el-input>
    </el-form-item>
    <el-form-item
    label="密码"
    >
      <el-input
      v-model='formdata.password'
      placeholder="请输入密码"
      type="password"
      ></el-input>
    </el-form-item>
    <el-button
    type="primary"
    @click.prevent='handelLogin'
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
    async handelLogin () {
      // 发送ajax请求
      const logInfo = await this.$http.post('/login', this.formdata)
      const {meta} = logInfo.data
      if (meta.status === 200) {
        // 登录成功
        const token = logInfo.data.data
        this.$message.success(meta.msg)
        sessionStorage.setItem('token', token)
        // 可以跳转到home页面了
        this.$router.push('/')
      } else {
        // 各种失败信息
        this.$message.warning(meta.msg)
      }
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
