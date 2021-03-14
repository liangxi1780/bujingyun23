
 
     

 
     
     

 

##  :house: 官网
  
  官网： https://godspen.ymm56.com/

  使用手册： https://godspen.ymm56.com/doc/cookbook/introduce.html

  在线体验： https://godspen.ymm56.com/admin/#/home
  
  私有部署： https://godspen.ymm56.com/doc/cookbook/install.html


![](https://ymm-maliang.oss-cn-hangzhou.aliyuncs.com/ymm-maliang/access/ymm_1539588655850.png)


  :point_right: `喜欢别忘了加star支持我们，你的支持是我们坚持的动力` :point_left: 


## 码良是什么

码良是一个在`线生成h5页面并提供页面管理和页面编辑的平台`，用于快速制作H5页面。用户无需掌握复杂的编程技术，通过简单拖拽、少量配置即可制作精美的页面，可用于营销场景下的页面制作。同时，也为开发者提供了`完备的编程接入能力`，通过脚本和组件的形式获得强大的组件行为和交互控制能力。

## 码良为谁而作

如上所述，码良不仅可服务于运营人员用来制作轻业务的营销页面，基于完备的编程接入能力，甚至可以作为开发者进行快速业务迭代的工具。 `码良的初心是创建一个开源免费的平台，希望有才的人在平台上贡献自己的组件，脚本，设计模板页面，如果需要后续可以提供组件或脚本开发者设置免费或则收费使用` 当然完全也支持公司内部搭建使用。  

## 码良现状

码良发布于2018年3月初，截止2019年10月目前已经支撑运满满 2500多个活动页面。期间也得到了很多反馈、建议，以及bug报告，基于此，我们持续迭代，致力于提升操作效率，打磨用户体验。道阻且长，仍需努力。 目前开源了编辑器相关的代码。预计在12月份开源后台相关代码,欢迎大家实时关注我们的消息。

## 组件接入简单

提供方便的脚手架创建组件，你可以把一个小功能，一个页面，一个项目做成一个组件，暴露参数给其他同学在编辑器里面填写 [组件开发文档](http://u.720life.cn/g/28cf37965b6b5eb13a1b1bf64e0d47b0342eb021c094e69bab10ac4bd33ecb56bcb50b1f1f07e3dc591c9536755e0dea4d2e0cfb3e8cd40c74604c85776f1a75)

*图为组件开发套件使用动图*

![](https://cos.56qq.com/fis/201910111753054572216e3ca0d8c8ec.gif)

## 脚本扩展组件功能
每个特定功能的组件可以通过组合各种功能（点击跳转，打点等等任何逻辑）脚本来达到对组件功能的扩展。完成特定的功能，并友好的提供参数给到组件的使用者在编辑器上填写。*目前每个脚本都是一个 vue对象，这对熟悉vue的开发者非常友好 深入了解请前往 [码良是如何设计高扩展的在线网页制作平台的](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460a3f8ea458fa1d677969241d4bf901aa3222a3c0dabec9bb6f107605f6d6a21450ad077a8fc9bf1ce9273b89ea31b6910429d35c4a3eaf0f974943ea5780ec9e4d2039b174509de198dfa8532b65ad5f2915045bdd8f449f0169cbb0b065d4315e0acc13e3fbadaec10eb34738e359cc7db25c8b20cbdb0107d83e3c549519f7)*
![](https://ymm-maliang.oss-cn-hangzhou.aliyuncs.com/ymm-maliang/resource/ymm_1570591673129.png)

*图为编辑器工作区界面*
![](https://cos.56qq.com/fis/20191011171531762de15ff82e88a338.png)

## 组件动画展示
运营活动对一些简单的动画提供支持，方便做一些入场和出场的动画，提升活动的交互感，我们使用了 animate.css 提供的一套css动画。下面提供简单的展示
![](https://ymm-maliang.oss-cn-hangzhou.aliyuncs.com/ymm-maliang/access/ymm_1539761082989.gif)

## 合成组件展示
合成组件就是选择已有的节点保存为一个通用的组件，方便下次直接使用

### 使用组合组件
![](https://ymm-maliang.oss-cn-hangzhou.aliyuncs.com/ymm-maliang/access/ymm_1539760696547.gif) 
### 导出组合组件
![](https://ymm-maliang.oss-cn-hangzhou.aliyuncs.com/ymm-maliang/access/ymm_1539760806761.gif)

## 模板页面
页面模板的目的和组合组件类似，都是提供已经做好的内容，运营快速选择使用达到快速上线活动的目的,下面是简单演示
![](https://ymm-maliang.oss-cn-hangzhou.aliyuncs.com/ymm-maliang/access/ymm_1539760521686.gif)


## 安装依赖
这里切记。使用 `yarn install` 安装依赖。不要使用npm直接安装依赖。确保版本统一。
```bash
yarn
```

### 开发

```bash
npm start
```

### 构建

编辑器构建

```bash
npm run editor:build
```

渲染器构建

```bash
npm run client:build
```


### 技术实现

* [开篇: 码良的正确打开方式](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460a3f8ea458fa1d677969241d4bf901aaccdeaa2ba6fcab786f3636fce9df064bf57a5b2054f8ed0b8ff2deefaf22ccca8535c8638c971fdaf9e198441dbfa85bb31249a2ae61e8919f116d66ff7389fd6567424755c790a4562eb6b01f050cc01554e6f11bab0f80ef59a55a1016079eaf07d7103016d12037d48c0efd958a85)
* [码良是如何设计高扩展的在线网页制作平台的](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460a3f8ea458fa1d677969241d4bf901aa3222a3c0dabec9bb6f107605f6d6a21450ad077a8fc9bf1ce9273b89ea31b6910429d35c4a3eaf0f974943ea5780ec9e4d2039b174509de198dfa8532b65ad5f2915045bdd8f449f0169cbb0b065d4315e0acc13e3fbadaec10eb34738e359cc7db25c8b20cbdb0107d83e3c549519f7)


## 支持我们
 开源项目需要的是持续的坚持，而我们坚持的动力当然也来自于你们的支持，希望你  :point_right: `来都来了，加个关注再走吧` :point_left:


## 常见问题

#### 项目依赖一定使用  yarn 安装依赖。不要用 npm 

#### 在windows 系统上安装依赖时，如果缺少c++编译环境会报错

>![](https://cos.56qq.com/fis/201910121010326537220190b4d0131b.png)
>可以尝试全局安装 [windows-build-tools](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c96d476ba1fa35991dd1fa99ef8e2dc61c36435a4344f60b9727c4f9adb392086d2cc59bf9c32fa93b5624b8c90076d56c9)
>windows-build-tools 是一个 npm 包，可以一键安装 c++ 编译所需的 python27、Visual Studio、C++ Build Tool 等。
>Both installations are conflict-free, meaning that they do not mess with existing installations of Visual Studio, C++ Build Tools, or Python

####  如果碰到安装 sass模块失败，当独安装一下 

#### 后端代码和管理系统开源计划  2019年12月份之前

## License

[MIT](http://u.720life.cn/g/ba059582536a397f7c573b87c8bea647045b0ef049248233b6f76e909e70200fe7048b25e29c8bab79aeff32ea74556a)


## 交流群

|钉钉 | 微信  |
| ------------- | ----------- |
|   优先加钉钉群 |  如果上面微信二维码过期。[点击我查看最新二维码](http://u.720life.cn/g/28cf37965b6b5eb13a1b1bf64e0d47b06b47a618511a28bb62d1aa74dd37906e757ad9d9e62ab81ba978e0306bcb63b9ac831d8df4bd109cbecab18d4659012084e5450814ff794c85b93e24f250240c) 添加的时候备注上 `码良`我再邀请你进入群聊 |





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec4b4dcd7567b7d5295fe3f87db8a259d17d4b8a6fb265875b4cd2f160d071e76426f73b9075c1688fa1a9d36a35a9bcc)