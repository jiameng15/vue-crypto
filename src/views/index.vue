<template>
  <div class="wrapper">
    <!--加密-->
    <div class="example-box">
      <div class="title">加密示例</div>
      <p class="msg">
        明文：

        <input type="text" v-model="msg" />
      </p>

      <button class="encrypt-btn" @click="encrypt">加密</button>
      <p class="msg">密文：{{ encryptMsg }}</p>
    </div>
    <!--解密-->
    <div class="example-box">
      <div class="title">解密示例</div>
      <p class="msg">密文： <input type="text" v-model="userInfo" /></p>
      <button class="encrypt-btn" @click="decrypt">解密</button>
      <p class="msg">明文： {{ decryptMsg }}</p>
      <button class="encrypt-btn" @click="md5">MD5加密</button>
      <p class="msg">MD5： {{ md5Msg }}</p>
    </div>
  </div>
</template>

<script>
import secret from "../utils/secret";
// import secret from "yunmeng-crypto";
// import userInfo from "../utils/mock";
export default {
  data() {
    return {
      msg: "123456",
      encryptMsg: "",
      userInfo: "",
      decryptMsg: "",
      md5Msg:""
    };
  },
  methods: {
    md5(){
      this.md5Msg = secret.MD5(this.msg)
    },
    encrypt() {
      // this.userInfo = this.encryptMsg = secret.Encrypt(this.msg);
      this.userInfo = this.encryptMsg = secret.MD5(this.msg)
    },
    decrypt() {
      this.decryptMsg = secret.Decrypt(this.userInfo);
    },
  },
};
</script>

<style scoped>
.msg {
  color: #333;
  text-align: center;
  font-size: 24px;
  min-width: 40px;
  line-height: 40px;
}
.encrypt-btn {
  display: block;
  margin: 15px auto;
  font-size: 14px;
  padding: 10px 15px;
  text-align: center;
  border: none;
  outline: none;
  color: #fff;
  cursor: pointer;
  background-color: #409eff;
  -webkit-appearance: none;
  border-radius: 4px;
  -webkit-user-select: none;
  min-width: 100px;
}
.example-box {
  margin: 100px auto 0;
}
.example-box .title {
  font-size: 24px;
  color: #333;
  text-align: center;
  font-weight: bold;
}
</style>
