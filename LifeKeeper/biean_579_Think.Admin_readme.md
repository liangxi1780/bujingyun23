ThinkAdmin for PHP
--
## 大道至简 · 悟在天成

* ThinkAdmin 是一个基于 Thinkphp 5.1.x 开发的后台管理系统，集成后台系统常用功能。
* 项目安装及二次开发请参考 ThinkPHP 官方文档及下面的服务环境说明，数据库 sql 文件存放于项目根目录下。
>* 注意：项目测试请另行搭建环境并创建数据库（数据库配置 config/database.php）, 切勿直接使用测试环境数据！
>* 如果系统提示“测试系统禁止操作等字样”，可以修改项目路由配置（route/route.php）, 清空里面的路由记录。
>* 当前版本使用 ThinkPHP 5.1.x 版本，对PHP版本要求不低于php5.6，具体请查阅ThinkPHP官方文档。


Documentation
--
认真看看文档可能会对你的开发有所帮助哦！

文档地址：[ThinkAdmin 开发文档](http://u.720life.cn/g/ba0134f7488dc7089e9b70cb680345588bca47ae1a02989a67a4c150c0b08d32f0c19a94e142fe0b9901c1e79b27b19b4a11a032e512237ebe5986f99debdc60)


PHP开发技术交流（QQ群 513350915）

[![PHP微信开发群 (SDK)](http://pub.idqqimg.com/wpa/images/group.png)](http://shang.qq.com/wpa/qunwpa?idkey=ae25cf789dafbef62e50a980ffc31242f150bc61a61164458216dd98c411832a) 


Repositorie
--
 ThinkAdmin 为开源项目，允许把它用于任何地方，不受任何约束，欢迎 fork 项目。
* GitHub 托管地址：https://github.com/zoujingli/ThinkAdmin
* Gitee  托管地址：https://gitee.com/zoujingli/Think.Admin

对于新版本的微信模块使用的是授权模式，需要用到 ThinkService 项目。
* GitHub 托管地址：https://github.com/zoujingli/ThinkService
* Gitee  托管地址：https://gitee.com/zoujingli/ThinkService

其安装与 ThinkAdmin 相似，这里就不多说了。具体可以参见微信开放平台官网
https://open.weixin.qq.com ，ThinkService 后台具体可以配置对应参数。

ThinkAdmin 与 ThinkService 对接是通过 WebService 通信的，因此运行环境需要安装 Soap 模块支持。


Module
--
* 简易`RBAC`权限管理（用户、权限、节点、菜单控制）
* 自建秒传文件上载组件（本地存储、七牛云存储，阿里云OSS存储）
* 基站数据服务组件（唯一随机序号、表单更新）
* `Http`服务组件（原生`CURL`封装，兼容PHP多版本）
* 微信公众号服务组件（基于[WeChatDeveloper](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304623d5890c2bd604e4e7fc1bc0f0f2ab125c6a4b771485f1466ee93033331d3b13)，微信网页授权获取用户信息、已关注粉丝管理、自定义菜单管理等等）
* 微信商户支付服务组件（基于[WeChatDeveloper](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304623d5890c2bd604e4e7fc1bc0f0f2ab125c6a4b771485f1466ee93033331d3b13)，支持JSAPI支付、扫码模式一支付、扫码模式二支付）
* 更多组件开发中...


Environment
---
>1. PHP 版本不低于 PHP5.6，推荐使用 PHP7 以达到最优效果；
>2. 需开启 PATHINFO，不再支持 ThinkPHP 的 URL 兼容模式运行（源于如何优雅的展示）。

* Apache

```xml
 
  Options +FollowSymlinks -Multiviews
  RewriteEngine On
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteRule ^(.*)$ index.php/$1 [QSA,PT,L]
 
```

* Nginx

```
server {
	listen 80;
	server_name wealth.demo.cuci.cc;
	root /home/wwwroot/ThinkAdmin;
	index index.php index.html index.htm;
	
	add_header X-Powered-Host $hostname;
	fastcgi_hide_header X-Powered-By;
	
	if (!-e $request_filename) {
		rewrite  ^/(.+?\.php)/?(.*)$  /$1/$2  last;
		rewrite  ^/(.*)$  /index.php/$1  last;
	}
	
	location ~ \.php($|/){
		fastcgi_index   index.php;
		fastcgi_pass    127.0.0.1:9000;
		include         fastcgi_params;
		set $real_script_name $fastcgi_script_name;
		if ($real_script_name ~ "^(.+?\.php)(/.+)$") {
			set $real_script_name $1;
		}
		fastcgi_split_path_info ^(.+?\.php)(/.*)$;
		fastcgi_param   PATH_INFO               $fastcgi_path_info;
		fastcgi_param   SCRIPT_NAME             $real_script_name;
		fastcgi_param   SCRIPT_FILENAME         $document_root$real_script_name;
		fastcgi_param   PHP_VALUE               open_basedir=$document_root:/tmp/:/proc/;
		access_log      /home/wwwlog/domain_access.log    access;
		error_log       /home/wwwlog/domain_error.log     error;
	}
	
	location ~ .*\.(gif|jpg|jpeg|png|bmp|swf)$ {
		access_log  off;
		error_log   off;
		expires     30d;
	}
	
	location ~ .*\.(js|css)?$ {
		access_log   off;
		error_log    off;
		expires      12h;
	}
}
```

Copyright
--
* ThinkAdmin 基于`MIT`协议发布，任何人可以用在任何地方，不受约束
* ThinkAdmin 部分代码来自互联网，若有异议，可以联系作者进行删除


Sponsor
--
![赞助](http://zoujingli.oschina.io/static/pay.png)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8a380ab4cedd16ce2346496653a94dc00c207d4a0184b38f21b2ba6b29e0bab1791c0f979b7288e9ddd403a32ce6aa15)