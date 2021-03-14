 
     
         
     
 

# iView Admin

[![](https://img.shields.io/github/release/iview/iview-admin.svg)](https://github.com/iview/iview-admin/releases)
[![](https://img.shields.io/travis/iview/iview-admin.svg?style=flat-square)](https://travis-ci.org/iview/iview-admin)
[![vue](https://img.shields.io/badge/vue-2.5.10-brightgreen.svg?style=flat-square)](https://github.com/vuejs/vue)
[![iview ui](https://img.shields.io/badge/iview-3.0.0-brightgreen.svg?style=flat-square)](https://github.com/iview/iview)
[![npm](https://img.shields.io/npm/l/express.svg)]()

[更新日志](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464acd1bc69bca9dfde1b71ae150cc182cc0a955cc9601a6818dc0530991e4c9ba)

[使用文档](http://u.720life.cn/g/6ad9dbe2a8c4d70d8fb53a14cfcde12a67233e0da1068b2c57b74d21697e114c37321cef4b87d136c4738ddf55ee7379)

[在线访问](http://u.720life.cn/g/db4148208f38c52b0dc58375b7563f962dee7380da29032f75c9995e040666dd)

[简化版模板](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464acd1bc69bca9dfde1b71ae150cc182c82a60517e869b96d1cbc0e827c353f265a50895c433abf0cca20f867e814424b)

[教学视频(26课时)](http://u.720life.cn/g/6900aa436d7855810ebad430307e6f91ecc1e73b6385e6054f22f747da943f0f001a0f7505f630d8b15d9c1631174cdf6c6a8193767253ceb0a6d84711fdd89d)

`注：在线版本会在开发版本新小版本发布后更新到相应版本，所以如果想体验最新版本iview-admin，请clone完整项目代码到本地运行。`

## Install
```bush
// install dependencies
npm install
```
## Run
### Development
```bush
npm run dev
```
### Production(Build)
```bush
npm run build
```

## 简介
&emsp;&emsp;iView admin是基于Vue.js，搭配使用[iView](http://u.720life.cn/g/042b48c1b518af8039860c9df004b13cb855bd704dab6d9eda4b7866cab288c8) UI组件库形成的一套后台集成解决方案，由TalkingData前端可视化团队部分成员开发维护。iView admin遵守iView设计和开发约定，风格统一，设计考究，并且更多功能在不停开发中。
如果您想查看iview-admin的更新动态，您可以到[更新日志](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464acd1bc69bca9dfde1b71ae150cc182cc0a955cc9601a6818dc0530991e4c9ba)查看了解最新更新；如果您是新手，想快速入手iview-admin，您可以到[使用教程]https://github.com/iview/iview-admin/wiki

## 功能

- 登录/登出
- 权限管理
    - 列表过滤
    - 权限切换
- 多语言切换
- 组件
    - 富文本编辑器
    - Markdown编辑器
    - 城市级联
    - 图片预览编辑
    - 可拖拽列表
    - 文件上传
    - 数字渐变
    - split-pane
- 表单编辑
    - 文章发布
    - 工作流
- 表格
    - 可拖拽排序
    - 可编辑表格
        - 行内编辑
        - 单元格编辑
    - 可搜索表格
    - 表格导出数据
        - 导出为Csv文件
        - 导出为Xls文件
    - 表格转图片
- 错误页面
    - 403页面
    - 404页面
    - 500页面
- 高级路由
    - 动态路由
    - 带参页面
- 换肤
- 收缩侧边栏
- tag标签导航
- 面包屑导航
- 全屏/退出全屏
- 锁屏
- 消息中心
- 个人中心

## 文件结构
```shell
.
├── build  项目构建配置
├── config  开发相关配置
├── public  打包所需静态资源
└── src
    ├── api  AJAX请求
    └── assets  项目静态资源
        ├── icons  自定义图标资源
        └── images  图片资源
    ├── components  业务组件
    ├── config  项目运行配置
    ├── directive  自定义指令
    ├── libs  封装工具函数
    ├── locale  多语言文件
    ├── mock  mock模拟数据
    ├── router  路由配置
    ├── store  Vuex配置
    ├── view  页面文件
    └── tests  测试相关
```

## Links

- [TalkingData](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a6b05f598c3817e53335135bafff79d6)
- [iView](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c77dfb115f76a8da39c86e27313b7fe5)
- [Vue](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a66c77cd0911e5527fb3fc591bfc25f5)
- [Webpack](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467fcc54064697beb3b7b3df6e06eef298df4c1c58c8a6fda9268979495e98dbb2)

## 效果展示

- 响应式布局首页
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/home.gif)

- 标签导航
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/page-tags.gif)

- 权限管理
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/access.gif)

- 可拖拽列表
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/dragable-list.gif)

- 图片预览编辑
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/image-editor.gif)

- 文件上传
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/upload.gif)

- 数字渐变
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/count-to.gif)

- split-pane
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/split-pane.gif)

- 文章发布
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/article-publish.gif)

- 工作流
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/workflow.gif)

- 可拖拽表格
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/dragable-table.gif)

- 可编辑表格
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/editable-table.gif)

- 表格导出数据
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/exportable-table.gif)

- 表格转图片
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/table2image.gif)

- 错误页面
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/error-page.gif)

- 锁屏
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/locking.gif)

- 可收缩侧边栏
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/sidebarmenu.gif)

- 主题切换
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/theme.gif)

- 消息中心
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/message.gif)

### 💖💖 If you find this project helpful, maybe you can buy me a coffee. 💖💖
![image](https://github.com/iview/iview-admin/raw/dev/github-gif/code.png)


## License
[MIT](http://u.720life.cn/g/ba059582536a397f7c573b87c8bea647045b0ef049248233b6f76e909e70200fe7048b25e29c8bab79aeff32ea74556a)

Copyright (c) 2016-present, iView



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef192d166b5ef20caf8ce7d84feb31a4a54654ef3368464f20509eaac16a138b52bb4dfdd05ee755c4fd162de2868de7503cc7a5abea83d60a1b0cabb2bbe75e8)