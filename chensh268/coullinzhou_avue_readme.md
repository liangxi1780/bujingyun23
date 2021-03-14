 
   
   
   
 


#### 简介

Avue是基于[Vue.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a66c77cd0911e5527fb3fc591bfc25f5)和[element]https://github.com/ElemeFE/element 它的核心是数据驱动UI的思想，让我们从繁琐的crud开发中解脱出来，它的写法类似easyUI，但是写起来比easyui更容易，因为它是基础数据双向绑定以及其他vue的特性。同时不知局限于crud，它还有我们经常用的一些组件例如，表单，数据展示卡，人物展示卡等，更多的组件还在开发  

### avue2.x来了！！
avue2.x重磅来袭！与1.0.x版本截然不同！！  
不只是后台模板解决方案，更像是页面开发神器，积木拼装的概念，简单的拼装快速实现业务场景复杂的需求  
  
核心:数据驱动视图  
  
亮点:  
1.只需要配置简单的json属性，即可实现复杂的页面  
2.配置不同的属性，实现不同的控件效果和业务逻辑（需要一个上传图片的功能，配置属性为upload,和图片上传后台接口即可)  
3.配置字典接口，全局字典自动加载无需操心label和value值的对应
4.简单配置即可实现分步骤表单提交，多选项卡表单提交，等其他复杂的表单  
5.不需要写大量html和css，只需要一个json即可完成你的页面  
6.解放手写大量重复crud和form表单功能，只要维护一个json就好  
7.让你轻松完成工作，有更多的时间去泡妹子  
8.重点在form表单和crud表格  
avue-cli 2.x演示地址  
[演示地址](http://u.720life.cn/g/3cd20dad1e32aaf5ddf74faf1a78adb8c7335822ba012b77c3159f7bc9ea07a8)  

适合人群:  
1.常年撸后端，对前端页面有恐惧心里  
2.刚入门vue，需要写一些复杂的业务场景  
3.干着大量重复的crud，机械式劳动，浪费时间  
4.前端小白，没用过很多框架，没有很多经验  

[点击查看详情](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9a45ea68dd78dd93ab4ce0a12f91adcf04ed54ad7b8814501f2748c9dbd259d2 )

#### 百度云课程
 
   
 

- [B站视频](http://u.720life.cn/g/0b2e9c050c16e17e2de17da38fe221e14e891e7f464d808a8bfeaa8b64b73a972be6650bc19bffe47ced5004aa779743)
- [1.Avue修仙系列之基础环境的准备和课程介绍](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93e602f6d4008ad959dfca888a294abbca335f71160492ea82db3a54e85cd478a9)
- [2.Avue修仙系列之avue-crud组件type属性介绍](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93b4521f9e867a8e01f96744f07a45afd17a7a28301724043451643726ce2ceb0b5c8169624868b4cf6bdec29b1ee01851)
- [3.Avue修仙系列之avue-crud本地字典的使用方法](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93e9a2b8dd53fe055bff5527a3e31489da3a946b17d4f9cc3d95eff0ba773f1e5d)
- [4.Avue修仙系列之avue-crud后台接口字典的使用方法](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93e8358afebaeaf49f38c7739d1776fd0946ee39148d91f4269bc4875e78b14195)
- 未完待续

#### avue自定义第三方插件

[穿梭框](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9a45ea68dd78dd93ab4ce0a12f91adcf65b379b74028433a3dbaad5e1857f7cf2c5808499ef0ca8cd6ca0a393395fce8)  
[富文本编辑器](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9a45ea68dd78dd93ab4ce0a12f91adcfb82e8b33e1f00d45dbadba75feb55e47bb40a737d1b9ca0b420c634d3bf5745d)  

使用方式(以富文本编辑器为例)：  
* npm install avue-plugin-ueditor --save
* main.js导入import 'avue-plugin-ueditor/packages'
* 列的属性配置"component": "AvueUeditor" 你插件的全局名字即可


#### avue综合实际实例
- [crud综合例子](http://u.720life.cn/g/5b4e7201c2191e6d5e2846fe11b9b99bae55717c04ae944a4a90aedaa2b8856e405d43c3f891e1f28f2aeb01e198fcd7)
- [crud流程例子](http://u.720life.cn/g/e20548455f3a77105d0b7939b1d9449c8ebc401f1568d08b8b03e7ff62fa49da0b8ba2332ff1477f780e3e63992f91fb)
- [crud多级联动例子](http://u.720life.cn/g/e20548455f3a77105d0b7939b1d9449c4a82e116dbfba9fda21315b36ccb046ffb4051fdb8d9e230f0a1e467a2c94225)
- [crud动态切换](http://u.720life.cn/g/e20548455f3a77105d0b7939b1d9449c4e5fa5327d67f3124d1a69e883e8d935718d439d8075d25a1782e816ea8316a2)
- 未完待续

#### avue相关地址
欢迎加入QQ交流群，互相学习   
前端avue交流群：606410437  
后台微服务群：23754102   
服务端解决方案：[https://gitee.com/log4j/pig](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e003a98ff8124711bc8bb2a735eddd1c3)   
刚入门的前端小师妹博客:[https://my.oschina.net/u/3883702/](http://u.720life.cn/g/a88615b97db01a1ba3d626afe31cb1739185713aa056a5d69cd2692a52399bb0d78d14509a13bfaa81f26bf163090d4d)   
最近很多人反应不太会用crud快速开发组件，因此免费推出crud系列的讲解课程，详情请加QQ群

#### cli 1.x演示地址
- [演示地址](http://u.720life.cn/g/23bf3e5655695aeaa2cc01b597fc217960de9a3764dce81a5390516de0d399ff)

#### 技术文档
- [avue技术文档](http://u.720life.cn/g/ba0134f7488dc7089e9b70cb68034558f2cf4545b793f89ca7e40a3e74dd9343f555509efcf91247e4794f1a92432a66)

#### 官方网站
- [avue官方网站](http://u.720life.cn/g/0ab41158b362205dfed5842565baddd4)

#### 源码地址
- [码云地址:https://gitee.com/smallweigit/avue](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9a45ea68dd78dd93ab4ce0a12f91adcf597755959c1ecde8ac8b2591700d6b1d)
- [github地址：https://github.com/nmxiaowei/avue](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fa0560fb7036e10e12eca11f4b9b4c38adfe310c8f56be78ac45cacbda9ef82e)

#### 更新日志
本项目以更新到最新的vue-cli@3.0的脚手架，更多使用请去vue官方查看  
- [更新日志](./UPDATE.md)

### Avue
基于数据驱动视图的思想，根据json数据快速构建crud和form等组件  
依赖包:  
* axios：发送ajax数据用到的包
* element-ui：可视化UI组件
* 引入avue之前先引入上面这俩个包

#### CDN
```
 
  

#### npm
npm i @smallwei/avue --save

#### yarn
yarn add @samallwei/avue --save

```

#### 使用方式
```
import Element from 'element-ui'
import axios from 'axios'
import Avue from @smallwei/avue/lib/index.js
import @smallwei/avue/lib/theme-chalk/index.css

Vue.use(Element);
Vue.use(Avue,axios)

```

#### 功能结构
```
- 全局错误日志记录
- vuex持久化存储
- 主题色切换
- 锁屏
- SSR渲染页面
- 数据展示
- 登录/注销
 - 用户名登录
 - 验证码登录
- 权限验证
- 第三方网站嵌套
- CRUD(增删改查)
- FORM(动态生成)
- 阿里巴巴图标库(在线调用)
- 环境变量
- 表格树
- 引导页
- 数据持久化
- 剪切板
- 系统管理
 - 用户管理
 - 角色管理
 - 菜单管理
- 高级路由
 - 动态路由
 - 参数路由
- 更多功能开在开发
```

### 部分页面展示 （其他页面效果图在publich/cdn/imgages目录）

#### 登录页面
 

#### 炫彩主题
 


#### 开发
```bash
# 克隆项目
git clone https://gitee.com/smallweigit/avue.git

# 进入项目
cd avue

# 安装依赖
npm install --registry=https://registry.npm.taobao.org

# 启动服务
npm run serve

```


#### vue-ui启动
```bash
1.npm install -g @vue/cli 全局安装vue脚手架最新版  
2.vue --version 查看版本是否为3.x版本  
3.vue ui 运行管理工具，导入avue-cli项目  

```


#### 调试与发布
```bash
# 构建测试环境
npm run serve

# 构建生成环境
npm run build

```


#### 其它
```bash
# 代码检测
npm run lint

# 单元测试
npm run test:unit2
```

#### 友情链接
- [d2-admin](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046653cebc44e4d3b92f12d021137f15365ecdfa3550ecf9c31b5bf3f5e32f9aa90)

#### License
[MIT](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9a45ea68dd78dd93ab4ce0a12f91adcfb5874aa0eefb9381520c3bfb904862a34e6a764f9c2b7ff3923d0242b8cf8aef)

Copyright (c) 2017-present Smallwei



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e978ac1836426029742b0fb4687a9751f3099dda41156ec11e4f056c305730eddc3b8d8d0bbbae00e835e73be5e4755e8)