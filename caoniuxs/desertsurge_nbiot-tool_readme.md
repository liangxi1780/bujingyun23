
# nbiot-tool
WEEX开发 NB 频点转换工具

 

![eros](http://upload.ouliu.net/i/20180124175551qrzlq.png)

 

## 介绍

**eros 不是框架，是基于 [weex](http://u.720life.cn/g/074dc012087a3bfd627043a18bcf1369ad5c8c53ae44af3685f1bf98727370db) 封装、面向前端的 [vue](http://u.720life.cn/g/1eea7f654038e3466b5f7afd82540e02e7da038f816469dc8db0feff6028bc7d) 写法的一整套 APP 开源解决方案。**

> 简单来说，在 weex 提供的强大支持下，用一份 vue 写法的代码，编译成 iOS/Android 两端原生 APP。

## 文档 
> [帮助我们完善和翻译文档](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d39a8bb0dd14b0063607f166ec2b1bb9ff4ccc834d89acfd2ec971e1e91cea6f)
- [中文文档](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89da1b003bc4bafa2f48b4dd960ef5f9e113)
- [English document](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89da9c9a4461440d0627660dd0a50af99040)

## 作品轮播
> 图片较大，耐心等候

 
    
![eros-demos](https://s18.postimg.org/3n8tb3fhl/soogif1.gif)

 

[大图地址](http://u.720life.cn/g/3022e8612e5d34f9d3d1c1f6fa5cbba333a714c9a5bc5ba0824af74ba5318950a293d344e242cd5d179aa1c67ba713c2)

## Demo

 > 开发者可以扫描二维码来下载 eros app 来进行体验，iOS首次打开App需要在 **设置->通用->设备管理 信任开发证书。**
 
| Eros iOS demo | Eros Android demo |
|---------|---------|
|![【ios 下载】](https://bmfe.github.io/eros-docs/zh-cn/image/iosqr.png)|![【android 下载】](http://upload.ouliu.net/i/201801241911376ee1z.png)|
|[【预览录屏】](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89dac5ff3cf3b19417c3faceeacb384bb1c7ed2e75c12d0e67a07db9d93f8ad016f0)|[【预览录屏】]https://bmfe.github.io/eros-docs/zh-cn/image/androidDemo.gif
|[【下载链接】](http://u.720life.cn/g/f73c0c6f5dc4d1e43abb974d680fdd760e8aa6a2f435f2615d4b2aaf889940db)|[【下载链接】]https://fir.im/weexerosandroid

## 选择了 EROS 可以得到什么？
### 原生能力
暴露给前端大量便捷实用的 [原生能力](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89da674126acea2fa6bcf42f5713f44b17650dd3c3df6cd18128172d4a815e2ead8c07b966ac5d43c97af65e8c7bff1f75dd9051954f599eca3efebed97669d14d2aecd839887ac4d9cc048bfe9e0318d92b) 
，拓展了 [非常有用的事件](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89da674126acea2fa6bcf42f5713f44b1765f109b9d771a70d8f6301e72f6dfb127415a32cc7071712f5f3e4720bf4c07aba2fa82005df769b4396c09408d58a7786288ec36cd6ca1cfef72fe4c48d74c3a1) 。

- 路由
- 原生事件
- 本地化存储
- 发布订阅
- Restful 请求，支持 Cookie
- 图片处理
- 拍照上传
- 浏览图片
- 操作本地图片
- 拨打电话
- 发短信
- 选择联系人
- 地图
- 定位
- 个推
- 支付
- 分享
- 原生弹窗
- 拷贝
- 扫一扫
- Echart
- 日历
- Bindingx
- ...

### 开发过程中
 
- 详细的文档
- **iOS/Android 模拟器/真机热刷新**
- 支持 `weex debug`
- 一套 Vue 代码，两端原生应用
- 通过 `appboard JS bundle` 极大的减少了公共代码冗余
- 为大型项目内置了中介者服务，方便管理业务间的事件交互

### 脚手架 [eros-cli](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046791cacbb4efb6bbfc39b2a40202a946f)：
- 随时初始化最新的开发项目模板。
- [简单而且快速的依赖更新。](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89da3f278974da099c77b657cc9f28b72ce8d52774e770e2077682b6ef282861bf16)
- 支持生成内置包，全量包，增量包。
- 支持随时更新模板内容。
- 支持 Weex 两种入口开发方式 `JS/Vue`。
- 内置与增量服务器的交互逻辑。


### 热更新机制

**由于 Weex 的机制，我们能在远端发布代码，客户端更新并生效，并不需要审核发布流程，给 APP 提供了强大的迭代动力。**

- [热更新详解](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89daef7004a583ce945924bb1dc607c8d78d0ea4013db8a1051c0015134178bac413)
- [eros-publish 开源的，简单的热更新后台逻辑](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046654a225e5d17d93a37d63cc49b3791bb4d14ae79c12b2edbcb2e0961cf032454)

### UI 库
使用 UI 库，开发效率也会大大提升：
* [alibaba/weex-ui](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e2da7c305aada67d44600a2d4acf3431d6d0722e2ff5f4280e6a8b059d616f58)
* [bui](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046935ebb5be29855744c97d21f954f68cccd143396f3732388b899b56a217961ce)


## EROS 正在做什么?
EROS 在进行组件化的开发，争取做到插件可配置，让原生开发者专注拓展原生能力，前端开发者专注与业务逻辑，极力打造一个可共享的插件社区。

## 开源现状
在 EROS 开源的半年时间，已帮助近百位开发者开发了属于自己的原生应用，这里先简单列举几个，后续会征求同意来展示：

* StarLife 
* 赢商大数据 
* 易送 
* 蜂觅 
* JEX
* 1234TV
* 博山头条
* 新长宁慧生活
* 辽河油田
* 连云港政协
* 连云港古树
* 亿康通
* ...

涉及行业分布于区块链、资讯、医疗、招商、购物、政府、办公、直播等。

## 支持性
跟随着 weex 的支持性，**但 eros 并不支持开发代码兼容 web 端**
* Android 4.1 (API 16)
* iOS 8.0+
* WebKit 534.30+

## 快速开始
* [EROS 入门指南](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89dacdcb41e6cd9b9ab60e4d780027b30d47dd8ca9fc7ac76ce411d2bb8952f1693f)
* [EROS 网易严选](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d3850c8fbfb89594a0327558c6ddbfe1503c7a3013724bc72a80a13beb8f61ef)
* [EROS 更新日志](http://u.720life.cn/g/68eeb4c3391612ea65a3b6a749701a8a7ea6fceaf10cfaa8136c11eed3df89da0800c84e544e7d3b671aef6d3b8e81dbf5bb55516a3ba6881a6b59c602cef18c)

## 周边系统

> 以下项目，全部开源：

| Project | Description |
|---------|-------------|
| [eros-cli](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046791cacbb4efb6bbfc39b2a40202a946f) | 简单的 eros 项目构建工具，可以提供搭建，开发，调试和发布等功能。 |
| [eros-publish](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046654a225e5d17d93a37d63cc49b3791bb4d14ae79c12b2edbcb2e0961cf032454) | 简单的服务器差分包更新逻辑，需要和脚手架搭配使用。 |
| [eros-widget](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046488dba1df76b2ee93aa7875276009b264fbeee7934f3f0873852559723043be8) | 二次封装 module。 |
| [eros-ios-library](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462282010f51da0557ea95028c9bd1b563092d98051050ee6e1510ee9e96caaa28) | eros ios Weex 项目依赖库。 |
| [eros-ios-sdk](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c29ebc87de24fc62a1bc062dc871ccae21e72d283f9b0512303bcfef18e8dcaa) | eros ios Weex sdk。 |
| [eros-android-framework](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046413735281bc3be62b92d20e97e0eff80b56103bc4505d2c669dff3bd8ee3bca6) | eros weex 移动解决方案安卓端框架。 |
| [eros-android-widget](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c0b21a8373910f11a9bd32a93a433f7) | eros 安卓组件库。 |
| [eros-android-sdk](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461017fdbf7ab07a7deb61bf62ffda548f) | eros 安卓移动解决方案安卓端 WeexSDK。 |

## 社区贡献
* [weex-eros-book 书籍阅读 app](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046982c349ee2992a078ae6678fd7fbfccc8b0b91801f5c6ae40bad8cc1e86dd2f5)
* [lygtq-eros-publish 服务器增量发布逻辑](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304613b8602dd38ca4ea9ae6a93414cd179b2b6fc27140a0da68b2bdcecb356644d7)
* [eros-node-server 服务器增量发布逻辑](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304677128d68defd8f9a840a9ac9696a49173cb1233fe367fbb9ee18f58a8c111069)


# 讨论组
eros 正式开源到现在已经有了一个拥有大量开发者的微信群 (只能通过邀请)，群里有大量开发者已经有 eros 产品在开发中和已上线，为了维护一个良好的环境，还请先熟知以下群规：

* **此并不是流量群，也并非广告群，是为了大家一起成长，保证信息的有效性，如果发黄赌毒，不和谐言语，与学习无关的广告，推广内容，无关小程序，不会商量，直接会被踢，且不会再有入群机会。**
* eros开发中遇到任何问题可以随时发到群里 weex开发相关可以一起讨论。
* 如果不能及时回答也请耐心等待，群里开发丰富经验的同学会帮您一起看问题。
* 除了 eros 自身紧急 BUG 外的问题，均需要提 issue，我们会按 issue 处理，目的是为了更好的给其他开发者参考，紧急问题请直接抛到群里，我们会直接远程帮助您调试。


QQ群:  

 

微信群: 

 


## License
[MIT](http://u.720life.cn/g/22e7b067064505b0b066921a690bc00f1d50276b811118d1c1385e5fc89962b82ba3402c9eeae31a4a3c9e7e77bdc483)

Copyright (c) 2017-present, 本木医疗


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e427688e5e1ce6c0a463db724755b9a50b9aeb4a632426b4e11b4807d7e7be45539b492df40333bb01cbf271778d23ce1)