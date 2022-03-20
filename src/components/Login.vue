<template>
  <div class="login_container">
    <div class="login_box">
      <div class="avatar_box">
        <img src="../assets/logo.png" alt="" />
      </div>
      <el-form
        ref="loginFormRef"
        :rules="loginFormRules"
        :model="loginForm"
        label-width="80px"
        class="login_form"
      >
        <!-- username -->
        <el-form-item label-width="0" prop="username">
          <el-input
            v-model="loginForm.username"
            prefix-icon="iconfont icon-wode"
          ></el-input>
        </el-form-item>
        <!-- passowrd -->
        <el-form-item label-width="0" prop="password">
          <el-input
            v-model="loginForm.password"
            prefix-icon="iconfont icon-huiyuan1"
          ></el-input>
        </el-form-item>
        <!-- button -->
        <el-form-item class="btns" label-width="0">
          <el-button @click="login" type="primary">Login</el-button>
          <el-button @click="resetLoginForm" type="info">Reset</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // login bind data
      loginForm: {
        username: "",
        password: "",
      },
      loginFormRules: {
        username: [
          { required: true, message: "please input uname", trigger: "blur" },
          {
            min: 3,
            max: 10,
            message: "length should between 3 to 10",
            trigger: "blur",
          },
        ],
        password: [
          { required: true, message: "please input password", trigger: "blur" },
          {
            min: 6,
            max: 15,
            message: "length should between 6 to 10",
            trigger: "blur",
          },
        ],
      },
    };
  },
  methods: {
    resetLoginForm() {
      this.$refs.loginFormRef.resetFields();
    },
    login() {
      this.$refs.loginFormRef.validate(async (valid) => {
        if (!valid) {
          return;
        }
        const { data: res } = await this.$http.post("login", this.loginForm);

        if (res.meta.status !== 200)
          return this.$message.error("Error Username/Password");
        return this.$message.success("success login!");
      });
    },
  },
};
</script>

<style lang="less" scoped>
.login_container {
  background-color: #2d4d6d;
  height: 100%;
}
.login_box {
  width: 450px;
  height: 300px;
  background-color: #fff;
  border-radius: 3px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  box-shadow: 0 0 10px;
}

.avatar_box {
  height: 130px;
  width: 130px;
  border: 1px solid #eee;
  border-radius: 50%;
  padding: 10px;
  box-shadow: 0 0 10px;
  position: absolute;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #fff;
  img {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background-color: #eee;
  }
}
.btns {
  display: flex;
  justify-content: flex-end;
}
.login_form {
  position: absolute;
  bottom: 0%;
  width: 100%;
  padding: 0 20px;
  // 规定两个并排的带边框的框
  box-sizing: border-box;
}
</style>
