#描述

最近在云栖社区的雨客的博客上看到了一个设计图形验证码的案例，经过试验和目前OpenResty的最新功能，对原来代码进行了调整（采用OpenResty自带的Redis库、替换了原来有问题的随机数种子设置逻辑），另外也增加了独立删除验证码的接口，后续可能会视需要增加图形验证码的分片存储等功能

#代码结构

lua_scripts  接口的实现逻辑脚本

lualib       替换lua-uuid库的lua脚本实现

nginx        nginx配置文件


#依赖

gd图形处理库[http://www.boutell.com/gd/http/gd-2.0.33.tar.gz](http://u.720life.cn/g/7511bd621156e0d244002bdb1c0eb8813d6ae3ca57ebe7aff614768d452fc342ecce23d9df7aebdaca0701323ab114c7 "gd-2.0.33")

nginx sysguard模块[https://github.com/alibaba/nginx-http-sysguard/archive/master.zip](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304637dc453ed13008bce171d03b7c4391f06249af2422c1e05f609240c00fd6af6284b9ed33a13f5f1c604de17436820d6406efa76732c7f2f46df201141e513975 "nginx sysguard模块")

OpenResty[http://openresty.org/download/openresty-1.9.15.1.tar.gz](http://u.720life.cn/g/847a7658f2aaf9f3bf6ef90149776062827d324e1a9c2d724ea7bd461821a1dcf0a67627ba20c156227a29066dd2f78a55e9e8bd4b3cd7cca7678719dc8cf00e "OpenResty")

Lua-Resty-UUID[https://github.com/dcshi/lua-resty-UUID/archive/master.zip](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304699afa5d550a7cc5a2dcf4025dfe190ea296eabf64f1828969ce796ad367b31dcf7ee9f2559b66192f718c90a58123e38 "Lua-Resty-UUID")

Lua-GD[http://jaist.dl.sourceforge.net/project/lua-gd/lua-gd/lua-gd-2.0.33r2 (for Lua 5.1)/lua-gd-2.0.33r2.tar.gz]

Redis[http://download.redis.io/releases/redis-3.2.3.tar.gz](http://u.720life.cn/g/9b4a1380e2aa619eac4d900347bdc8b90291aec0a8652a552cf3d3c67ed6e21db666da10974108970ceb24cfba26f06a29f078405559afea235c84b2a04664ed "Redis")

#使用方法

请求验证码：
http://192.168.10.112:9000/captcha-require
http://192.168.10.112:9000/captcha-require?picgid=abcd1234
http://192.168.10.112:9000/captcha-require?picgid=abcd1234&picwidth=100&picheight=40

验证验证码：
http://192.168.10.112:9000/captcha-check?picgid=abcd1234&picstr=1234
直接返回true或者false



#安装说明

[https://git.oschina.net/kevin158/captcha_server/blob/master/INSTALL.md](http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b57967a7e9e5fe3b274124057bf3f5fe3a59a24f6ca29b02416e752a92d47fad173b6a146cff45293425259dcced4bf451cd80b6d799fa58f0b308564d34d9316 "进入")



#联系

堂吉诃德
 
421093703@qq.com





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec2ba211ab1d9791772c9e3da986c73b893fc5450a9849142637af1cc01a93c24715bdb229719325f66e704d0228bb72983e01f47af5df9ceab8798294fe8553d)