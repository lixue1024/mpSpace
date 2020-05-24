<template>
    <div class="loginBox">
        <div class="login">
            <div>
              <van-image
                round
                width="6rem"
                height="6rem"
                src="/static/images/mp01.jpg"
              ></van-image>
            </div>
            <van-field
              label="昵称"
              left-icon="smile"
              clearable
              :value="form.userName"
              @change="changeUserName"
              placeholder="请输入昵称"></van-field>
            <van-field
              label="密码"
              left-icon="lock"
              type="password"
              required
              clearable
              :value="form.passWord"
              @change="changePassWord"
              placeholder="请输入密码"></van-field>
              <!-- 登录按钮 -->
              <div class="loginBtn">
                <van-button size="small" color="#FFAA00" @click="login">登 录</van-button>
              </div>
        </div>
    </div>
</template>

<script>
export default {
    data () {
    return {
        value: '',
        form: {
          userName: '',
          passWord: ''
        }
    }
  },
  methods: {
    changeUserName(event) {
      this.form.userName = event.mp.detail
    },
    changePassWord(event) {
      this.form.passWord = event.mp.detail
    },
    login() {
      const url = "../index/main"
      mpvue.navigateTo({url})
    }
  }
}
</script>

<style lang="wxss">
page {
  height: 100%;
}
</style>

<style scoped>
.loginBox {
    width: 100%;
    height: 100%;
    background-color: #fcd9dd;
}
.login {
    width: 80%;
    height: 500rpx;
    /* border: 1px solid #000; */
    position: relative;
    top: 20%;
    margin: 0 auto;
    text-align: center;
    /* padding: 10px; */
}
.loginBtn {
    margin: 10px 0;
}

</style>
