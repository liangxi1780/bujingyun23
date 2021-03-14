# colloc
一款烧脑的益智游戏。同名微信小游戏已上线。

开源出来作为`Pixi.js`游戏开发的入门教程。

### 配置
> 修改成开发者自己的云开发环境和广告位 ID

- 小程序端
```js
// src/core/env.js
// 云开发 环境名
PIXI.settings.CLOUD_ENV = ''
```
- 云函数
```js
// 每个函数是独立的所以需要开发者自行修改
// dist/cloud/verify/index.js
cloud.init({env: ''})
```

- 广告位
```js
// 开发者自己的广告位 ID
// src/modules/ad.js
wx.createRewardedVideoAd({
  adUnitId: ''
})
```

### 开发

```bash
# clone 项目
git clone git@github.com:JetLua/colloc.git

# clone 子项目
git submodule init
git submodule update

# 安装依赖
npm i

# dev 可以替换成 build
# 运行
npm run dev

# 开放域
npm run dev:ctx

# 微信开发者工具选择 dist 目录
```

### 游戏截图

   

   



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e06a2e34d2f290f3435bbf43ad640ca865bcf58625a3eb715ece0b7f0a4854490f8240c299380797d585f7fa3cb345798)