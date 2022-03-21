<template lang="">
  <el-container class="home-container">
    <el-header>
      <div>
        <img id="avatarImg" src="../assets/avatar.jpg" alt="" />
        <span>唛闹的主页</span>
      </div>
      <el-button type="info" @click="logout">Logout</el-button>
    </el-header>
    <el-container>
      <el-aside width="200px">Aside</el-aside>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>
<script>
export default {
  name: 'app',
  methods: {
    logout() {
      window.sessionStorage.clear()
      this.$router.push('/login')
    },
  },
}
</script>
<style lang="less" scoped>
.el-header {
  background-color: #373d41;
  display: flex;
  justify-content: space-between;
  padding-left: 0;
  align-items: center;
  color: #eaedf1;
  font-size: 20px;
  > div {
    display: flex;
    align-items: center;
    span{
      margin-left: 20px;
    }
  }
}

.el-aside {
  background-color: #333744;
}

.el-main {
  background-color: #eaedf1;
}

.home-container {
  height: 100%;
}

#avatarImg {
  width: 50px;
  height: 50px;
}
</style>
