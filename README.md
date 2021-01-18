# vue-crypto

> 前端 AES 加解密的实现

## 如何开始

### 第一步

引入依赖:

```
npm install crypto-js
```

### 第二步

在项目中创建 secret.js
本示例文件路径为 /src/utils/secret.js

### 第三步

在需要的页面中使用
引入及使用加密解密方法

```
import secret from "../utils/secret";

methods: {
  encrypt() {
    this.userInfo = this.encryptMsg = secret.Encrypt('需要加密的内容');
  },
  decrypt() {
    this.decryptMsg = secret.Decrypt('需要解密的内容');
  },
}
```

具体参考 /src/view/index.vue

## Build Setup

```bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```
