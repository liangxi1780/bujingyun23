# youdiancms

####一、系统简介
1. 产品简介
友点企业网站管理系统（简称YouDianCMS）集电脑站、手机站、微信、APP、小程序于一体，共用空间，数据同步，是国内五站合一优秀企业建站解决方案。系统采用PHP开发，具有操作简单、功能强大、稳定性好、易扩展、安全性强、维护方便等特点，可帮您快速构建一个强大专业的企业网站。系统支持多语言、自定义模型、SEO优化、静态页、评论留言、购物车、在线支付、订单管理、三级分销、广告管理等企业网站基本功能。软件著作权登记号：2013SR028772

2. 产品优势
系统同时支持电脑网站、手机网站、微信网站、APP、小程序五站合一，数据同步！

3. 运行环境
（1）操作系统：跨操作系统平台，支持Windows、Linux等操作系统 
（2）软件环境：PHP5.3/5.4/5.5/5.6/7.0/7.1/7.2/7.3
（3）伪静态：伪静态规则存放在网站根目录下，主要有3个文件，分别用于不同的服务器环境：
web.config：用于iis7.0以上版本
.htaccess：用于Apache服务器、IIS6.0 + ISAPI_Rewrite3
httpd.ini：用于IIS6.0 + ISAPI_Rewrite2
IIS6.0必须安装ISAPI_Rewrite才支持伪静态组件，Apache和IIS7.0以后默认支持伪静态

4. 相关文档
官方网站：http://www.youdiancms.com
使用手册：http://use.youdiancms.com
标签手册：http://tag.youdiancms.com

####二、系统安装
1. 安装步骤
第一步：上传并解压
将程序压缩包上传到虚拟主机，登录虚拟主机管理后台解压；

第二步：开始安装
输入网址后，自动进入安装程序，按提示操作即可。

安装完毕：
后台管理地址：http://您的网址/index.php/admin
手机网站地址：http://您的网址/index.php/wap
如果你的服务器支持伪静态（Apache,IIS7.0或以上版本默认支持伪静态），则无需录入/index.php

2. 常见安装错误及其解决方案
错误信息：能正常安装，安装完成后，提示一下错误：
Fatal error: Allowed memory size of 8388608 bytes exhausted (tried to allocate 775920 bytes)
原因：这是由于php设置的最大使用内存值太低（默认为8M或12M）造成的，建议修改成128M
解决方案：修改php.ini（推荐），打开php.ini，ctrl+f 找到memory_limit，修改后面的值；memory_limit = 12M，建议修改为128M：memory_limit = 128M，修改完成后，重启Web服务器即可生效
你可以运行http://你的网址/probe.php来查看服务配置参数




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecebec23da90df2953058596ffa2a71eb4acb50dd0af819facf51ffd032621be6141ca13015cf800b2ee7f9a982824a23)