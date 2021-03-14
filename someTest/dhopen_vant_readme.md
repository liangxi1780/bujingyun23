 
      
     
 
 
     
 

 Lightweight Mobile UI Components built on Vue 

 
     
     
     
     
     
     
     
 

 
  🇨🇳  访问中文版 
  &nbsp;
  🚀  Vant Weapp - 小程序版 
 

---

## Features

* 50+ Reusable components
* 80%+ Unit test coverage
* Extensive documentation and demos
* Support [babel-plugin-import](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462aaced1fa5f947db3914dcd309b60a3e71c4b60d088e736628077dab47444f64478b22ac59d0b3daf92a0f1c947dc8de)
* Support TypeScript
* Support SSR

## Install

#### NPM

```shell
npm i vant -S
```

#### YARN

```shell
yarn add vant
```

#### CDN

```html
 
 

 
  
  
```

## Quickstart

#### 1. Use [babel-plugin-import](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462aaced1fa5f947db3914dcd309b60a3e71c4b60d088e736628077dab47444f64478b22ac59d0b3daf92a0f1c947dc8de) (Recommended)

```bash
# Install babel-plugin-import
npm i babel-plugin-import -D
```

```js
// set babel config in .babelrc or babel-loader
// Note: Don't set libraryDirectory if you are using webpack 1.
{
  "plugins": [
    ["import", {
      "libraryName": "vant",
      "libraryDirectory": "es",
      "style": true
    }]
  ]
}
```

Then you can import components from vant, equivalent to import manually below.

```js
import { Button } from 'vant';
```

> If you are using TypeScript，please use [ts-import-plugin](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f524422f9534b81f016aa6e751cdffdab53144349fec878def9417627b266fc) instead

#### 2. Manually import

```js
import Button from 'vant/lib/button';
import 'vant/lib/vant-css/base.css';
import 'vant/lib/vant-css/button.css';
```

#### 3. Import all components

```js
import Vue from 'vue';
import Vant from 'vant';
import 'vant/lib/vant-css/index.css';

Vue.use(Vant);
```

> If you configured babel-plugin-import, you won't be allowed to import all components.

See more in [Quickstart](http://u.720life.cn/g/36797055cd4afe462930655519827aa4dbc28ac46e8dc65677ef0642bcb4709a2d216923a1b990ff74c43057ecdd7fd6).

## Contribution

Please make sure to read the [Contributing Guide](./.github/CONTRIBUTING.md) before making a pull request.

## Browser Support

Modern browsers and Android 4.0+, iOS 6+.

## Links

* [Documentation](http://u.720life.cn/g/36797055cd4afe462930655519827aa479839138ecda46eba665fca0ad00bd48)
* [Changelog](http://u.720life.cn/g/36797055cd4afe462930655519827aa4dbc28ac46e8dc65677ef0642bcb4709ae0f1b9f9e2dea71aa654d07049351624)
* [Vant Demo](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465cd2ad6ed181d693242703045902cce8c697463be025c4ac9da05540f0f6fca9)
* [Vant Weapp: Weapp UI](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469e4b782c858cfd572db9884a9548a8014810590f63a365ee1649fc29a832ea18)
* [Zent: PC UI base on React](http://u.720life.cn/g/095438af5533ac3c0c425063e628f415011e95821061d1d16f468d463ded9a081bb05a1713a58d6d371f07157619d0bc)


## Preview

You can scan the following QR code to access the demo：

 

## Wechat Group

Scan the qrcode to join our wechat discussion group, please note that you want to join Vant discussion group.

 

## LICENSE

[MIT](http://u.720life.cn/g/fa1db2c4a526903522dec7b8417f89d15f847589016765e3143cbb68cadbc104b1c4e151f2bc0d5bdecbcbaec8e9f53f6911e682a15e2223b2e88a1c1a85af42)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e02dea1c87180f3f94fa7c09dbb597c657e12d5d1e8a284086036624b46c9c557da084cbfc57d396fcaf0c030e3dd548c)