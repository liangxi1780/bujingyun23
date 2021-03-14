# Taro

[![](https://img.shields.io/node/v/@tarojs/cli.svg?style=flat-square)](https://www.npmjs.com/package/@tarojs/cli)
[![](https://img.shields.io/npm/v/@tarojs/taro.svg?style=flat-square)](https://www.npmjs.com/package/@tarojs/taro)
[![](https://img.shields.io/npm/l/@tarojs/taro.svg?style=flat-square)](https://www.npmjs.com/package/@tarojs/taro)
[![](https://img.shields.io/npm/dt/@tarojs/taro.svg?style=flat-square)](https://www.npmjs.com/package/@tarojs/taro)
[![](https://img.shields.io/travis/NervJS/taro.svg?style=flat-square)](https://www.npmjs.com/package/@tarojs/taro)

> 👽 Taro['tɑ:roʊ]，泰罗·奥特曼，宇宙警备队总教官，实力最强的奥特曼。

## 简介

**Taro** 是一套遵循 [React](http://u.720life.cn/g/4c49339db9b897b20ce9fa9b972593befe0bb743870912e185120b1d918dee79) 语法规范的 **多端开发** 解决方案。现如今市面上端的形态多种多样，Web、React-Native、微信小程序等各种端大行其道，当业务要求同时在不同的端都要求有所表现的时候，针对不同的端去编写多套代码的成本显然非常高，这时候只编写一套代码就能够适配到多端的能力就显得极为需要。

使用 **Taro**，我们可以只书写一套代码，再通过 **Taro** 的编译工具，将源代码分别编译出可以在不同端（微信小程序、H5、React-Native 等）运行的代码。

## 使用案例

Taro 已经投入了我们的生产环境中使用，业界也在广泛地使用 Taro 开发多端应用。

![案例](https://i.loli.net/2018/10/11/5bbf3604909b6.png)

[征集更多优秀案例](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046aa7876cb9d1c6ed117d983058b37f215008c05c28e9028bce7360a0362e95e17)

## 示例项目

* Taro Redux 示例 [taro-redux-sample](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ebc74fe749ac4cd2454f4ef8fe4805664c4df97b189e9b83db7dbd9ca099185)
* [TodoMVC](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304680c052abde2b634a8863bef94165857a50ba72c03c8a662f9b19bbf4c8bf9953) (小程序/H5/React Native)
* Taro 组件库示例 [taro-components-sample](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ba581e45ca9e0b3f9e254d2ca08a0fa32f98185286735c6818c72cc08762c4b)
* Taro 端能力示例 [taro-apis-sample](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462570f10e270ed419b31fc8f64541feb98dbe8b4d9191b3a4a141cffc65e1fd23)
* Taro 实验性特性项目 [taro-todo](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b30f7608516c1aa3e704e4de1a4a9abf0dcc132a5bb964a9c3be257b052fb57d)
* [仿知乎小程序](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f521afadf2eb0c57d32bf8444571e44888083f446e15b59586b1c6c9de925ac0)
* [Taro整合Dva示例](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046295f6801783216c45378f5ed248c2e1953c78a02aed8f978fa1d988df9fb3c55)
* [V2ex小程序（TypeScript）](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469c966c20857d045ff7e31218852cbd894dc85cac45c829e7b315fb0e918ff297)
* [与微信小程序原生融合的示例](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304662b2a3bcd24c8db54b8361b713f5db844c3132633bcfe8c671baf27b3f75dc6a)
* [基于Taro + Dva构建的时装衣橱(电商实战项目)](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466e1ae9436ab442bbc895bdfb186bcecc698bc45a28265c598b5c911312114d3b)

## 文章教程

* [从0到1构建适配不同端（微信小程序、H5、React-Native 等）的taro + dva应用](http://u.720life.cn/g/8a35642bd69eb006eb1f0259b3a6f6f0a0ea17bcbc47e211ed7e47c714bdef86fa01ba4eb40e9f3f6b88de381c7cfd15)
* [【小程序taro最佳实践】http请求封装（方便使用，增加token，统一错误日志记录和上报）](http://u.720life.cn/g/6900aa436d7855810ebad430307e6f91c8b258b81c5d2f9bc5f21dfc6a8e3e472372f782e356e4923bc261f8e54e61f4)
* [【小程序taro 最佳实践】异步action优雅实践(简化流程)](http://u.720life.cn/g/6900aa436d7855810ebad430307e6f91c8b258b81c5d2f9bc5f21dfc6a8e3e47481e45a084580ee750012e58674bd24f)
* [使用Taro框架开发小程序](http://u.720life.cn/g/8a35642bd69eb006eb1f0259b3a6f6f0ebfc4af50a7c55032096c4f70f16e3f3b022a15263b46e342da11f1b58e2c90c)
* [Taro下利用Decorator快速实现小程序分享](http://u.720life.cn/g/8a35642bd69eb006eb1f0259b3a6f6f0abd142f65461b213880086df83ccf7bde4f760aeb18ca031dd74c27c1f079d1d)
* [微信小程序授权登陆方案以及在Taro下利用Decorator修饰器实现](http://u.720life.cn/g/8a35642bd69eb006eb1f0259b3a6f6f0426f8c03381214240c86c0fd60b0734229e9e308b1cddcf32fd2118ae0ff924f)
* [试用React语法的多端框架Taro问题汇总](http://u.720life.cn/g/6900aa436d7855810ebad430307e6f91c8b258b81c5d2f9bc5f21dfc6a8e3e47365033b9aa1c4114ebcedea334a1085e)
* [Taro 在京东购物小程序上的实践](http://u.720life.cn/g/8a35642bd69eb006eb1f0259b3a6f6f0edbcd2e21a9e585728282f38cf334c363794b423a5df6b6e76161ed629e4cbd9)
* [Taro实践 - TOPLIFE小程序 开发体验](http://u.720life.cn/g/8a35642bd69eb006eb1f0259b3a6f6f087f9a754f5a1067a688a85abf2f881e70d7a4af535f623a473c69119d53fafc8)
* [Taro 技术揭秘：taro-cli](http://u.720life.cn/g/8a35642bd69eb006eb1f0259b3a6f6f06e2741773891c4a72d1c8b050c857834d8fcbd65da62cd304a52e5a3a70c977d)
* [为何我们要用 React 来写小程序 - Taro 诞生记](http://u.720life.cn/g/8a35642bd69eb006eb1f0259b3a6f6f0cfbf2caea6af72e9d1193ae6de8c847a54b171dc61142d368a87811d816916ec)

## Taro 特性

#### React 语法风格

Taro 的语法规则基于 React 规范，它采用与 React 一致的组件化思想，组件生命周期与 React 保持一致，同时在书写体验上也尽量与 React 类似，支持使用 JSX 语法，让代码具有更丰富的表现力。

代码示例

```javascript
import Taro, { Component } from '@tarojs/taro'
import { View, Button } from '@tarojs/components'

export default class Index extends Component {
  constructor () {
    super(...arguments)
    this.state = {
      title: '首页',
      list: [1, 2, 3]
    }
  }

  componentWillMount () {}

  componentDidMount () {}

  componentWillUpdate (nextProps, nextState) {}

  componentDidUpdate (prevProps, prevState) {}

  shouldComponentUpdate (nextProps, nextState) {
    return true
  }

  add = (e) => {
    // dosth
  }

  render () {
    return (
       
         {this.state.title} 
         
          {this.state.list.map(item => {
            return (
               {item} 
            )
          })}
           添加 
         
       
    )
  }
}
```

#### 快速开发微信小程序

Taro 立足于微信小程序开发，众所周知小程序的开发体验并不是非常友好，比如小程序中无法使用 npm 来进行第三方库的管理，无法使用一些比较新的 ES 规范等等，针对小程序端的开发弊端，Taro 具有以下的优秀特性：

✅ 支持使用 npm/yarn 安装管理第三方依赖。

✅ 支持使用 ES7/ES8 甚至更加新的 ES 规范，一切都可自行配置。

✅ 支持使用 CSS 预编译器，例如 Sass 等。

✅ 支持使用 Redux 进行状态管理。

✅ 小程序 API 优化，异步 API Promise 化等等。

#### 支持多端开发转化

Taro 方案的初心就是为了打造一个多端开发的解决方案。目前 Taro 代码可以支持转换到 **微信小程序**/**H5 端**以及**移动端（React-Native）**。

    微信小程序  

    H5端  


## 快速开始

安装 Taro 开发工具 `@tarojs/cli`

使用 npm 或者 yarn 全局安装，或者直接使用 [npx](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b36b48c82aba0a8190d0111a0ce859098a4b5f6721293cc5819436bcc078b3e90ac3d17143a0ff6082c6bc9560f3b595c708172d65313204d7328d11ad4cfc43415)

```bash
$ npm install -g @tarojs/cli
$ yarn global add @tarojs/cli
```

使用命令创建模板项目

```bash
$ taro init myApp
```

npm5.2+ 也可在不全局安装的情况下使用 npx 创建模板项目

```bash
$ npx @tarojs/cli init myApp
```

进入项目目录开始开发，可以选择小程序预览模式，或者 H5 预览模式。若使用微信小程序预览模式，则需要自行下载并打开[微信开发者工具](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484c20708e11463bd684459f5de41dafa7d0c3e1211843e1cdbef7a640a8fe47dc75e47294b5e75d000ca479e5d58269765021b8fbabad90318955d5cae729789a9)，选择预览项目根目录。

微信小程序编译预览模式

```bash
# npm script
$ npm run dev:weapp
# 仅限全局安装
$ taro build --type weapp --watch
# npx 用户也可以使用
$ npx taro build --type weapp --watch
```

H5 编译预览模式

```bash
# npm script
$ npm run dev:h5
# 仅限全局安装
$ taro build --type h5 --watch
# npx 用户也可以使用
$ npx taro build --type h5 --watch
```

## 项目打包
打包小程序代码

```bash
# npm script
$ npm run build:weapp
# 仅限全局安装
$ taro build --type weapp
# npx 用户也可以使用
$ npx taro build --type weapp
```

打包 H5 代码

```bash
# npm script
$ npm run build:h5
# 仅限全局安装
$ taro build --type h5
# npx 用户也可以使用
$ npx taro build --type h5
```

## 开发计划

[开发计划](./PLANS.md)

## 更新日志

本项目遵从 [Angular Style Commit Message Conventions](http://u.720life.cn/g/4e20e720fe373c1a62f69fb6778bcfe3aeecdf9c75f68a615e887f30827ff32d5c5fde2217dd1d505994eac3ce98b66f39404d81f6a974c9c54e1a8986ce6158)，更新日志由 `conventional-changelog` 自动生成。完整日志请点击 [CHANGELOG.md](./CHANGELOG.md)。

## 开发交流

[官方交流微信群](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046aa7876cb9d1c6ed117d983058b37f2154d1fbca85e85b78e2d26765bb11be05a)

## License

MIT License

Copyright (c) 2018 O2Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e11050912ed170c3ec1a916d69e451773737c4143f681bc045f8b89d2e1910c56f2157e4bdc4e765aed71863fe9101075)