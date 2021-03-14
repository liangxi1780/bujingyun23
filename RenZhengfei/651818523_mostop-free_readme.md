# MOSTOP-FREE 免费版

### DEMO 示例
##### http://admin.demo.mostop.cn/

### 项目搭建步骤

### 1、下载项目并切换到项目中
https://www.mostop.cn/product.html

### 2、修改目录权限
##### chown www:www app_backend/runtime/
##### chown www:www app_backend/web/assets/
##### chown www:www app_backend/web/uploads/

### 3、添加 nginx 配置到 nginx 服务器中，注意修改项目名称及路径
##### \_\_DOCUMENT\_\_/free.mostop.cn.public.conf

### 4、创建 utf8、utf8_general_ci 的 mostop_free 数据库并导入数据
##### \_\_DOCUMENT\_\_/mostop_free.sql

### 5、修改数据库连接配置
##### vim common/config/db.php

### 6、绑定开发 hosts
##### 192.168.101.245 admin.free.mostop.cn.public

### 7、访问项目链接地址，完毕！
##### http://admin.free.mostop.cn.public/


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eca1ac766a8981c4957d6bd40cc953f0797244339dd16b58638881459af2df3d366a1c23c5818a9a28c1e59a07d75dcef)