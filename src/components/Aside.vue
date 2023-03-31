<template>
<div>
            <!-- vh是整个浏览器的高度  50px是头部高度 calc(减号前后要有空格)-->
      <el-menu
          style="width: 200px;height:calc(100vh - 50px)"
          default-active="2"
          class="el-menu-vertical-demo"
          @open="handleOpen"
          @close="handleClose">
        <el-submenu index="1">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>导航一</span>
          </template>

          <el-submenu index="1-4">
            <template slot="title">选项1</template>
            <el-menu-item index="1-4-1">选项1-1</el-menu-item>
          </el-submenu>

        </el-submenu>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">导航二</span>
        </el-menu-item>

        <el-menu-item index="4">
          <i class="el-icon-setting"></i>
          <span slot="title">导航四</span>
        </el-menu-item>
      </el-menu>


</div>
</template>

<script>
export default {
  name: "Aside",
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
}
</script>

<style scoped>

</style>
