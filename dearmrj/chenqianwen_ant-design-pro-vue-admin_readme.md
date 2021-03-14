English | [简体中文](./README.zh-CN.md)

 Ant Design Pro Vue 
 
An out-of-box UI solution for enterprise applications as a Vue boilerplate. based on   Ant Design of Vue 
 

 

[![Backers on Open Collective](https://opencollective.com/ant-design-pro-vue/backers/badge.svg)](#backers) [![Sponsors on Open Collective](https://opencollective.com/ant-design-pro-vue/sponsors/badge.svg)](#sponsors) [![License](https://img.shields.io/npm/l/package.json.svg?style=flat)](https://github.com/sendya/ant-design-pro-vue/blob/master/LICENSE)
[![Release](https://img.shields.io/github/release/sendya/ant-design-pro-vue.svg?style=flat)](https://github.com/sendya/ant-design-pro-vue/releases/latest)
[![Travis branch](https://travis-ci.org/sendya/ant-design-pro-vue.svg?branch=master)](https://travis-ci.org/sendya/ant-design-pro-vue)

 

- Preview: https://preview.pro.loacg.com
- Home Page: https://pro.loacg.com
- Documentation: https://pro.loacg.com/docs/getting-started
- ChangeLog: https://pro.loacg.com/docs/changelog
- FAQ: https://pro.loacg.com/docs/faq
- Branches: 
  - demo/router-view-table: CRUD view in router
  - feature/demand_load: loaded on demand
  - feature/lang: i18n support
  - feature/dynamic-menu: dynamic menu demo
  - lite: lite template (legacy)


Overview
----

![dashboard + multi-tabs](https://static-2.loacg.com/open/static/github/20190224163345.jpg)

![dashboard + setting](https://static-2.loacg.com/open/static/github/20181126112124.png)

![user profile](https://static-2.loacg.com/open/static/github/20180916-134251.png)

![permission list](https://static-2.loacg.com/open/static/github/20180916-154937.png)


### Env and dependencies

- node
- yarn
- webpack
- eslint
- @vue/cli ~3
- [ant-design-vue](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e9854afb95fc2c4f46c385f1ad1c1b1e644e2a29c8d4c09fb06ebdf1dd63e142) - Ant Design Of Vue 
- [vue-cropper](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cb02cb667b2e3a1151b644ec4f3fc255851d63e3a4b2ec8054369d4e896c1637) - Picture edit
- [@antv/g2](http://u.720life.cn/g/cace86085bfdb3f3ceccf2ebf27c1561e01019ca4035c4442125d7bd8108a203e8b8870fb3486ea6911e55ed60147014) - AntV G2
- [Viser-vue](http://u.720life.cn/g/3b8a5feda496d337294216be41f8c62c1435c481a262cd3f59dbc42f71c6f6d4bd4238bda473274ed2789269e33a9f4c5ab02b4345b08262efbe738cddcba3bd)  - Antv/G2 of Vue

> Note:  [Yarn](http://u.720life.cn/g/661e937512ac7ab6d29ddae041a9c3066c65c7aae19b9978fd58aa89bc881660) package management is recommended, the exact same version loaded with the demo site of this project (yarn.lock) . but you can also use npm


### Project setup

- Clone repo
```bash
git clone https://github.com/sendya/ant-design-pro-vue.git
cd ant-design-pro-vue
```

- Install dependencies
```
yarn install
```

- Compiles and hot-reloads for development
```
yarn run serve
```

- Compiles and minifies for production
```
yarn run build
```

- Lints and fixes files
```
yarn run lint
```


### Other

- **IMPORTANT : About Issue feedback !! when opening Issue read [Issue / PR Contributing](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046540369d8253c9e089ad527dbcce538cfcad1a77744d0e2025dba7999781b37b2108ed15fa05ce6d0087a2ced0e73ed82)**

- [Vue-cli3](http://u.720life.cn/g/d2cf559f8c6d745b4f7f93b06ed0aac3628ac0bd0893688bc47ad812819d84ac) used by the project.
- Disable Eslint (not recommended): remove `eslintConfig`  field in `package.json`  and `vue.config.js` field `lintOnSave: false`

- Load on Demand: modify `/src/main.js` L14,  replace to `import './core/lazy_use'` code.

- Customize Theme:  [Custom Theme Config](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046533c51541883223071820434e6c84511696883bfe6d9bfc0575d8c760311df862aa7fe5f67c7e76cfceca34654e6e4ab572fc36540a412b4b6bc301fa23e02ea545df3317cbf4eba530529b3aaaeb24731d0a8c948ce65df2aaa368184359591)


## Browsers support

Modern browsers and IE10.

| [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) IE / Edge | [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) Firefox | [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) Chrome | [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) Safari | [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) Opera |
| --- | --- | --- | --- | --- |
| IE10, Edge | last 2 versions | last 2 versions | last 2 versions | last 2 versions |


## Contributors

This project exists thanks to all the people who contribute. 
   


## Backers

Thank you to all our backers! 🙏 [[Become a backer](http://u.720life.cn/g/df0d0b49c04f66c9033e4268d2ee0e12094d5b6d6f94735a1a60ba8a88c9b171cc7c917c9815508ef16ff3d2cf2c068d6462f9056e03fc47904a36bda4729dd5)]

   


## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](http://u.720life.cn/g/df0d0b49c04f66c9033e4268d2ee0e12094d5b6d6f94735a1a60ba8a88c9b171599fb713f9cd0508d1407b933919efa5d6e172f61c79231df0119075f1d9067c)]

   
   
   
   
   
   
   
   
   
   




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef46b8ca3811642ac4552d8d25ab44474c34f6d991e41df7e032b795ef8a5ae3b35f19332b74711ec27550ca84c217376a542d46532121263811a3d60b3c1b8e1)