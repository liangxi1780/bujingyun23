# Docker安装及使用Wiki

------

## 1.安装

不要使用系统的包管理工具安装Docker，如yum/apt-get install docker

daocloud.io提供了最新版的简洁安装脚本，只需要执行

```shell
curl -sSL https://get.daocloud.io/docker | sh
```

即可安装所有linux发行版最新版本的Docker

## 2.镜像加速

只需执行

```shell
curl -sSL https://get.daocloud.io/daotools/set_mirror.sh | sh -s http://e8719b5b.m.daocloud.io
```

即可加速官方镜像的pull速度

## 3.我们的镜像站 http://114.215.93.217:5000

在这里有海量的生产环境镜像，你可以编辑/etc/docker/daemon.json
将内容改为如下的JSON

```json
{
    "registry-mirrors": ["http://e8719b5b.m.daocloud.io"],
    "insecure-registries":["http://114.215.93.217:5000"]
}
```
 
然后执行

```
systemctl restart docker
```

即可pull此镜像站的镜像

## 4.镜像使用

在每个镜像内都有镜像的使用方式



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1d7d9f81f3be5d8609b4c211c13a30b05bb0e44e4408f555c1f65ed6ff34641f318a98ec9ce41082f37b5dc811e41835)