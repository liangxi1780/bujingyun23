
Jeewx-Boot 免费微信管家平台
==========

当前最新版本： 1.1.0（发布日期：20191205）

[![AUR](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg)](https://github.com/zhangdaiscott/jeewx-boot/blob/master/LICENSE)
[![](https://img.shields.io/badge/Author-JEECG团队-orange.svg)](http://www.jeewx.com)
[![](https://img.shields.io/badge/version-1.1-brightgreen.svg)](https://gitee.com/jeecg/jeewx-boot)



项目介绍
-----------------------------------
JeewxBoot是一款基于SpringBoot的开源微信管家系统，采用SpringBoot2.1.3 + Mybatis + Velocity 框架技术。支持微信公众号、微信小程序、微信第三方平台（扫描授权公众号）、抽奖活动等。JeewxBoot实现了系统权限管理、公众号管理、抽奖活动等基础功能，便于二次开发，可以快速搭建微信应用！
Jeewx-Boot采用插件开发机制，实现一个抽奖活动项目是一个独立的插件（对JAVA来讲就是一个JAR包），可以很方便的做插拔，最终打造像Discuz一样的插件生态圈。。


	  
功能清单
-----------------------------------

```
├─系统管理
│  ├─用户管理
│  ├─角色管理
│  ├─菜单管理
│  └─首页设置
│  └─项目管理（插件）
├─公众号运营
│  ├─基础配置
│  │  ├─公众号管理
│  │  ├─关注欢迎语
│  │  ├─未识别回复语
│  │  ├─关键字设置
│  │  ├─自定义菜单
│  │  ├─菜单支持小程序链接
│  │  ├─Oauth2.0链接机制
│  └─微信第三方平台
│  └─支持扫描授权公众号
│  ├─素材管理
│  │  ├─文本素材
│  │  ├─图文素材
│  │  ├─超强图文编辑器
│  │  ├─图文预览功能
│  ├─用户管理
│  │  ├─粉丝管理
│  │  ├─粉丝标签管理
│  │  ├─图文编辑器
│  │  ├─接受消息管理
│  │  ├─粉丝消息回复
│  │  ├─图文预览功能
│  ├─高级功能
│  │  ├─微信群发功能
│  │  ├─群发审核功能
│  │  ├─二维码管理
├─微信抽奖活动
│  ├─砸金蛋
│  ├─小程序官网（CMS模块）
│  ├─摇一摇（尚未开源）
│  ├─微信砍价（尚未开源）
│  ├─更多商业活动
├─高级功能（尚未开源）
│  ├─小程序商城
│  ├─竞选投票
│  ├─分销商城
│  ├─团购商城
│  ├─红包活动
│  ├─更多商业功能
│  ├─。。。
```




技术文档
-----------------------------------

* 技术官网 ：[www.jeewx.com](http://u.720life.cn/g/777ad498d3808edff841aa7bd3054dfde98a66dc2acf421b2dadef665a780beb)
* 演示地址 ：[http://demo.jeewx.com](http://u.720life.cn/g/4294e21550d4b34ffe22e85b28a80f700aa88f89b458bf727a600c8576fb7177) 【测试账号： jeewx/123456】
* QQ交流群 : 97460170
* 入门必读：http://doc.jeewx.com/1414959
* 开发文档：http://doc.jeewx.com
* 视频教程 ：[JeewxBoot入门视频教程](http://u.720life.cn/g/0b2e9c050c16e17e2de17da38fe221e14e891e7f464d808a8bfeaa8b64b73a9763ca50f5502c50bc91cc6f6366525a0d)
* 常见问题贴：[开发日常问题汇总](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb3235c7498b3747e0b953f7e153f50db9c743482c7d8c5e9c3159ce0b5ae6f4df6ff479a40cb56ce52b1042151a9cb8a710dbf42beebb89cb7e25ba5cfc61de4987b)


项目说明
-----------------------------------

| 项目名   |      中文名      |  备注 |
|----------|:-------------:|------:|
| jeewx-boot-start |  启动项目 |  |
| jeewx-boot-base-system |  系统用户管理模块 |  |
| jeewx-boot-module-weixin | 微信公众号管理 |     |	 
| jeewx-boot-module-api | 共通业务API接口 |     |	
| huodong/jeewx-boot-module-goldenegg |    砸金蛋活动   |    |


小程序端源码
-----------------------------------

* 小程序官网 ：https://gitee.com/jeecg/jeewx-app-cms
* 小程序商城(暂未开放) ：https://gitee.com/jeecg/weixin-app-shop




系统效果
----

##### 体验二维码
![github](https://static.oschina.net/uploads/img/201907/13101120_zUgL.jpg "jeewx521")
![github](https://static.oschina.net/uploads/img/201907/13100959_naiO.jpg "jeewx521")

##### PC端
![输入图片说明](https://static.oschina.net/uploads/img/201907/15141922_GIP8.png "在这里输入图片标题")
![github](https://static.oschina.net/uploads/img/201808/11172049_s7hH.png "jeecg")
![github](https://static.oschina.net/uploads/img/201808/11153109_73Aj.png "jeecg")
![输入图片说明](https://static.oschina.net/uploads/img/201807/26192231_JVRQ.png "在这里输入图片标题")


##### 手机端
![github](https://static.oschina.net/uploads/img/201808/11195358_bi9e.png "jeecg")







 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b6c319f23e63285734660131654aad2295bd47c2de916f452c129cb751efed83c154cb8092e69dbe73a41b67b5e6347)