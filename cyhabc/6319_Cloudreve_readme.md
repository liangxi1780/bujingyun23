![logo_white.png](https://raw.githubusercontent.com/HFO4/Cloudreve/master/static/img/logo_white.png)

Cloudreve - Make the cloud easy for everyone
=========================
[![Packagist](https://img.shields.io/packagist/v/HFO4/Cloudreve.svg)](https://packagist.org/packages/hfo4/cloudreve)
[![Latest Unstable Version](https://poser.pugx.org/hfo4/cloudreve/v/unstable)](https://packagist.org/packages/hfo4/cloudreve)
[![License](https://poser.pugx.org/hfo4/cloudreve/license)](https://packagist.org/packages/hfo4/cloudreve)

[主页](http://u.720life.cn/g/a3fa9a4580abf6698946d084ad0e9d3610c8bb2896380ec5d35fd47360c3c242) | [论坛](http://u.720life.cn/g/15c83f01d8fe4e45aefd09338d27da295727cc1bf00f0009bef0ba3b66eb9260) | [演示站](http://u.720life.cn/g/905cbac40c7500a167ad70e477c7306da9a6ab7f17f6c52303d12512b28b7161) | [QQ群](http://u.720life.cn/g/55fcd4cfb32e35fc063cde71dfc8708fdc3cae8d0d1ba3cc6063c482df3b9a7252435feece0ce7c359e8243f0198dc70) |[Telegram群组](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304644f9d75c3b291418d20e52fee2f1eeccb4fc23c9c59a5aa466923174712057d9)

基于ThinkPHP构建的网盘系统，能够助您以较低成本快速搭建起公私兼备的网盘。

![homepage.png](https://download.aoaoao.me/homepage-linux.png)

目前已经实现的特性：

* 快速对接多家云存储，支持七牛、又拍云、阿里云OSS、AWS S3、自建远程服务器，当然，还有本地存储
* 可限制单文件最大大小、MIMEType、文件后缀、用户可用容量
* 基于Aria2的离线下载
* 图片、音频、视频、文本、Markdown、Ofiice文档 在线预览
* 移动端全站响应式布局
* 文件、目录分享系统，可创建私有分享或公开分享链接
* 用户个人主页，可查看用户所有分享
* 多用户系统、用户组支持
* 初步完善的后台，方便管理
* 拖拽上传、分片上传、断点续传、下载限速（*实验性功能）
* 多上传策略，可为不同用户组分配不同策略
* 用户组基础权限设置、二步验证
* WebDAV协议支持

To-do:

* - [ ] 重写目录分享和单文件分享页面样式
* - [ ] 增加保存其他用户的分享到自己账户（限Pro版）
* - [ ] 推出辅助程序GoDriver,用于驱动php或客户端实现不了的功能，并借此实现:
   * - [ ] 压缩包解压缩、文件压缩
   * - [ ] 对接Ondrive、Google Drive,上传模式为先上到自己服务器，然后由GoDriver中转
* - [ ] 用Golang重写的远程服务端

安装需求
------------
* LNMP/AMP With PHP5.6+
* curl、fileinfo、gd扩展
* Composer

简要安装说明
------------

#### 1.使用Composer安装主程序
```
#安装开发版
$ composer create-project hfo4/cloudreve:dev-master
```

```
#等待安装依赖库后，会自动执行安装脚本，按照提示输入数据库账户信息
   ___ _                 _                    
  / __\ | ___  _   _  __| |_ __ _____   _____ 
 / /  | |/ _ \| | | |/ _` | '__/ _ \ \ / / _ \
/ /___| | (_) | |_| | (_| | | |  __/\ V /  __/
\____/|_|\___/ \__,_|\__,_|_|  \___| \_/ \___|
        
                Ver XX
================================================
#按提示输入信息
......
```

```
#出现如下提示表示安装完成
Congratulations! Cloudreve has been installed successfully.

Here's some informatioin about yor Cloudreve:
Homepage: https://pan.aoaoao.me/
Admin Panel: https://pan.aoaoao.me/Admin
Default username: admin@cloudreve.org
Default password: admin
```

#### 2.目录权限
`runtime`目录需要写入权限，如果你使用本地存储，`public` 目录也需要有写入权限

#### 3.URL重写
对于Apache服务器，项目目录下的`.htaccess`已经配置好重写规则，如有需求酌情修改.
对于Nginx服务器，以下是一个可供参考的配置：
```
location / {
   if (!-e $request_filename) {
   rewrite  ^(.*)$  /index.php?s=/$1  last;
   break;
    }
 }
```

#### 4.完成
后台地址：`http://您的域名/Admin` 初始用户名：`admin@cloudreve.org` 初始密码：`admin`
#### 后续操作
以下操作不是必须的，但仍推荐你完成这些操作：
* 修改初始账户密码
* 到 设置-基础设置 中更改站点URL，如果不更改，程序无法正常接受回调请求
* 添加Crontab定时任务 ：你的域名/Cron
* 如果你打算使用本地上传策略并且不准备开启外链功能，请将·public/uploads·目录设置为禁止外部访问
* 如需启用二步验证功能，请依次执行`composer require phpgangsta/googleauthenticator:dev-master` `composer require endroid/qr-code`安装二步验证支持库
* 给本项目一个Star~

文档
------------
* [完整安装说明](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304644f9d75c3b291418d20e52fee2f1eecc547b9caa9ca53be8055305be6795a0d2055895caa0414ca6243a40b896d8c61ac0199bda20a39aa310e08de5f4e6edf6)
* [安装及初次使用FAQ](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304644f9d75c3b291418d20e52fee2f1eecc547b9caa9ca53be8055305be6795a0d289f7d1959577782ea1f32d93603ab1419f50764faaee0662ae8188d626aeec1146e87a41f96c4559fdd7e3228302b00c2992c3f4031655e181a52a514aa87077)

许可证
------------
GPLV3



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee873e8129dcebea8dafbc5c4640bf1cffbef3c6fd71c7eca54264cef6dd2b3488e1c3eb4d15565903113fb96ad7928a6)