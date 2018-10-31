<template>
<section class="el-container is-vertical">
  <el-header class="header">
    <el-row>
      <el-col :span="4">
        <div class="grid-content bg-purple">
          logo
        </div>
      </el-col>
      <el-col :span="19" class="middle">
          <h2>电商后台管理系统</h2>
      </el-col>
      <el-col :span="1">
          <a href="#"
          class="loginout"
          @click.prevent="logOut"
          >退出</a>
      </el-col>
    </el-row>
  </el-header>
  <section class="el-container">
    <!-- aside -->
    <Aside></Aside>
    <main class="el-main">Main</main>
  </section>
</section>
</template>

<script>
import Aside from '@/components/common/aside'
export default {
  beforeCreate () {
    const token = sessionStorage.getItem('token')
    if (!token) {
      this.$router.push('/login')
      this.$message.warning('请先登录')
    } else {
      this.$router.push({name: 'home'})
      this.$message.success('进入到home页面')
    }
  },
  components: {
    Aside
  },
  methods: {
    logOut () {
      sessionStorage.clear()
      this.$router.push('/login')
    }
  }
}
</script>

<style>
.el-container{
  width: 100%;
  height: 100%;
}
.header{
  background: #ccc;
}
.header .middle{
    line-height: 60px;
    color: #fff;
    text-align: center;
  }
  .header .loginout{
    line-height: 60px;
    text-decoration: none;
  }
</style>
