# DBErp

#### 介绍
DBErp 系统，是北京珑大钜商科技有限公司 基于 Zendframework 3 + doctrine 2 开发的一套进销存系统。

#### 本系统运行环境要求：

- 服务器系统：Linux（推荐）、Unix、Windows
- Web服务软件：Apache（推荐）、Nginx
- PHP版本：7.1及以上版本
- MySQL版本：5.7及以上版本


Web服务软件要求开启重写（Rewrite），使用Apache默认已经开启重写功能


#### PHP需要开启的扩展：
1. Curl
1. fileinfo
1. openssl
1. PDO

#### DBErp系统安装过程：
*从码云下载的程序在本地需要运行 [composer](http://u.720life.cn/g/d5f1cf35647bbcd870aa9cc0452a2958e2335b0b7c0efe9734806c0884dd1bac) update，可以在 https://bbs.dbshop.net/forum.php?mod=viewthread&tid=2191 下载完整系统包*
1. 使用数据库管理软件，建立DBErp需要的数据库，然后将sql目录内的dberp.sql导入数据库。
1. 在config/autoload/local.php中设置数据库连接，主要设置 40、41、42、43 行。
1. 删除 data/cache 目录下的两个php文件。
1. 通过ip或者域名访问即可，访问地址是 域名(ip)/public 如果你使用域名，请在设置域名时，直接将域名指向public目录，这样就可以直接通过域名访问，而不需要在后面加上public目录了。
1. 默认登录账户是 admin 密码是 111111

*特别说明：如果您在没有设置好数据库连接信息的情况下，通过浏览器访问了系统，那么在设置好连接信息后，请重复操作 3*

#### DBErp系统支持网址：

官方网站：https://www.dberp.com.cn 
官方论坛：https://bbs.dbshop.net 
演示DEMO：http://demo.dberp.com.cn


#### DBErp系统联系方式：
电子邮箱：support@dbshop.net 
QQ交流群：737830419

![QQ交流群扫码加入](https://images.gitee.com/uploads/images/2019/0629/174642_f5bf58c1_1001162.jpeg "TIM图片20190629174609.jpg")


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee5c554bbc7bca934fa9235309b67aa19e6a35fbd05546e41b86710460bf7d3e965d22eaf7257a34191ac4edbcba780f8)