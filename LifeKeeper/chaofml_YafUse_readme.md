# YafUse - I Use Yaf!
Yaf 地址:https://github.com/laruence/php-yaf 请针对自己的php 版本进行安装,注意服务器url路由规则

## Why I Do
自己在项目中用了yaf，用了很多外部类，感觉需要优化地方很多，逐渐改进。这里只是一个简单的例子，可以用于yaf快速上手，我的修改有些借鉴别人的思路，想要用好希望多看鸟哥的官方文档及源码.(http://u.720life.cn/g/5bb3e5989797a86a9bec41dfc8c80787a79a75bb8d8bf56914ae0f733e2408a8)

## What I Do
- layout布局实现
- bootstrap 后台管理界面
- PDO数据库操作类(Mysql数据主从实现)
- 简单的增删改查实现
- 错误捕捉显示及日志记录
- 数据库连接可以自主选择或者自己写个连接和操作类
- 目前这个demo里面使用的是两个连接实现了读写分类操作,如果mysql使用了proxy实现的,建议还是用自己写的数据库操作类进行实现

## Requirement
- Nginx
- PHP 5.2 +
- PHP Yet another Framework
- Mysql

## How To Use

### Rewrite rules

#### Apache

```conf
#.htaccess
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule .* index.php
```

#### Nginx (nginx.conf已有示例)

```
server {
  listen ****;
  server_name  domain.com;
  root   document_root;
  index  index.php index.html index.htm;
 
  location / {
		try_files $uri $uri/ /index.php?$args;
  }

}
```
### Database
使用shidatabase.sql,简单的例子，只有一个数据表(增删改查实现)

### app.ini
详细见具体文件

### ErrorAction
报错开启关闭在ini中有配置，可以记录为日志文件，需要有写权限。在Error.php实现。

### user name and pws
admin / 12345678



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8770c4884fa18935a7212900b6e91b5ae27eaee3ba4eab8e5757f48aa7c82d37440695785d42e21ef036406aa48007f2)