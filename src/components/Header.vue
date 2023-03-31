<template>
<div style="height:50px;line-height: 50px;border-bottom: 1px solid #ccc;display:flex">
 <div style="width:200px;padding-left: 30px;font-weight: bold;color:cornflowerblue">
   后台管理系统
 </div>
  <div style="flex: 1 ">

  </div>

  <div style="width:100px ">
    <el-dropdown>
  <span class="el-dropdown-link">
    张三<i class="el-icon-arrow-down el-icon--right"></i>
  </span>
      <el-dropdown-menu slot="dropdown">
        <el-dropdown-item>个人信息</el-dropdown-item>
        <el-dropdown-item>退出系统</el-dropdown-item>

      </el-dropdown-menu>
    </el-dropdown>
  </div>

</div>
</template>

<script>
export default {
  name: "Header.vue"
}
</script>

<style scoped>
.el-dropdown-link {
  cursor: pointer;
  color: #409EFF;
}
.el-icon-arrow-down {
  font-size: 12px;
}
</style>
