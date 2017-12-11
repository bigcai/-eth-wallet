# -eth-wallet

**先从node官网下载node安装包**

 [传送门： node官网 nodejs.org ](https://nodejs.org/zh-cn/)

**安装完成后用node自带的npm（node package manger）下载两个依赖： 椭圆加密算法包，keccak哈希包**


> npm install secp256k1
> npm install keccak

**进入node交互界面**
>node
>
>

**执行node脚本**
```node
 //引入包
 const secp256k1 = require("secp256k1/elliptic")
 const createKeccakHash =  require("keccak")
 const crypto = require('crypto')
 
 // 生成私钥
 const privateKey = crypto.randomBytes(32)
 // 生成公钥
 const publicKey = secp256k1.publicKeyCreate(privateKey, false).slice(1)
 // 生成地址
 const address = createKeccakHash("keccak256").update(publicKey).digest().slice(-20)
 
 // 查看结果
 privateKey.toString('hex')
 address.toString('hex')
```

**以上代码在 Imtoken钱包 导入成功， 并能够正常使用，即 核对导入后的钱包address与 脚本生成的address一致**

**分享请署名以及链接来源，谢谢**
