 
   
     
   
 

 Ant Design 

 

An enterprise-class UI design language and React UI library.

[![CircleCI status][circleci-image]][circleci-url] [![CI status][github-action-image]][github-action-url] [![codecov][codecov-image]][codecov-url] [![NPM version][npm-image]][npm-url] [![NPM downloads][download-image]][download-url]

[![david deps][david-image]][david-url] [![david devDeps][david-dev-image]][david-dev-url] [![Total alerts][lgtm-image]][lgtm-url] [![FOSSA Status][fossa-image]][fossa-url] [![Issues need help][help-wanted-image]][help-wanted-url]

[![Follow Twitter][twitter-image]][twitter-url] [![Gitter][gitter-english-image]][gitter-english-url] [![Gitter][gitter-chinese-image]][gitter-chinese-url] [![[SemVer stability]][semver-stability-image]][semver-stability-url]

[npm-image]: http://img.shields.io/npm/v/antd.svg?style=flat-square
[npm-url]: http://npmjs.org/package/antd
[circleci-image]: https://img.shields.io/travis/com/ant-design/ant-design.svg?style=flat-square
[circleci-url]: https://travis-ci.com/ant-design/ant-design
[github-action-image]: https://github.com/ant-design/ant-design/workflows/test/badge.svg
[github-action-url]: https://github.com/ant-design/ant-design/actions?query=workflow%3Atest
[codecov-image]: https://img.shields.io/codecov/c/github/ant-design/ant-design/master.svg?style=flat-square
[codecov-url]: https://codecov.io/gh/ant-design/ant-design/branch/master
[david-image]: https://img.shields.io/david/ant-design/ant-design?style=flat-square
[david-dev-url]: https://david-dm.org/ant-design/ant-design?type=dev
[david-dev-image]: https://img.shields.io/david/dev/ant-design/ant-design?style=flat-square
[david-url]: https://david-dm.org/ant-design/ant-design
[download-image]: https://img.shields.io/npm/dm/antd.svg?style=flat-square
[download-url]: https://npmjs.org/package/antd
[lgtm-image]: https://flat.badgen.net/lgtm/alerts/g/ant-design/ant-design
[lgtm-url]: https://lgtm.com/projects/g/ant-design/ant-design/alerts/
[fossa-image]: https://app.fossa.io/api/projects/git%2Bgithub.com%2Fant-design%2Fant-design.svg?type=shield
[fossa-url]: https://app.fossa.io/projects/git%2Bgithub.com%2Fant-design%2Fant-design?ref=badge_shield
[help-wanted-image]: https://flat.badgen.net/github/label-issues/ant-design/ant-design/help%20wanted/open
[help-wanted-url]: https://github.com/ant-design/ant-design/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22
[twitter-image]: https://img.shields.io/twitter/follow/AntDesignUI.svg?label=Ant%20Design&style=social
[twitter-url]: https://twitter.com/AntDesignUI
[gitter-english-image]: https://img.shields.io/gitter/room/ant-design/ant-design-english.svg?style=flat-square&logoWidth=18&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NCjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgd2lkdGg9IjEyMzUiIGhlaWdodD0iNjUwIiB2aWV3Qm94PSIwIDAgNzQxMCAzOTAwIj4NCjxyZWN0IHdpZHRoPSI3NDEwIiBoZWlnaHQ9IjM5MDAiIGZpbGw9IiNiMjIyMzQiLz4NCjxwYXRoIGQ9Ik0wLDQ1MEg3NDEwbTAsNjAwSDBtMCw2MDBINzQxMG0wLDYwMEgwbTAsNjAwSDc0MTBtMCw2MDBIMCIgc3Ryb2tlPSIjZmZmIiBzdHJva2Utd2lkdGg9IjMwMCIvPg0KPHJlY3Qgd2lkdGg9IjI5NjQiIGhlaWdodD0iMjEwMCIgZmlsbD0iIzNjM2I2ZSIvPg0KPGcgZmlsbD0iI2ZmZiI%2BDQo8ZyBpZD0iczE4Ij4NCjxnIGlkPSJzOSI%2BDQo8ZyBpZD0iczUiPg0KPGcgaWQ9InM0Ij4NCjxwYXRoIGlkPSJzIiBkPSJNMjQ3LDkwIDMxNy41MzQyMzAsMzA3LjA4MjAzOSAxMzIuODczMjE4LDE3Mi45MTc5NjFIMzYxLjEyNjc4MkwxNzYuNDY1NzcwLDMwNy4wODIwMzl6Ii8%2BDQo8dXNlIHhsaW5rOmhyZWY9IiNzIiB5PSI0MjAiLz4NCjx1c2UgeGxpbms6aHJlZj0iI3MiIHk9Ijg0MCIvPg0KPHVzZSB4bGluazpocmVmPSIjcyIgeT0iMTI2MCIvPg0KPC9nPg0KPHVzZSB4bGluazpocmVmPSIjcyIgeT0iMTY4MCIvPg0KPC9nPg0KPHVzZSB4bGluazpocmVmPSIjczQiIHg9IjI0NyIgeT0iMjEwIi8%2BDQo8L2c%2BDQo8dXNlIHhsaW5rOmhyZWY9IiNzOSIgeD0iNDk0Ii8%2BDQo8L2c%2BDQo8dXNlIHhsaW5rOmhyZWY9IiNzMTgiIHg9Ijk4OCIvPg0KPHVzZSB4bGluazpocmVmPSIjczkiIHg9IjE5NzYiLz4NCjx1c2UgeGxpbms6aHJlZj0iI3M1IiB4PSIyNDcwIi8%2BDQo8L2c%2BDQo8L3N2Zz4%3D
[gitter-english-url]: https://gitter.im/ant-design/ant-design-english?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge
[gitter-chinese-image]: https://img.shields.io/gitter/room/ant-design/ant-design.svg?style=flat-square&logoWidth=18&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NCjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgd2lkdGg9IjkwMCIgaGVpZ2h0PSI2MDAiIHZpZXdCb3g9IjAgMCAzMCAyMCI%2BDQo8ZGVmcz4NCjxwYXRoIGlkPSJzIiBkPSJNMCwtMSAwLjU4Nzc4NSwwLjgwOTAxNyAtMC45NTEwNTcsLTAuMzA5MDE3SDAuOTUxMDU3TC0wLjU4Nzc4NSwwLjgwOTAxN3oiIGZpbGw9IiNmZmRlMDAiLz4NCjwvZGVmcz4NCjxyZWN0IHdpZHRoPSIzMCIgaGVpZ2h0PSIyMCIgZmlsbD0iI2RlMjkxMCIvPg0KPHVzZSB4bGluazpocmVmPSIjcyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNSw1KSBzY2FsZSgzKSIvPg0KPHVzZSB4bGluazpocmVmPSIjcyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTAsMikgcm90YXRlKDIzLjAzNjI0MykiLz4NCjx1c2UgeGxpbms6aHJlZj0iI3MiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEyLDQpIHJvdGF0ZSg0NS44Njk4OTgpIi8%2BDQo8dXNlIHhsaW5rOmhyZWY9IiNzIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMiw3KSByb3RhdGUoNjkuOTQ1Mzk2KSIvPg0KPHVzZSB4bGluazpocmVmPSIjcyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTAsOSkgcm90YXRlKDIwLjY1OTgwOCkiLz4NCjwvc3ZnPg%3D%3D
[gitter-chinese-url]: https://gitter.im/ant-design/ant-design?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge
[semver-stability-url]: https://dependabot.com/compatibility-score.html/?dependency-name=antd&package-manager=npm_and_yarn
[semver-stability-image]: https://api.dependabot.com/badges/compatibility_score?dependency-name=antd&package-manager=npm_and_yarn&version-scheme=semver

 

