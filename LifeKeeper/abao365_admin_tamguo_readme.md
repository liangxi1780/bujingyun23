# tamguo 題庫

![logo](https://www.tamguo.com/files/book/201812/1065126653186768898/logo_731bc32.png "logo")

# 简介

`探果网`（简称tamguo）是基于java开发的在线题库系统，包括

 1. [在线访问][1]
 2. [后台运营][2]
 3. [会员中心][3]
 4. [书籍中心][4]

  [1]: http://www.tamguo.com
  [2]: http://admin.tamguo.com
  [3]: http://member.tamguo.com
  [4]: http://book.tamguo.com

- 管理员账号：system 密码：123456

QQ群：937899574



松耦合、高可用、可靠一直是软件工程的设计目标，探果网在这些方面还有很长的路要走，期待我们能手牵手一起走向未来。

> ### 期望
> 作者每天会把当天需要做的事情列出一个清单，给这周或者这个月立下一个flag。但是这中间发现了一些问题，事情永远也做不完，只会越做越多。

探果网期望可以使用java开发一套完整的互联网项目，分享互联网在技术、运营上的经验和知识。


# 系统部署图

# 项目结构

![探果网项目结构](https://www.tamguo.com/files/book/201812/1077070399566454786/20181225135556.png "探果网项目结构")

1. `tamguo-common` 一些基础的工具类包
2. `tamguo-modules-core` 依赖`tamguo-common`，主要是核心业务包，包括数据处理，文件处理，邮件处理，短信处理等等。
3. `tamguo-bms` 书籍系统[https://books.tamguo.com](http://u.720life.cn/g/d96b1ac4af53d8525901ef0af70140abb4ac15d286fbae236a45afda75c5ba16 "https://books.tamguo.com"),书籍系统展现层
4. `tamguo-mms`会员中心[https://member.tamguo.com](http://u.720life.cn/g/0067557f8d371cee675b04e5e94db3a38be0c4bd1fdaab6fa2c835aa1c74e8c9 "https://member.tamguo.com")
5. `tamguo-oms`后台管理系统[https://admin.tamguo.com](http://u.720life.cn/g/0067557f8d371cee675b04e5e94db3a38be0c4bd1fdaab6fa2c835aa1c74e8c9 "https://admin.tamguo.com")
6. `tamguo-crawler`爬虫程序，单独项目运行

# 数据库脚本

在`tamguo db`目录下


> ### 捐赠 
> 感谢你们的支持！






 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee0f13c4a813a559cff38b6a4c48316f578a137ee810fec64f29aeb82cf3df83228ebf33d1dbd266d15a9ce84aa2ab56f)