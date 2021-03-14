 
   
     
   
 

 

Umi 的封装脚手架，但又不仅仅是一个脚手架，还是一种开发提效生态

[![Build With Umi](https://img.shields.io/badge/build%20with-umi-028fe4.svg?style=flat-square)](http://umijs.org/)
   
 

简单好用，无脑撸业务。

## 安装

通过 npm 安装即可

`npm install -g alita`

通过 yarn 安装即可

`yarn global add alita`

若有权限问题，需要 `sudo`

## 快速开始

### 新建项目

```bash
$ alita g app myApp
```

![2019-07-02 21 05 53](https://user-images.githubusercontent.com/11746742/60694246-190baf00-9f10-11e9-9f88-06f5378cc214.gif)

### 启动项目

```sh
$ cd myApp
$ yarn  (或 npm i)
$ yarn start (或 npm start)
```

## 配置文档(9)

### umi

alita 基于 [umi](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466a366ec01265e7a4529f7a5163eb1fa9) ,支持 umi 的所有配置项。`umi-plugin-react` 的配置项在 `umi` 中配置。
如

```bash
export default {
  umi: {
    dva: {
      immer: true,
    },
    antd: true,
    polyfills: ['ie9'],
    locale: {},
    dynamicImport: {
      webpackChunkName: true,
      loadingComponent: './components/Loading.js',
    },
    hd: true
  }
};
```

### appType

- 类型：String

定义项目类型 （ 值为 pc 、 h5 、 cordova ）

默认：

```js
appType:'pc'
```

### proxy

如果要代理请求到其他服务器，可以这样配：

```js
"proxy": {
  "/api": {
    "target": "http://jsonplaceholder.typicode.com/",
    "changeOrigin": true,
    "pathRewrite": { "^/api" : "" }
  }
}
```

然后访问 `/api/users` 就能访问到 [http://jsonplaceholder.typicode.com/users](http://u.720life.cn/g/c81c81832c6af9b7d5c508d07b0532ac3d5ff73ca24b96cd0f29e9c5df96aa4da827282af3c1e8d8768ca0df572f3b6a) 的数据。

### retainLog

默认会在打包 ( build ) 的时候，移除 `console.*` ，保留 `console.error` 。

如果你需要在打包之后仍然保留 `console` ，请配置

```js
retainLog:true
```

### complexRoute

alita 默认只识别 index 文件（ pages/*/index ）生成路由，如果你需要嵌套路由功能，请配置

```js
complexRoute:true
```

### mainPath

alita 默认把 `pages/index/index` 文件作为根路由，如果你希望使用其他文件，请配置

```js
mainPath:'/home'
```

### tongjiCode

增加百度统计功能

```js
tongjiCode:'baidu code'
```

### gaCode

增加谷歌统计功能

```js
gaCode:'google code'
```

### keepalive

支持 keep alive 功能，底层实现是 [react-router-cache-route](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304692a204e6e16921dee71d561c8afa57a2fa700aa4dd8681615bfa194044e4862013a98dcb56f11c743c9cbfb02b660371) ，如果你需要使用，请配置

```js
 keepalive:['/list']
```

#### keep alive 初始化

由于 umi 还不支持 keep alive ，暂时通过覆盖 umi 库文件的方式实现，所以每次重装模块之后都要先执行初始化

```sh
alita keepalive
```

配置中的页面，会被保持，你可以在不需要的时候手动解除

```js
import { dropByCacheKey } from 'alita';

export default () => {
  const clearCache = () => {
    dropByCacheKey('/list');
  };
  return (
     
       clear list page cache 
     
  );
};
```

## 新建页面

### 新建空白页面

```sh
$ alita g pages home
```

![2019-07-02 21 10 03](https://user-images.githubusercontent.com/11746742/60694280-32acf680-9f10-11e9-8a28-6638308a76fb.gif)

### 新建区块页面

#### 增加配置

```ts
export default {
  appType: 'pc',
  block: {
    defaultGitUrl: 'https://github.com/ant-design/pro-blocks',
  },
};
```

## 原生打包

### 修改配置

```js
export default {
  appType: 'cordova',
};
```

### 初始化 cordova 项目

```sh
$ alita cordova --init
```

### 生成 ios 项目

```sh
$ alita cordova --ios
```

### 生成 android 项目

```sh
$ alita cordova --android
```

注意：安卓开发的时候，启动时需要配置环境变量

```json
"scripts":{
  "start":"CORDOVA=android alita dev"
}
```

## 其他配套生态

### 接口翻译

[米莱狄(Milady)](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304656a7b245e0e49c1a008dbbdbb06c555aa064ad661a96ee88719733f8abfa9f7d) 通过解析接口文档生成前端代码
![jiekou4 2019-07-05 10_45_29](https://user-images.githubusercontent.com/11746742/60694824-114d0a00-9f12-11e9-85e3-0213e35e602a.gif)
 后续还会加入接口版本控制等功能

### 图表封装

[rc-charts](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046125399fb881967ebad85dbef2c585610c3c520ca6efb74209ca90e208a0665e6) 一个基于 BizCharts 的图表库
![image](https://user-images.githubusercontent.com/11746742/60695149-4d349f00-9f13-11e9-89d0-eae52b1a9b99.png)

### H5通用布局

[alita-layout](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304613788f6a6af29f123f2771be1b7717180cb39db5548416e85348b15e98c8a156) H5 通用布局,直接使用微信小程序的 API 定义，简单易用。
![image](https://user-images.githubusercontent.com/11746742/60695238-9f75c000-9f13-11e9-935c-7fbea42d18f9.png)

可以算是[ant-design-pro-layout](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6e11bcd1789040e2198d673b48072251e3a08f97bcf16adf736e2ac58c28f7533)的补充项目

### VC Code 插件

现在 VS Code 插件[Umi Pro](http://u.720life.cn/g/61df49c8dfe6497e1d755535043d5993f084ad4bb2562a93ce813aeeb8e143e31ce529a8f29bba55ad86d25d14134388e6219b6dab205cb4183396611b241e961cda9cf8a4e332ef94dcd372b534489c)也支持alita了。

![action1](https://user-images.githubusercontent.com/11746742/60695328-ebc10000-9f13-11e9-8ce4-163fa51c816d.gif)

### 国际化

和阿里巴巴国际化全流程解决方案 kiwi 结合使用，能实现一键提取中文文案 、一键替换文本、一键翻译、一键导出文本等功能。配合 vscode 插件使用，甚至可以实现可视化操作功能，后续国际化版本甚至可以让客服人员点点鼠标就能高效快速完成。
（还未兼容umi的locale）

### 页面权限

直接新建 src/Authority.js 文件，然后在配置文件中，写上需要检测权限的页面 url 即可。甚至可以使用正则，通配符的形式进行页面矫权。

### 京东Alita

五月份的时候京东开源了一套把React Native代码转换成微信小程序代码的转换引擎工具，也叫做[Alita](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463268e51d2c95c18edfc7b287ebe3f29c071410054a8ff68b93849208577193f8)。因为这个包发的是`@areslabs/alita` ，所以并没有注意到包名冲突问题。

通过npm安装, `npm install -g @areslabs/alita` 。

使用 `alita -i myproject -o myprojectwp` 将现有的Rn项目转化成小程序项目。

导致同时安装 `alita` 和 `@areslabs/alita` 时，会有命令冲突的情况发生。

### 社区

* 钉钉，请扫描下面的二维码加群

  

* 微信，扫描二维码添加机器人，回复alita进群

  

### 其他业务

其他业务需求都可以通过，插件的形式实现，有需要的项目按需添加，也是只要简单的更改配置文件即可，不需要写多余的代码。

我们将为你提供技术指导与技术支持，使umi更适用于你们内部业务，这一切都是免费的。

请告诉我们你的需求[Alita/Issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304613788f6a6af29f123f2771be1b771718b89c21dddac188d87297fbcc71bffa64) 、[umi/Issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468b1b1a40a06e6d5abffeb16cd5a155eb9a2a865ed9e1e51491e25dfa737d4de4) 、 [ant-design-pro/Issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6fdc6904f4a7c0cb72dd2229f0413ca299e37f85d3e0c59f670198a7300a18255)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb00d0aae5c9f5c5e114a38cb08e945d9db4cf78a35cebcf3ec53ab133bb5607b9bb76d18b320edd86170af951d0df238)