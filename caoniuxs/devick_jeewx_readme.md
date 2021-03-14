JeeWx 微信管家平台，简称“捷微”.
===============
  （是一款免费开源的JAVA微信公众账号开发平台）
===============
当前最新版本： 2.4.2（发布日期：20160912）

![github](http://img.blog.csdn.net/20140706133601296?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvemhhbmdkYWlzY290dA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
 平台介绍：

一、简介
-----------------------------------
Jeewx是一个开源、免费的微信管家系统，采用JAVA语言基于Jeecg框架实现，支持微信公众号，支持微信企业号。Jeewx实现了微信系统的基础功能，便于用户二次开发。Jeewx采用微服务框架，插件开发模式，JEEWX已推插件“微信企业号”。
【更多插件敬请期待：微信公众号、微信企业号、支付服务窗、QQ公众号、微博等】

二、主要特性
-----------------------------------
* 	1、JEEWX基于快速开发平台jeecg 3.4.4 版本开发，采用Springmvc+Hibernate+Bootstrap+Velicity等主流架构技术
*   2、支持企业快速开发，完善的用户组织机构，报表，强大的代码生成器，有效的提高开发效率
*   3、开源免费，jeewx遵循Apache2开源协议。
*   4、支持微信公众号管理（针对：微信公众订阅号、微信公众号服务号）
*   5、支持微信企业号管理（针对：微信企业号）
*   6、详细的二次开发文档，并不断更新增加相关开发案例提供学习参考
*   9、采用微服务架构Jeecg-p3，支持插件化开发，更易于集成


三、系统主要功能
-----------------------------------

【模块一：微信公众号】
-----------------------------------
*   1，微信接口认证
*   2，菜单自定义
*   3，文本管理和回复
*   4，关注欢迎语
*   5，关键字管理
*   6，文本模板管理
*   7，图文模板管理
*   8，账号管理
*   9，用户管理
*   10，角色管理
*   11，菜单管理
*   12, 多用户多公众号
*   13，微信大转盘
*   14，微信刮刮乐
*   15，微信CMS
*   16，自定义接口回复
*   17，翻译
*   18，天气
*   21, author2.0链接
*   22, 微信插件机制
*   23, 用户消息
*   24, 微信第三方平台（全网发布）
*   25, 支持微信企业号(微信企业号管理平台)


【模块二：微信企业号】
-----------------------------------
*   1，微信企业号管理
*   2，微信应用管理
*   3，素材管理：文本素材
*   4，素材管理：图文素材
*   5，菜单管理
*   6，通讯录管理
*   7，用户管理
*   8，关键字管理
*   9，关注回复管理
    源码下载地址：http://yun.jeecg.org

四、开发环境
-----------------------------------
  eclipse + maven + jdk7 + tomcat6 + mysql_5.0.37 （注意：不支持jdk8）
  如果不熟悉maven可以下载非maven版本: [更多版本下载地址](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb3235c7498b3747e0b953f7e153f50db9c743482c7d8c5e9c3159ce0b5ae6f4df6ff7ac380f61f0699dfbf5c265374a5c24423919f02a0ed2109054673ce54d8f67a)

五、系统安装
-----------------------------------
* 	1、将项目采用maven方式导入eclipse中，通过maven下载项目依赖。
* 	2、采用Mysql手工创建数据库jeewx 采用UTF-8编码，执行JEEWX数据初始化SQL脚本 ：doc/db/jeewx-mysql.sql
* 	3、采用maven方式启动项目，首次在浏览器中访问 http://localhost:8080/jeewx/，默认admin登录，一个账号只能配置一个微信公众账号。
* 	4、微信域名配置（重要）
* 	   修改：src/main/resources/sysConfig.properties
* 	   参数：domain={http://localhost:8080/jeewx/}
* 	5、服务器配置      
        URL:   http://*地址*/jeewx/wechatController.do?wechat 
        Token:  jeecg 
*   6. [开发环境搭建入门](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb3235c7498b3747e0b953f7e153f50db9c743482c7d8c5e9c3159ce0b5ae6f4df6ff58b853408a0b622e2a77eded54b44378b6670fa9b72eb5079491aaaf387ef411) 
*   7. Jeewx依赖本地Maven仓库下载 (http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d08b36d58a29f0bb52a8540881388913694e2294f920fb7c517213a1182defc46) 

六、技术交流
-----------------------------------
* 	论 坛:  www.jeecg.org
* 	QQ 群:  ④289709451、③175449166(满)、②129190229(满)、①287090836(满)
* 	官 网:  www.jeewx.com
* 	邮 箱： jeecg@sina.com


七、技术文档
-----------------------------------
* [JEEWX 系统操作手册](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a47ce8905daa5af1296d2963974eb062f3b39c01b15e2888a5f5090f2f4ff4cd0ef0203b3c2cc6c7cbb9dc405949b814fa)
* [JEEWX 开发环境搭建入门](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a47ce8905daa5af1296d2963974eb062f3b39c01b15e2888a5f5090f2f4ff4cd0e5631a64a9c7f1f5fa7e1c6689eab364d)
* [JEEWX 开发入门视频](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb3235c7498b3747e0b953f7e153f50db9c743482c7d8c5e9c3159ce0b5ae6f4df6ffae0d019111a675f87ff925553943b4e3cec7eba8d2caba6f45cbed978a07fddc)
* [JEEWX 入门常见问题](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb3235c7498b3747e0b953f7e153f50db9c743482c7d8c5e9c3159ce0b5ae6f4df6ff3767c29bc91195c4e5d99ade4a1568be506c0cb30486ae37aa422c211b8f197d)
* JEECG 应用插件下载中心：[http://yun.jeecg.org](http://u.720life.cn/g/93688df96c7f4921cee16d94aac01921005b7ff953bc6c28311bbba9e345070b)

八、在线体验
-----------------------------------
*   在线演示: [http://www.jeewx.com/jeewx](http://u.720life.cn/g/777ad498d3808edff841aa7bd3054dfd6a68e10a80de7a0f5034db0361312be2)
*   体验账号：ceshi/123456 (可注册)

    官方公众号："JEECG"  "H5互动汇"
![github](http://img.blog.csdn.net/20160323155143399?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323154916164?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")


系统截图 
-----------------------------------
![github](http://img.blog.csdn.net/20160908175834009?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160822173828381?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160822173833177?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323152508827?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323153059001?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323153104923?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323153117501?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323153122251?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eda5032162d0fd21c41f2eb52b0cfd771639b19f33c457be48274bba1ac6a07da93f86ee05149da9219f9f558ef9414f7)