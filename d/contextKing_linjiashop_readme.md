 # 前言
[![Spring Boot](https://img.shields.io/badge/spring--boot-2.1.1.1.RELEASE-brightgreen)](https://github.com/spring-projects/spring-boot)
[![vue](https://img.shields.io/badge/vue-2.6.10-brightgreen.svg)](https://github.com/vuejs/vue)
[![element-ui](https://img.shields.io/badge/element--ui-2.11.0-brightgreen.svg)](https://github.com/ElemeFE/element)
[![Vant](https://img.shields.io/badge/vant-2.2.0-brightgreen.svg)](https://youzan.github.io/vant/#/zh-CN/intro)
[![Vant-weapp](https://img.shields.io/badge/vant--weapp-1.0.1-brightgreen)](https://youzan.github.io/vant-weapp/#/intro)
[![Flutter](https://img.shields.io/badge/Flutter-1.9.6-brightgreen)](https://flutter.dev/)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/enilu/linjiashop/blob/master/LICENSE)
[![Gitee stars](https://gitee.com/microapp/linjiashop/badge/star.svg?theme=social)](https://gitee.com/microapp/linjiashop)
[![GitHub stars](https://img.shields.io/github/stars/microapp-store/linjiashop.svg?style=social&label=Stars)](https://github.com/microapp-store/linjiashop)
 


- linjiashop 是一个基于[Spring Boot]https://spring.io/projects/spring-boot/)和[Vue.js]https://cn.vuejs.org)的web商城系统
- linjiashop 包含了商城的后台管理系统,手机h5，小程序版本
- linjiashop 包含了app版本（基于flutter) 仓库地址[gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3a65ba5e2202419c97ace9d785451e094540e8b05b9b360d7649d6a7062a36591b3872a2b9a6a49a6e79e35c21a4114cea8feb97df74adbf7dcede9e91cace62178345c223065e34d4e3198c3eb1f97a5de020f4592419a59fa8889703d35788)  
 
## 演示
- 手机版本：[http://linjiashop.microapp.store](http://u.720life.cn/g/ac37ce79e617605327eb453fb27eb3db634aa99a7eb0376f27f9eeac2b7cf305)  
- 后台管理：[http://linjiashop-admin.microapp.store](http://u.720life.cn/g/ac37ce79e617605327eb453fb27eb3dbc17be3b06dc72a47999f03e66d818e61e92952f0bab79ac4a8812776fcc2dfb6) 
- 公众号演示：关注公众号“外滩一号店"进行体验，或者扫描下面二维码关注

    ![外滩一号店](https://gitee.com/microapp/linjiashop/raw/master/doc/img/online/wt1hd.jpg)

- [开发教程视频](http://u.720life.cn/g/c06035f1d070842c2f9dbe6b055163a0c4293905e5be90e8f510fab19a04555af2f97d1a02a4d091068f220d31d597931b2f837a779afd321f7228457d115514) 
## 功能模块
linjiashop包含了后台管理功能和手机端商城业务功能
- 基础模块
    - 部门管理
    - 用户管理
    - 角色管理
    - 菜单管理
    - 权限分配
    - 参数管理
    - 数据字典管理
    - 定时任务管理
    - 操作日志
    - 登录日志
    - cms内容管理
    - 消息管理：配置消息模板，发送短信，邮件消息
    - 基于idea插件的代码生成
- 商城功能
    - 会员管理
    - 商品类别
    - 商品管理
    - 订单管理
    - 购物车
    - banner管理
    - 收藏列表
- 手机端
    -完整的商城购物功能        

## 运行效果图
_商品素材取自小米商城_
### 手机端H5
![手机端](doc/img/mobile.gif)

### IOS
 
 
 
  
 
  
 
 
 
  
 
  
 
 
 
  
 
  
 
 

### Android
![效果](doc/img/app/mobile.gif)

### 后台管理
![后台管理](doc/img/admin.gif)

## 技术选型
- 核心框架：Spring Boot
- 数据库层：Spring data jpa
- 数据库连接池：Druid
- 缓存：Ehcache
- 前端：后台管理基于[element](http://u.720life.cn/g/99b90101e0edb43e4fb6c26272a617e6d36457c3d71617c4b00b10d9d1e2a83e83dcf418449297b7cebc5ac682db2831b7abd7c936528dc59859305c7f432fd0c1b770c5edd64cb785af36775a21dac5147916d43fabd833aef7d3afa7c5840d08b0ba16ee351309c7d0f627fbab1dd9) 


## 目录说明
- linjiashop-admin PC端后台管理的前端网页
- linjiashop-admin-api PC端后台管理的api服务
- linjiashop-mobile 手机商城的前端网页
- linjiashop-mobile-api 移动端商城的api服务（h5,小程序，app都用改api服务作为后台接口）
- linjiasho-wxapp 微信小程序商城
- linjiashop-core 基础模块，包括工具类，dao，service，bean等内容
- linjiashop-generator 代码生成模块,根据实体生成dao,service,后台管理的controller和页面,配合IDEA 代码生成插件[webflash-generator]https://plugins.jetbrains.com/plugin/12648-webflash-generator使用效果更好，使用前请仔细阅读该[文档]http://enilu.gitee.io/web-flash/ecosystem/code-generator.html


## 快速开始
- 克隆本项目
- 导入idea或者eclipse
- 确保开发工具下载并安装了lombok插件，另外由于lombok有版本差异，如果出现问题，可以更新maven以来中lombok的版本来解决
- 创建数据库：linjiashop
     ```sql
    CREATE DATABASE IF NOT EXISTS linjiashop DEFAULT CHARSET utf8 COLLATE utf8_general_ci; 
    CREATE USER 'linjiashop'@'%' IDENTIFIED BY 'linjiashop191028';
    GRANT ALL privileges ON linjiashop.* TO 'linjiashop'@'%';
    flush privileges;
    ```     
- 下载项目测试数据的图片：链接：[https://pan.baidu.com/s/1V1QTSLspuDRuwI7H9TjcOA](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9388b8e9f64a606a15c11557e65103984f8b9523432357a2ee2b80ce792bae92bf)  提取码：dyj6 ，将图片存放到t_sys_cfg表中system.file.upload.path配置的目录下(注意该目录未绝对路径，该目录可以通过“系统管理”-“参数管理”进行配置)
- 启动后台管理
    - 启动后台管理api服务:linjiashop-admin-api
        - 修改linjiashop-admin-api中数据库连接配置
            ```properties
            ## 首次启动需要设置下列配置项设置为create，以便系统可以自动创建表并导入./import.sql测试数据文件
            ## 如果下面配置无法自动建表并导入测试数据文件；则可以手动初始化数据库，手动使用的初始化文件文件位于：doc/database.sql
            spring.jpa.hibernate.ddl-auto=create
            ```                    
        - 启动linjiashop-admin-api主类：cn.enilu.flash.api.AdminApiApplication，访问http://localhost:8082/swagger-ui.html ， 保证api服务启动成功
    - 启动后台管理的前端界面:linjiashop-admin
        - 运行 npm install --registry=https://registry.npm.taobao.org
        - 运行npm run dev
        - 启动成功后访问 http://localhost:9528 ,登录，用户名密码:admin/admin 
- 启动手机端商城
    - 启动手商城的api服务:linjiashop-mobile-api   
        - 修改linjiashop-mobile-api中数据库连接欸配置
        - 启动linjiashop-mobile-api主类：cn.enilu.flash.MobileApiApplication,访问http://localhost:8081/swagger-ui.html ， 保证api服务启动成功
    - 启动手机商城的前端:linjiashop-mobile
        - 运行 npm install --registry=https://registry.npm.taobao.org
        - 运行npm run dev
        - 启动成功后访问 http://localhost:8080/#/index
- 微信小程序开发
    - 首先启动后台api服务，和h5公用一个后台服务，即：linjiashop-mobile-api
    - 进入linjiashop-wxapp目录
        - 运行  npm install --registry=https://registry.npm.taobao.org
        - 运行npm run dev
        - 启动微信开发工具导入linjiashop-wxapp/dist/wx 目录即可预览小程序
 
## 技术交流
- 关注公众号：嗨客帝国，点击对应的项目菜单进群交流。

![公众号二维码](doc/img/haike.jpg)

## 在线文档
- 项目文档：[http://microapp.gitee.io/linjiashop](http://u.720life.cn/g/c06035f1d070842c2f9dbe6b055163a0c4293905e5be90e8f510fab19a04555acfbb6844e3063fc956e0b1a2985e37c6) 
- [商业支持](http://u.720life.cn/g/c06035f1d070842c2f9dbe6b055163a0c4293905e5be90e8f510fab19a04555a5a47f35b83d76f0cda0f0a8eb10ce86317c28e59f56cb87845c1114f7f630137) 
- 该项目克隆并扩展自[web-flash]https://github.com/enilu/web-flash,所以开发的时候多看看web-flash的[在线文档]http://enilu.gitee.io/web-flash
- 该项目手机端linjiashop-mobile使用有赞Vant组件库，开发过程可以参考Vant的[在线文档](http://u.720life.cn/g/36797055cd4afe462930655519827aa46b6f7723127dbe0a5d65cddef27e6a585e2a0fa1013c1482b0a64f8cd1d96cf6) 
- 该项目微信小程序使用mpvue+vant-weapp，开发过程请参考相关文档：[mpvue文档]http://mpvue.com/,[vant-weapp文档]https://youzan.github.io/vant-weapp/#/intro
- 该项目的业务功能和部分功能代码参考复用了[litemall]https://github.com/linlinjava/litemall，感谢[linlinjava]https://github.com/linlinjava
- [视频教程](http://u.720life.cn/g/c06035f1d070842c2f9dbe6b055163a0c4293905e5be90e8f510fab19a04555af2f97d1a02a4d091068f220d31d597931b2f837a779afd321f7228457d115514) 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)