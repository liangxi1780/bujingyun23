# Rss Hunter 将微博 微信公众号等网站内容转RSS服务
可以直接将某个微博账号、微信公众号转为RSS服务，提供RSS订阅源

- 基于Spring Boot 构建服务
- 使用rome类库处理RSS
- 使用jsoup处理网站dom

基于maven构建，可以直接打包编译预览，内置swagger2文档生成，可以直接基于此进行调试 
http://localhost:80/swagger-ui.html 


微博RSS输出，原理是微博秀网站抓取，基于微博用户uid获得,访问 http://localhost:80/weiborss/uid/1671353227 获取该uid的RSS输出示例：
![微博RSS接口输出](http://wx4.sinaimg.cn/large/639ed38bgy1fkhzw9kphdj21kw0thqcl.jpg "微博RSS接口输出")

uid获取方式之一：
```
进入微博主页，F12查看元素后，直接搜索 'uid'

```
![获取微博用户uid](http://wx3.sinaimg.cn/large/639ed38bgy1fki0cv7j9vj21820rmjxw.jpg "获取微博用户uid")



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e171511531bc1da10728a8ee2e2a30ce459123bf82ef81f078f6cf00f2ea025ee75ee75d8cab609debc72d3aede60baa6)