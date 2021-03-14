# Project: STAR BEAT!

[English](README-en.md)

Tongfang Hackintosh Utility 2.0, 全新的同方模具笔记本黑苹果工具箱。

## 功能简介

- 跨平台的键盘灯设置功能 (支持 Windows, macOS, Linux)
- 管理、更新、定制 OpenCore 配置文件
- 一键修复睡眠、开启 HiDPI 等
- 相比 v1 更友好的用户界面
- 多语言国际化支持

> Tips: 键盘灯控制功能仅适用于搭载了 ITE Device 8291, **版本 0.02** 的电脑. 如果你有 ITE Device 8291 设备，但 **版本为 0.03**, 请使用此工具： [AUCC](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304622e6e24aa74b6ecebaa1ea691110aea738af39626499316672e85bae38b0ed1071cf494d625d34f03428251b322adcdf).

## 下载

可以在 [Release](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467deaddf464cbf54f653cea8aad5d28575530c5320cec46c2ea331a0cea5864ee52a46057531772025e4a7afea03f0ad5) 页面下载。

## 构建

```bash
# ------ clone repo ------
git clone https://github.com/kirainmoe/project-starbeat starbeat
cd starbeat

# ------ start a development server ------
cd starbeat-core && yarn install
yarn start                             # will run webpack-dev-server on localhost:3000
cd ..
cd starbeat-client && yarn install
yarn start                             # will launch electron

# ------- pack an executable file -------
# build front-end
cd starbeat-core && yarn build
cd ..
cp -r starbeat-core/build starbeat-client/build
cd starbeat-client
yarn pack:macos
```

## 截图

 

   

   

## 技术栈

- Node.js
- electron
- React
- React Router
- node-hid

## 贡献

Feel free.

## 许可协议

Tongfang Hackintosh Utility (Project: STAR BEAT!) 基于 MIT 协议开源。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3f68ad7c153ea48338134edb3407d07247a9108a68a314464beb865170415701e411374bb969cc6681b51f88ccc545d3)