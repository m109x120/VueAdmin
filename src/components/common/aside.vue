<template>
  <aside class="el-aside" style="width: 200px;">
    <el-menu
      :router="true"
      :unique-opened="true"
      default-active="/user"
      style="height: 100%;"
      @open="handleOpen"
      @close="handleClose"
      class="asideBar"
      >
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-star-on"></i>
          <span>用户管理</span>
        </template>
        <el-menu-item index="/user">用户列表</el-menu-item>
      </el-submenu>
      <el-submenu index="2">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span>权限管理</span>
        </template>
        <el-menu-item index="/role">角色管理</el-menu-item>
        <el-menu-item index="/rights">权限列表</el-menu-item>
      </el-submenu>
      <el-submenu index="3">
        <template slot="title">
          <i class="el-icon-question"></i>
          <span>商品管理</span>
        </template>
        <el-menu-item index="/goodList">商品列表</el-menu-item>
        <el-menu-item index="/category">分类参数</el-menu-item>
        <el-menu-item index="/goodCategory">商品分类</el-menu-item>
      </el-submenu>
      <el-submenu index="4">
        <template slot="title">
          <i class="el-icon-setting"></i>
          <span>订单管理</span>
        </template>
        <el-menu-item index="/orderList">订单列表</el-menu-item>
      </el-submenu>
      <el-submenu index="5">
        <template slot="title">
          <i class="el-icon-info"></i>
          <span>数据统计</span>
        </template>
        <el-menu-item index="/dashbord">数据报表</el-menu-item>
      </el-submenu>
    </el-menu>
  </aside>
</template>
<script>
export default {
  data () {
    return {
      isUniqueOpend: true,
      defaultOpend: 1
    }
  },
  methods: {
    handleOpen (key, keyPath) {
      console.log(key, keyPath)
    },
    handleClose (key, keyPath) {
      console.log(key, keyPath)
    }
  }
}
</script>

<style>
.el-aside,
.asideBar{
  height: 100%;
}
</style>
