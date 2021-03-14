     

[![Bower version](https://img.shields.io/bower/v/amazeui.svg?style=flat-square)](https://github.com/amazeui/amazeui)
[![NPM version](https://img.shields.io/npm/v/amazeui.svg?style=flat-square)](https://www.npmjs.com/package/amazeui)
[![Build Status](https://img.shields.io/travis/amazeui/amazeui.svg?style=flat-square)](https://travis-ci.org/amazeui/amazeui)
[![Dependency Status](https://img.shields.io/david/amazeui/amazeui.svg?style=flat-square)](https://david-dm.org/amazeui/amazeui)
[![devDependency Status](https://img.shields.io/david/dev/amazeui/amazeui.svg?style=flat-square)](https://david-dm.org/amazeui/amazeui#info=devDependencies)

Amaze UI 是基于社区开源项目构建的一个跨屏前端框架。

### [Docs in English](http://u.720life.cn/g/fcc17508737486a3d8796e0f92b91fe917a4499941f63cc7e3147117463b96aade20bd78dd806ba16c12a4211ad9d05c)

__[README in English](README.en.md)__

### [React 版](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a5e07fa8e61557b0325f4ca74469addad43f5800a8945e6ade6ed81709bbd4d6) | [独立插件](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304682d3b1386aeb7d18821d9cbfc7952fdb) | [Amaze UI Touch](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a5e07fa8e61557b0325f4ca74469adda589ca433cb28ec9692e4d867b91bbc7f)

## 功能简介

### 移动优先

以移动优先（Mobile first）为理念，从小屏逐步扩展到大屏，最终实现所有屏幕适配，适应移动互联潮流。

### 组件丰富，模块化

Amaze UI 含近 20 个 CSS 组件、20 余 JS 组件，更有多个包含不同主题的 Web 组件，可快速构建界面出色、体验优秀的跨屏页面，大幅提升开发效率。

### 本地化支持

相比国外框架，Amaze UI 关注中文排版，根据用户代理调整字体，实现更好的中文排版效果；兼顾国内主流浏览器及 App 内置浏览器兼容支持。

### 轻量级，高性能

Amaze UI 面向 HTML5 开发，使用 CSS3 来做动画交互，平滑、高效，更适合移动设备，让 Web 应用更快速载入。

## 下载及使用

用户可以从 [Amaze UI 官网](http://u.720life.cn/g/f3f95953a76760bd63229c330fb1147c28d3f78630123500a6781b41e5e52abdf84d4437b0a0fbfcbce4d58db549b596) 下载打包好的模板。

所有文档存放在 `docs/` 目录下，为方便查看演示效果，建议通过 [Amaze UI 官网](http://u.720life.cn/g/f3f95953a76760bd63229c330fb1147ca5e20f5f9678c62fad545fb2a462012c)查看文档。


## 开发及构建

用户可以在 Amaze UI 的基础上进行二次开发。

### 目录结构

```
amazeui
|-- HISTORY.md
|-- LICENSE
|-- README.md
|-- package.json
|-- dist        # 构建目录
|-- docs        # 文档
|-- fonts       # Icon font，目前使用了 http://staticfile.org/
|-- gulpfile.js # 构建配置文件
|-- js          # JS 文件
|-- less        # LESS 文件
|-- tools       # 相关工具
|-- vendor
`-- widget      # Web 组件
```

### 构建工具

Amaze UI 使用 [gulp.js](http://u.720life.cn/g/42c4ab571b486d53af2ab7b8bae8086b8181dbde5f085c12e5be0270a023ad42) 构建项目。

首先全局安装 gulp：

```
npm install -g gulp
```

克隆项目文件:

```
git clone https://github.com/allmobilize/amazeui.git
```

然后进入目录安装依赖：

```
npm install
```

接下来，执行 `gulp`：

```
gulp
```

## [Bug 反馈及需求提交](CONTRIBUTING.md)

## 参考、使用的项目

* [Zepto.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469f598c8bd469a9d2cbe68197a3b1c8625cb380c2022ca100ba7f9e39711eaa22) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469f598c8bd469a9d2cbe68197a3b1c8624c069b1f82fd5d20e5da66b47c1b7351e82c004bbdf042a55f8cb02a46f7af34)
* [Sea.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a9c73c2682e968c56c126020d1eda26b) ([MIT License](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304655bdf9e331d2c1721a1f6d54a55a9888c10bea4f136c143a720e481dc30583733935993213c8ec5accbef1f1f8988a61)
* [Handlebars.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f3cbd1fa2ee25be0e67625c252a00e8aa7398c826d8201fb6023fda2971e78fd) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f3cbd1fa2ee25be0e67625c252a00e8ab346680549d74e9d9c0432ac11c25e5690d172d0ac007a287348b087122c5339)
* [normalize.css](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304601374e1ee3acaa6ef369f810edb14b4a8817837b4d1cb0214f8be145727c787d) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304601374e1ee3acaa6ef369f810edb14b4a0df59d9d43ff461c7aa22eb9a28bac8024796ce4a987cf9f4788601d41988071)
* [FontAwesome](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461b497c4d42fd57c4cbd279a2424a9c4782ea6356302c670dae3cb3b82da6a042) ([CC BY 3.0 License](http://u.720life.cn/g/b77ee7bfee69ac84b98b830822d7c3101745d83bd4a1837b72c6c2d6388fe3d09e1f590dd2b85e0b7782f55f625865d5)
* [Bootstrap](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465a8160a390414e5887ea7b27f65f8894df8a88b45f3cfc9c4098552eeb42db05) ([MIT License](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465a8160a390414e5887ea7b27f65f889452510fcf9aba1482d5b9996e0ed53fdf0d095b698dc3c8aa51b5d8cc2d99ff7d)
* [UIkit](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046350f8711fc2fa5bfa4160e1d935c628e) ([MIT License](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304603ad27296b2292a231178ebf25f8750b54c23209b42902af6fd54fbbc79822465ccfb033ab67bf49d0813614e8171872)
* [Foundation](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468d7a8036443292163d68ff8f1292a5706562e49b3490eb111fedd1ae1ef6ebbd) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468d7a8036443292163d68ff8f1292a570516305470a7d809834bd419fe88ae123aaab115c536e6a2b4216c2582967f347)
* [Framework7](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046034f07c34c53884cd706c760ef52d31595a53815eb3338e30f601a3501049ad0) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046034f07c34c53884cd706c760ef52d315afaeaa562c89c8b6e8f515efa2192e435f7a10f9eb60c255cbb584cd95dddf5f)
* [Alice](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304651e3253e3945d73c9e377c9bc569a03f53c53677b64611de4d74f89134ad2407) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304651e3253e3945d73c9e377c9bc569a03ffe1f86487d8edc0978edbaf2efc1bb3880718cb7600a8d38c43ef077586c91ff)
* [Arale](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046bc40c1c739a87498af9d1c905b6354eb9c7633011a3e25e6b2063aced92345c8) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046bc40c1c739a87498af9d1c905b6354ebe62f4c23d8c6c3df25df1cf18d95b571d3fa62696f5a998d4278ede151a29b3b)
* [Pure](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046820940f093f5a3dcf2f3a8c5c1b86a24) ([BSD License](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462be5821b0db59aaf7b45642f22d98a8bcd2144ac30a747d01d461faa8365d31eec048f8f7f303f10ffe1ed209b34e0f8)
* [Semantic UI](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d8202cb3c044a33c3ce88a3718636373f) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d2ef96adce29bb2d1ba24ba7be424ca35dce5fc4cc29cf696686acaaf8dcfbc5269f4ce2f13fd7bdf22a62fd6e0ca64d2)
* [FastClick](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461ba98c1451b2673b38c020bfa4820e665a97b827976b0f6824c51809eae0b195) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461ba98c1451b2673b38c020bfa4820e6614c1295c2a005d5450890c68da1c41f1fb1329b37da1b0d33e20f19cad28549c)
* [screenfull.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462a65f16275212ca6b7b7326d099e6667550cd3f5d49f6cd2e346cbc18e52dd7f) ([MIT
License](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462a65f16275212ca6b7b7326d099e6667ba2d5a8caf7ad1d155951e0463a2eb9642ec3629add084fc72473ba7ff4cd13a9fe22dea5dd64128540b650408d8d509)
* [FlexSlider](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046985ec38923a0657f63b6aeb6f6bacb98fc617d057986835233654e95d0ddd91b) ([GPL 2.0](http://u.720life.cn/g/0faf03d8167674bee364b61e9b7d6858dd29ebe81bbdead4b3a4fad1590c19d316db3dbbd0b8a0335824c1d4cabef07a)
* [Hammer.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c369d1e15aa2ec5fccd7f38426e3d0ae82206489887b89ffd8b5f397c24dba48) ([MIT License](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c369d1e15aa2ec5fccd7f38426e3d0aece7d46a90f4a5408001431004fb5ae72460300090dc40a9aa9712c56c009cb11)
* [Flat UI](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463ab627e8b43d9c12a0dd5a549ca5b3597f0cb17a9f1a108247682ccd3b372616) ([CC BY 3.0 and MIT License](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463ab627e8b43d9c12a0dd5a549ca5b359ccc731536591496ae968fe0039e396aeff09b7f8d0cc3ab13828538d9fc473d2)
* [store.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046820841448b4a7a1ffd2aab6528be878fdec3e4a7d9dac4c0c64d459d07aa0403) ([MIT License](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046820841448b4a7a1ffd2aab6528be878fc3e3e6ef40a5a54890b5bad2255ab9e5407e4eaa5df323207e71aab86292be32)
* [bootstrap-datepicker.js](http://u.720life.cn/g/e60a4ddff95c04af131cdb6b5e06194773020b7649a80706acdc44b84032995af1f95772cae79282e30de9dc6108c1ad) ([Apache License 2.0](http://u.720life.cn/g/e60a4ddff95c04af131cdb6b5e06194773020b7649a80706acdc44b84032995a11f0e5d8511fdecd9c4bd799322016c0cfd1049bc204699ee5b9bd5c32266f102e38e1053437f57aa7d4cc85c5b116ee)
* [iScroll](http://u.720life.cn/g/1636696c706a7535ba6b74952d11a2ef712d3fb2468d6fc943a578ffb74937b7) ([MIT License](http://u.720life.cn/g/1636696c706a7535ba6b74952d11a2ef65a9d820ec4321644e420748037012b1)

可能会有部分项目遗漏，我们会不断整理更新。

### Developed with Open Source Licensed [WebStorm](http://u.720life.cn/g/9c08b6539a854316e0b37584151fe42f5a8e56ce58f5034eae449861c2da9efd74924ad5ba67cc1c0f6732307b2e7c9c)

 
 
 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea9619edc6bf63133c514c69a989602176ba5a42fc49617ae5d8e14fa0d1dbea3fb55dab5528cc34078b2253c92aa70c7)