![](https://img.kancloud.cn/d7/f0/d7f0871b2b31924c94e7b1aac739fafc_397x493.jpg)

## Orange 开发框架是一款 Golang 语言 web 开发框架


### 主要特性
- 基于 golang 性能不凡；
- MVC 分层设计，逻辑清晰；
- 核心功能短小精悍，灵活度高；
- 丰富的工具包，有 图片验证码，本地缓存，发送邮件，http请求客户端，日志 等常用工具包；
- 持续更新，框架应用再多个线上成熟项目，为了解决各类业务问题，框架持续更新；
- 源码地址 [https://gitee.com/zhucheer/orange](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edebcc6e3f04089fbca7786d02db0c3ebd6241c51bca8a515421c66dc865c22fc)
- 文档地址 [https://www.kancloud.cn/chase688/orange_framework](http://u.720life.cn/g/ba0134f7488dc7089e9b70cb68034558b15287cbba9ce167c1b11b1ca9e4f2426b1778acb92f40623e02720637ae90bc7688bcb2cbb5738caa685da7386fb133)

## 快速开始

### 安装
> 下载项目 
`go get gitee.com/zhucheer/orange
`

### 创建一个新项目
```
>  orange create project // 命令执行后将会在GOPATH/src目录下生成项目
```
如果出现  orange 命令不存报错在则需要将 GOBIN 添加到环境变量。


###  启动项目
- 通过 go mod 管理相关依赖, 如果 go 版本小于 1.12 需要手动开启 go mod 功能； 
```
window 下在 cmd 中执行：set GO111MODULE=on
linux  下执行：export GO111MODULE=on
```
- go1.13版本环境通过配置env开启 go mod ，还需要添加代理配置;
```
//开启go mod
go env -w GO111MODULE="on"
// 添加国内代理
go env -w GOPROXY=https://goproxy.cn,direct
```


- 进入项目目录后依次执行下面的命令
```
>  go mod init // 初始化go mod 包管理
>  go mod tidy // 加载依赖包
>  go mod vendor // 将依赖包拷贝到项目目录中去
>  go run main.go [--config=config/config.toml] //启动项目 默认配置参数可以忽略，如配置文件位置改变可通过参数指定。
```

### 打包项目
> 配置好GOBIN环境变量，进入项目目录，然后执行如下命令：
> window： `orange.exe build`
> linux：`orange build`
> 打包命令默认会将程序打包到 build 目录下，打包好的程序可以直接运行，不依赖 golang 环境。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e54413da6c9f6027675a2d3df7d08b6e1f6e3b0f18d6de5f01ee230d60025189c93494e56046e9319a5f01d7d59412586)