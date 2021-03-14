# 轻量级 ISC BIND9 容器

ISC BIND9 Container (Stable: 9.14.8-r5) built on top of Alpine

Last update: 2019-12-25

Latest Stable Docker Tag: 9.14.8-r5

## RUN

+ 创建数据持久化挂载目录

```
mkdir -p /data/bind/cache
cp -r configs /data/bind/etc
```

+ 按需修改配置文件

`/data/bind/etc/`

+ run container

```
# modify or delete environment: OPTIONS=
docker-compose up -d
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6efb74177a68229528b8c22eacbe68cce91048026e3f2cb7cdd18c575e0a55207f46f0399f2ff8a2aad2a413fe32814424)