[![](https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*Yl83RJhUE7kAAAAAAAAAAABkARQnAQ)](https://ant.design)

English | [Português](./README-pt_BR.md) | [简体中文](./README-zh_CN.md)

## ✨ Features

- 🌈 Enterprise-class UI designed for web applications.
- 📦 A set of high-quality React components out of the box.
- 🛡 Written in TypeScript with predictable static types.
- ⚙️ Whole package of design resources and development tools.
- 🌍 Internationalization support for dozens of languages.
- 🎨 Powerful theme customization in every detail.

## 🖥 Environment Support

- Modern browsers and Internet Explorer 11 (with [polyfills](http://u.720life.cn/g/87bbd50441ad714fa4b3a92b06a39057c99d561856c3866c7b363085c26fdd7bdc7127d3768b476950cf5c879de3b7cd23cb4590fe600588f77faa6d5d1234963e46cc767a73d0ae77ca5fcb6fd83039)
- Server-side Rendering
- [Electron](http://u.720life.cn/g/3bf7be49e40902cdc4c52b9e09f9c7aa1221ffef35f6b74c8471ca5af72b028b)

| [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) IE / Edge | [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) Firefox | [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) Chrome | [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) Safari | [ ](http://u.720life.cn/g/e8e63e9d56ec68b803322c46733da50e250bafa89bf75b6fa300450a04e79d004a89ee4f068d6e1f9b40f65bb657f76f) Electron |
| --- | --- | --- | --- | --- |
| IE11, Edge | last 2 versions | last 2 versions | last 2 versions | last 2 versions |

## 📦 Install

```bash
npm install antd
```

```bash
yarn add antd
```

## 🔨 Usage

```jsx
import { Button, DatePicker } from 'antd';

const App = () => (
  <>
     PRESS ME 
     
   
);
```

And import style manually:

```jsx
import 'antd/dist/antd.css'; // or 'antd/dist/antd.less'
```

### TypeScript

`antd` is written in TypeScript with complete definitions, check [Use in TypeScript](http://u.720life.cn/g/19f81165ca0412019ffde45bafddc8e50ac72de83e871fd00e63eb73bd88269a3915d4b90bcef7008fcb4238ed0d87e4) to getting started.

## 🌍 Internationalization

Dozens of languages supported in `antd`, see [i18n](http://u.720life.cn/g/19f81165ca0412019ffde45bafddc8e58c7681f2aff56e1de6ed66cb52a755cbcfce910523426ef30e2b2469347806cc).

## 🔗 Links

- [Home page](http://u.720life.cn/g/19f81165ca0412019ffde45bafddc8e5e3d2bc08ce722c630c370fa427cf7bb1)
- [Components](http://u.720life.cn/g/19f81165ca0412019ffde45bafddc8e581a6c0ce710fecda27a04fbc93a67416bab890589a4a7957ab2073360211f7e1)
- [Ant Design Pro](http://u.720life.cn/g/af16116c8afdc6f3c6def5f669313ae41b793a6cfc3ccd215998d7df35ff2905)
- [Ant Design Charts](http://u.720life.cn/g/fe23c8c1847826eac85d7142ea0f579aa4d23628cfb9e8732a8c53c2c4103058)
- [Change Log](CHANGELOG.en-US.md)
- [rc-components](http://u.720life.cn/g/2319b00587ca4f603809a09965816da5ed9d810aaa3ed53487ff4f1623bb0d61f4b94bd0fa5a1a723d635fd159a3327b)
- [Mobile UI](http://u.720life.cn/g/76b4223e691710012ddcc92b7a239de307848a81d1b466161ef90fd73eb19181)
- [Ant Design Icons](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f674c004c781e41c6bc064b8be6c0115a4)
- [Ant Design Colors](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6db8c51b52533761e3c6c9afdf5baea47)
- [Ant Design Pro Layout](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6e11bcd1789040e2198d673b48072251e3a08f97bcf16adf736e2ac58c28f7533)
- [Ant Design Pro Blocks](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f682f4a7a1dec3cd74d36daa9529d23068888260dd7fc7566a06fd2357f47f5b)
- [Dark Theme](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f623a7b911287da969c04a3905ea97f3d3e23aa7d684f8cca1e3af4591d124fac8)
- [Landing Pages](http://u.720life.cn/g/11c8090d2f4445715052cc074770ace435f20bebd65dab6813557305b7d39e1c)
- [Motion](http://u.720life.cn/g/5a4d19a3a4855c71d9c3ca94a0ab62e5be9e2337eb0e81f6a1236da0b05b7ee7)
- [Scaffold Market](http://u.720life.cn/g/e0fc2dd6d96e64d38afbb712cd7a30f4410e5079b8274f9409d5df9116202f53)
- [Developer Instruction](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6996e800524b092d98185c6c33d7aab09094a188bbdde39074f1c9c06ddab720f)
- [Versioning Release Note](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f61b28226e3157b748e8f9cbd1f8685325f191d97b4634346352d08536518b06d9244ec8cadfa6b7bcede4430e841eaa735db4c1fe2c823189d5113082528977175488750812ba993a08a9b98f3dd0596d13a2bad546fb1b9d10f897730c5a8721e6d8430f6a3ef212c584aa790c09b69833e6a8a1da6635993c14b66927fd835d)
- [FAQ](http://u.720life.cn/g/19f81165ca0412019ffde45bafddc8e584b912e0aba6653c3c56f1d6769289f9c3875440d54596b92a5d1e46d36c4673)
- [CodeSandbox Template](http://u.720life.cn/g/d27f7c08ac52c469a424f68173fd730e51a3c19641cf6d451f3025aa13872c0e4a2694234dbbe7720d961429f3045e25) for bug reports
- [Awesome Ant Design](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046404ec3b3936d51370b1d6dfee677f44394838cab39575a6301b73ad1dd5ea0ea9131c35bbea41504757be580ea201387)
- [Customize Theme](http://u.720life.cn/g/19f81165ca0412019ffde45bafddc8e5fb470d7bbb9674d7288276976ca2d3f79c4fff6f0d7f6b8f0af673e06fb6f3db)
- [How to Apply for Being A Collaborator](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6a1ace845411a9a31adb8e562deb907ad1d0d1e521c53556d717f547d287b9ff653b7ed1afde4a5517b45ab2f82cfa1e086c4de381ea7b48cfbec78e15524d93c4ddb91051e7a66f6275f86e1e1bbe9b9)

## ⌨️ Development

Use Gitpod, a free online dev environment for GitHub.

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/ant-design/ant-design)

Or clone locally:

```bash
$ git clone git@github.com:ant-design/ant-design.git
$ cd ant-design
$ npm install
$ npm start
```

Open your browser and visit http://127.0.0.1:8001 , see more at [Development](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6996e800524b092d98185c6c33d7aab09094a188bbdde39074f1c9c06ddab720f).

## 🤝 Contributing [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

Read our [contributing guide](http://u.720life.cn/g/19f81165ca0412019ffde45bafddc8e54e28761ae4ccb0e9e844722399829739620d6774af0e2a867ce1e0a108229a51) and let's build a better antd together.

We welcome all contributions. Please read our [CONTRIBUTING.md](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6f072607d2a276f49fbc3f88545a92abd33c196db41fe2158b3fa59afea195cc91a7c43b16f4a536e631176cedd15f886) first. You can submit any ideas as [pull requests](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6bd721d7ab332e46e0c3edbefdcf8b1a1) or as [GitHub issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6baf3154394d5e017b9e0a73dbe420521). If you'd like to improve code, check out the [Development Instructions](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6996e800524b092d98185c6c33d7aab09094a188bbdde39074f1c9c06ddab720f) and have a good time! :)

If you are a collaborator, please follow our [Pull Request principle](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6ad5a5f8a9aed56d224724f68cbf678fae5db687ad30a0ba156d4fb1a1ec55070) to create a Pull Request by [collaborator template](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c720367d5be3d9a9eebaaaacc01f8f6306b55b6159d756c631a38063ca1bd09f1ace557e55dac8f636f0285f4baaec6adfc68c8b0ad80758db1c021f5b51716543f88f9ce15e6c3ab9c4e7da22dbbfd).

[![Let's fund issues in this repository](https://issuehunt.io/static/embed/issuehunt-button-v1.svg)](https://issuehunt.io/repos/34526884)

## ❤️ Sponsors and Backers [![](https://opencollective.com/ant-design/tiers/sponsors/badge.svg?label=Sponsors&color=brightgreen)](https://opencollective.com/ant-design#support) [![](https://opencollective.com/ant-design/tiers/backers/badge.svg?label=Backers&color=brightgreen)](https://opencollective.com/ant-design#support)

[![](https://opencollective.com/ant-design/tiers/sponsors.svg?avatarHeight=36)](https://opencollective.com/ant-design#support)

[![](https://opencollective.com/ant-design/tiers/backers.svg?avatarHeight=36)](https://opencollective.com/ant-design#support)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed1770d5704aae1c1b2c2d5d055695ad36db26b7ccdb0d7be92ddd40e4a332b526bc963f7223ecfb810a259049ca9e26b)