# 说明：此目录为 学习reboot自动化2期的课堂练习和作业。
Lesson01，02，03，04，05，06，07，09 为JsonRpc原理和zabbix及一些展现如graphite的二次开发，实现cmdb；
Lesson08，11，12 为 ELK搭建和简单使用以及自动发布系统。Lesson12的课程作业未能全部完成。

# 将课堂使用的镜像打包分享
## 共享地址，百度网盘
后续补充

## Lesson09 镜像打包脚本

vagrant package default --output reboot-devops-02.box --vagrantfile Vagrantfile
vagrant package webserver_01 --output reboot-ms-web-01.box --vagrantfile Vagrantfile
vagrant package zabbix_server --output zabbix-server-01.box --vagrantfile Vagrantfile
vagrant package graphite --output graphite-server.box --vagrantfile Vagrantfile

## Lesson12 镜像打包脚本

vagrant package default --output elk-01.box --vagrantfile Vagrantfile
vagrant package odweb_01 --output odweb_01.box --vagrantfile Vagrantfile


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef2087cfb4ba8bd02f85ffb407c98dd799e8445cb97d2a16203d94a90c5402e6d115ae812175a70fff93046a3af38b3a1)