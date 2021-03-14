# RemoteTail

RemoteTail是一款支持同步显示多台远程服务器的日志文件内容更新的工具，使用它可以让你同时监控多台服务器中某个（某些）日志文件的变更，将多台服务器的`tail -f xxx.log`命令的输出合并展示。

![logo](https://oayrssjpa.qnssl.com/remote-tail.jpg?20161011)

## 使用场景

假设公司有两台web服务器A和B，由于初期没有专业运维进行配置集中式的日志服务系统，两台服务器上分别部署了两套相同的代码提供web服务，使用nginx作为负载均衡，请求根据设定的策略转发的这两台web服务器上。

AB两台服务器中的项目均将日志写到文件系统的`/home/data/logs/laravel.log`文件。这种情况下如果我们需要查看web日志是否正常，一般情况下就需要分别登陆两台服务器，然后分别执行`tail -f /home/data/logs/laravel.log`查看日志文件的最新内容，这在排查问题的时候是非常不方便的。RemoteTail就是为了解决这种问题的，开发人员可以使用它同步显示两台（多台）服务器的日志信息。

## 安装

在[release页面](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046661964873a2021dc5cda52f202002efab0d14dd388a83b195e38ce30b0b4540a)下载对应的`remote-tail-平台`可执行文件，将该文件加入到系统的`PATH`环境变量指定的目录中即可。

比如，Centos下可以放到`/usr/local/bin`目录。

    mv remote-tail-linux /usr/local/bin/remote-tail

## 使用方法

使用前需要宿主机建立与远程主机之间的[ssh公钥免密码登陆](http://u.720life.cn/g/7c059e6b47e684702c648bf0beafe6f48f9e8c15fb57fb8df5aab6269b8d84d85881d710221be7ed219e3c4f29a468faedcec0b0f7fd98d29d0c0e4c92ea97cfb93b48d9699f79427987db6abe5bf2d790f1201aa14b89aeaf87d98dc6be37802c09b621dc50282e9f488a998cff8a0587a4057f8a94503d4f94f6c0f6f2e785f828b48ef761d55da0bfe7f7be2f6ca9)。

    remote-tail -hosts 'watcher@192.168.1.226,watcher@192.168.1.225' \
    -file '/usr/local/openresty/nginx/logs/access.log'

![demo](https://oayrssjpa.qnssl.com/remote-tail-demo.jpg?20161011)

> 如果服务器sshd监听的非默认端口22，可以使用`watcher@192.168.1.226:2222`这种方式指定其它端口。

### 指定配置文件

通过使用`-conf`参数可以为命令指定读取的配置文件，配置文件为TOML格式，请参考`example.toml`文件。

配置文件`example.toml`：

    # 全局配置,所有的servers中tail_file配置的默认值
    tail_file="/data/logs/laravel.log"

    # 服务器配置,可以配置多个
    # 如果不提供password,则使用当前用户的ssh公钥,建议采用该方式,使用密码方式不安全
    # server_name, hostname, user 配置为必选,其它可选
    [servers]

    [servers.1]
    server_name="测试服务器1"
    hostname="test1.server.aicode.cc"
    user="root"
    tail_file="/var/log/messages"
    # 指定ssh端口，不指定的情况下使用默认值22
    port=2222

    [servers.2]
    server_name="测试服务器2"
    hostname="test2.server.aicode.cc"
    user="root"
    tail_file="/var/log/messages"

    [servers.3]
    server_name="测试服务器3"
    hostname="test2.server.aicode.cc"
    user="demo"
    password="123456"

执行命令：

    remote-tail -conf=example.toml

## 如何贡献

欢迎贡献新的功能以及bug修复，**Fork**项目后修改代码，测试通过后提交**pull request**即可。

## 问题反馈

你可以在github的issue中提出你的bug或者其它需求，也可以通过以下方式直接联系我。

- 微博：[管宜尧](http://u.720life.cn/g/c1e3906cb73241d8bdbe53b5d457b17d26a24342dc891f8177814c0fea58fe0c)
- 微信：mylxsw

![WEIXIN](https://oayrssjpa.qnssl.com/join_weixin.jpg)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1070e69ad4ecc0b53c9dc5a571152181bf8bd6514a082847ec452b67458fcc234d17de01beb0030dbb541b16f0981e56)