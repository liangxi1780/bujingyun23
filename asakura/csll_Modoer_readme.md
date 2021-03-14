#Modoer点评系统 
	Modoer点评系统是有[http://www.modoer.com 陌风软件]出品，由PHP+MYSQL进行开发而成。
	本系统是一款专业的点评网站系统，多种行业的点评，可以自由调控点评项目，类型。
	Web2.0的建站方式，支持手机Web建站，网站会员能让快速上手。

#安装说明
	最佳安装环境 Linux + Apache 2.x + MYSQL 5.x + PHP 5.3.x
	最低安装环境 Linux/Win + Apache/IIS + PHP 5.3.3 + MYSQL 5.0
	请打开PHP.INI的短标签(short_open_tag=On)，GD库，curl库，iconv库
	请将 upload 文件夹内的文件上传到您的ftp空间，执行根目录下的install.php进行安装(http://www.你的网站.com/install.php)
	如有安装问题，请在论坛板块发帖。

#配置修改
	源码内部默认关闭了使用本地配置文件和DEBUG功能，如需要在本地进行调试开发，具体文件位置在 core\define.php，修改代码
	define('IN_LOCAL', TRUE);
	define('DEBUG', TRUE);	
	TRUE 都修改为 FALSE 即可在，程序会加载本地配置文件 data/config_local.php，同时在所有页面底部出现debug信息

#权限说明
	data文件夹和uplaods文件夹，包括其中的子文件夹和文件都必须具有读，写，修改，删除的权限，Linux下必须保持 0777 的权限
	其他文件夹和文件则为标准的权限
	如果需要使用在线模板编辑功能，则必须要使 templates 文件夹以及下属的文件夹，文件具有有读写修改删除的权限，Linux下必须保持0777的权限

#程序说明
	后台入口文件是admin.php，登录地址：http://www.你的网站.com/admin.php
	后台入口文件名可以自由更改，Modoer前后和后台帐号是分开的，安装时注册的帐号为后台帐号。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e308c526eba4623866183b8f6edcc9d6d29f0b225f4d4bcd44da083acc23daf2635da09e78e4501b80bc3b4159df35134)