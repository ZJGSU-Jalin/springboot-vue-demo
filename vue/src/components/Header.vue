<template>
  <div style="height: 50px; line-height: 50px; border-bottom: 1px solid #ccc; display: flex">
    <el-dropdown>
      <span class="el-dropdown-link">用户<i class="el-icon-arrow-down el-icon--right"></i></span>
      <template #dropdown>
        <el-dropdown-menu>
          <el-dropdown-item>个人中心</el-dropdown-item>
          <el-dropdown-item>应用管理</el-dropdown-item>
          <el-dropdown-item>切换账户</el-dropdown-item>
          <el-dropdown-item>登出</el-dropdown-item>
        </el-dropdown-menu>
      </template>
    </el-dropdown>
  </div>
</template>

<script>
export default {
  name: "Header",
  components: {

  }
}
</script>

<style scoped>

</style>