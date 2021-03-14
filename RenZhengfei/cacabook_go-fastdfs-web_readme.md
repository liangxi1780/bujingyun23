## Go-Fastdfs web管理平台
> go-fastdfs 是一个简单的分布式文件存储，具有高性能，高可靠，免维护等优点，支持断点续传，分块上传，小文件合并，自动同步，自动修复。本项目为go-fastdfs的web管理端

[前往 Go-Fastdfs](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046be25dbc85df6e79f260d28f18e5247b9a9c24bb91fcc62dbddd54a0a964ef30e)

## 简单预览图
![控制台](./screen/01.png)

![文件上传](./screen/02.png)

![文件列表](./screen/03.png)

![集群列表](./screen/04.png)

## 注意事项
1. 默认端口8088,修改默认端口号更改config/application-prod.properties即可
2. 如go-fastdfs开启了按组管理,则需要填写组名,反之不用填写
3. 进入安装页填写集群地址时,该地址需要在go-fastdfs配置文件配置管理ip白名单,否则获取不到数据!
4. 文件列表功能需要go-fastdfs服务版本在v1.2.8以上
5. 遇到获取不到信息的功能,先试一下本地调用go-fastdfs接口看是否能获取到

## 运行步骤
共提供三个版本,无环境版(需要自己安装java运行环境),Windows自带JRE环境版,Linux自带JRE环境版
[下载地址](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304649f290bc54ed639ad24bdf4457bac98a5db89b613b13aeb9d33d884282a08f125e820f46141fd5a43ec294f877933c04)

### 无环境版(Windows运行)
解压压缩包后,直接运行start.bat
### 无环境版(Linux运行)
解压压缩包后,运行脚本,命令如下:
```
1.运行
./goFastDfsWeb.sh start
2.查看运行状态
./goFastDfsWeb.sh status
3.重新启动
./goFastDfsWeb.sh restart
4.停止
./goFastDfsWeb.sh stop
```
### Linux自带JRE环境版
解压压缩包后,运行脚本,命令如下:
```
1.运行
./goFastDfsWeb.sh start
2.查看运行状态
./goFastDfsWeb.sh status
3.重新启动
./goFastDfsWeb.sh restart
4.停止
./goFastDfsWeb.sh stop
```
### Windows自带JRE环境版
解压压缩包后,直接运行start.bat

## 开发说明
项目使用SpringBoot,Mybatis,Shiro进行开发,为方便后期用户安装,数据库采用Sqlite,为了代码的简洁,使用了lombok插件,请在开发前提前安装.
开发前请先将application.properties中的spring.profiles.active=prod改为dev环境,之后参照application-dev.properties进行配置

## 打包方式
1. 将application.properties配置文件中spring.profiles.active的值改为prod
2. maven运行mvn clean package
3. 完成之后得到jar,zip,tar.gz三种格式文件


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0bbc8742018d376b4ea6baebfb5b78cd0c6ca39d53f0f5b613e9b8530f3648793584facf918de93cdfd9eec9a3b7a2d8)