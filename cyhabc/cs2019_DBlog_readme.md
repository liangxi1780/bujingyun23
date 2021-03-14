 **OneBlog** 一个简洁美观、功能强大并且自适应的Java博客。使用springboot开发，前端使用Bootstrap。支持移动端自适应，配有完备的前台和后台管理功能。    

![JDK](https://img.shields.io/badge/JDK-1.8-green.svg)
![Maven](https://img.shields.io/badge/Maven-3.3.1-green.svg)
![MySQL](https://img.shields.io/badge/MySQL-5.6.4-green.svg)
![Redis](https://img.shields.io/badge/Redis-3.0.503-green.svg)
[![license](https://img.shields.io/badge/license-GPL%20v3-yellow.svg)](https://gitee.com/yadong.zhang/DBlog/blob/master/LICENSE)

----

# 重要声明

1. 本项目配有相关[帮助文档](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4b545911174146a7e5e4f8f8fe023eb3c5) 【[新版文档](http://u.720life.cn/g/bffa3d31a87d90823a26a1bdcaa84b22a3cfc74f67903931cae9e84d7299ada0)】。文档中包括**基本的项目说明**、**shiro标签使用**、**七牛云配置**和一些常见的**异常问题解决方案**。使用时碰到问题请**优先**查阅【[帮助文档]https://gitee.com/yadong.zhang/DBlog/wikis
2. **提问题**前请优先阅读【[如何向开源社区提问题](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304648c6b52a8408b0350af3ec0815119068a7094db81195f0a84a1e8328e0846d06)】&【[提问的智慧]http://www.dianbo.org/9238/stone/tiwendezhihui.htm
3. **提问题**时请优先选择[Gitee Issues](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4bf424d1246af68e30382b7bc4f500e1a4)（方便问题追踪和一对一解决），其次[我的博客-留言板]https://www.zhyd.me/guestbook
4. 本项目唯一官网：[https://www.zhyd.me](http://u.720life.cn/g/18bbd2c33807f8b838ed0a0ae89d415bad18847e42c683d71d6b91f29869e34a)  
5. 本项目开源地址：[Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4b774c2ac54f756cf8eb6d8afc642938ec)    | [Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046657004bda8ede94a1599a0a84b57ad66f65f9ea8e1489bbcc011ec33b91f7af6)
6. 本项目修改记录，详情请移步[这里](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4b05e6af079e83c97b1c6913dbb9723c8f02cf2fe0d34221667c441b9f34adf06e)
7. 如果你想贡献代码，请先阅读[这篇文章](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4b05e6af079e83c97b1c6913dbb9723c8f60bdf4f5e5d36071135eb8daf1c9da27)

----

# 写在前面的话
ps: 虽然我知道，大部分人都是来了**直接下载源代码**后就潇洒的离开，并且只有等到下次**突然想到**“我天~~我得去看看OneBlog这烂项目更新新功能了吗”的时候才会重新来到这儿，即使你重新来过，我估计你也只有两个选择：    

发现更新代码了 --> 下载源码后重复上面的步骤    
发现没更新代码 --> 直接关闭浏览器

虽然我知道现实就是如此的残酷，但我还是要以我萤虫之力对各位到来的同仁发出一声诚挚的嘶吼：

**如果喜欢，请多多分享！！多多Star！！**

----

# Demo 演示

[前台demo](http://u.720life.cn/g/b65afaeb5c59388a6c3ebd22d84fc94ca7bb5503fc2f2d3beef6823044946c39)

[后台demo(root,123456)](http://u.720life.cn/g/234486bdc93c127011ba4dc168c14a461dab22e4fc238cbcf193cc5ca5720cb3)

![admin端首页](https://images.gitee.com/uploads/images/2019/0129/191117_221c6064_784199.png "admin-index.png")
![admin端文章列表也](https://images.gitee.com/uploads/images/2019/0129/191135_21e4f61c_784199.png "admin-article.png")
![admin端发布文章页](https://images.gitee.com/uploads/images/2019/0129/191150_0d28d51a_784199.png "admin-publish-article.png")
![admin端系统配置页](https://images.gitee.com/uploads/images/2019/0129/191203_cc6941e4_784199.png "admin-config.png")
![admin端文章搬运工](https://images.gitee.com/uploads/images/2019/0129/191214_5e8f3c34_784199.png "admin-spider.png")
![admin端文章搬运工](https://images.gitee.com/uploads/images/2019/0129/191237_d015fcda_784199.png "admin-spider2.png")
![web端首页-pc](https://images.gitee.com/uploads/images/2019/0129/191409_d2604f7d_784199.png "web-index-pc.png")
![web端首页-mobile](https://images.gitee.com/uploads/images/2019/0129/191428_c76317e8_784199.png "web-index.png")
![web端文章详情页](https://images.gitee.com/uploads/images/2019/0129/191448_a2777443_784199.png "web-article-detail.png")

----

# 模块划分

| 模块  | 释义 | 备注 |
| :------------: | :------------: | :------------: |
| blog-core | 核心业务类模块，提供基本的数据操作、工具处理等 | 该模块只是作为核心依赖包存在 |
| blog-admin | 后台管理模块 | 该模块作为单独项目打包部署 |
| blog-web | 前台模块 | 该模块作为单独项目打包部署 |
| blog-file | 文件存储功能模块 | 支持local、七牛云和阿里云OSS |
| ~~blog-spider~~ | 爬虫相关代码模块 | 已使用[blog-hunter](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfa1050bdbd5b64a47fac6001844d91a0a8c02852bd5242c1c1406c4fdc5a279)插件替代 |


# 技术栈

- Springboot 2.0.8
- Apache Shiro 1.2.2
- Logback
- Redis
- Lombok
- Websocket
- MySQL、Mybatis、Mapper、Pagehelper
- Freemarker
- Bootstrap 3.3.0
- wangEditor
- jQuery 1.11.1、jQuery Lazyload 1.9.7、fancybox、iCheck
- 阿里云OSS
- kaptcha
- Qiniu
- webMagic
- ...

# 功能简介

- 支持wangEditor和Markdown两种富文本编辑器，可以自行选择
- 在线申请友情链接，无需站长手动配置，只需申请方添加完站长的连接后自行申请即可
- 支持将文件提交到百度站长收录平台，加快百度引擎的收录
- 自研评论系统
- 后台配备完善的权限管理
- 自带robots、sitemap等seo模板，实现自动生成robots和sitemap
- 集成七牛云，实现文件云存储
- 系统配置支持快速配置。可通过后台手动修改诸如域名信息、SEO优化、赞赏码、七牛云以及更新维护通知等。
- 管理员可向在线的用户发送实时消息（需用户授权 - 基于websocket实现，具体参考[DBlog建站之Websocket的使用](http://u.720life.cn/g/18bbd2c33807f8b838ed0a0ae89d415b46e452cb0761cd5af4c39e18fe7657eb)）
- “文章搬运工”功能，支持一键同步imooc、csdn、iteye或者cnblogs上的文章，可抓取列表和单个文章


# 使用方法(以blog-web项目为例)

1. 使用IDE导入本项目
2. 新建数据库`CREATE DATABASE dblog;`
3. 导入数据库`docs/db/dblog.sql`
4. 初始化数据库`docs/db/init_data.sql`
5. 修改配置文件
   1. 数据库链接属性(在`[blog-core]/resources/config/application-center-{env}.yml`配置文件中搜索`datasource`或定位到L.5) 
   2. redis配置(在`[blog-core]/resources/config/application-center-{env}.yml`配置文件中搜索`redis`或定位到L.14)
   3. 以上两个必备的配置项修改完成后就能启动项目了。关于其他配置项，请参考后台“系统配置”页面
6. 运行项目(三种方式，任选其一)
   1. 项目根目录下执行`mvn -X clean package -Dmaven.test.skip=true -Ptest`编译打包（注：-Ptest中的test为环境标识），然后cd到blog-web目录下执行`java -jar target/blog-web.jar`
   2. 在`blog-web`项目根目录下执行`mvn spring-boot:run`(注，如果报依赖错误，可在相关的依赖模块先执行install操作)
   3. 直接运行`BlogWebApplication.java`
7. 浏览器访问`http://127.0.0.1:8443`
8. `blog-admin`项目的启动方式与`blog-web`类似，请参考上面的使用说明

# 后续扩展
- [ ] 1. 页面缓存
- [ ] 2. cc防护
- [ ] 3. 配套小程序
- [ ] 4. 待续...
...

# 在用OneBlog的网站 
- [张亚东博客](http://u.720life.cn/g/18bbd2c33807f8b838ed0a0ae89d415bad18847e42c683d71d6b91f29869e34a)
- [攻城狮不是猫博客](http://u.720life.cn/g/935c1aaf3b0bd5ca2462e27b452208d84bb7f2a49afcdf767e1ba41bb43e9f93)
- [罗远祥博客](http://u.720life.cn/g/641c2c4f3b60afba8a3b9afbc7b1f6a841d50383f2bff40382a492c610701ae0)
- [小公举的博客](http://u.720life.cn/g/a64ec5dd3bd65c23168a9c5e477294e87a41cd1e268724c92869c076005c7525)
- [陈晓雷的博客](http://u.720life.cn/g/423aaaa5c65b95a4e2a291c2a88089a6c3382e99dd5e1b637359975b70a364f9)
- [宋高俊博客](http://u.720life.cn/g/89d202b9f470fea349faee36f405962813a4f9619c111b12919436746cea6fec)
- [Li Pan's 博客](http://u.720life.cn/g/0c43c5b190151aa2a84ae758ae0281c7a7f35df921c3f1b1ce36490c9a1757e2)
- [MTR小站](http://u.720life.cn/g/58ec1a0a9c2f7c9b148a6b3d3d2559674a7536d2c38c9009a8737ab311c14339)
- [小米球Blog](http://u.720life.cn/g/71446ccd22fdeaf0c6064fec8055bb32e21152b45b4ee48e02d87b9bc2a82a1b)
- [怀念时光](http://u.720life.cn/g/9ada6cc059181ccde3b51ea87fae15292bd6de3b85cd1fab4f96468d214a48d6)
- [Java干货铺子](http://u.720life.cn/g/d620ca91e58aca607b4c3040f0a0182b453d2346dd2261311288fe05e1e4e576)

烦请各位使用OneBlog的朋友，能留下你的网址（没别的意思，只是看看有多少人而已） - [点这儿](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4b0a0f89bd8e393152a6bac73155e0135b033b85edc1d3aaa83eeb59298b8ed51c)

----

# 交流

|  微信(备注:加群)  |  公众号  |
| :------------: | :------------: |
|   |   |

 **QQ群** 

1. 1群[![](https://images.gitee.com/uploads/images/2019/0129/191256_a40bceba_784199.png)](https://shang.qq.com/wpa/qunwpa?idkey=3571c554a143eff1e15807de033a240196c6b493b25b903d1d37571cfb6040aa)（ **已升为1000人群** ）
2. 2群[![](https://images.gitee.com/uploads/images/2019/0129/191256_a40bceba_784199.png)](https://shang.qq.com/wpa/qunwpa?idkey=38594b12fb0ec66459f0dba0316648a5c4bb71ea613289e5b57b8f44ad83ebc9)（ **人很少** ）

# 赞助

> 为了让OneBlog更好用，作者码代码码的头发都没了！请作者买块生姜擦擦头皮，据说这样有助于生发~~

| 支付宝  | 微信  | 支付宝红包  |
| :------------: | :------------: | :------------: |
|   |   |   |


# 生命不息，折腾不止！ 更多信息，请关注：
 1. [我的博客](http://u.720life.cn/g/18bbd2c33807f8b838ed0a0ae89d415bad18847e42c683d71d6b91f29869e34a)
 2. [我的微博](http://u.720life.cn/g/c1e3906cb73241d8bdbe53b5d457b17dc5e7cf5c1bd2599d2e47e0359722cd11)
 3. [我的头条号](http://u.720life.cn/g/118b7af38f18204760fd37a6bfa049ce966f36fd837fb4636774805882b6e67bf4ba6b0df274ad1d0f31575221ab137b)
 4. [我的imooc](http://u.720life.cn/g/9bdca284b716378ad8944a645c76d01825cac3ba4c37de1f1e3f15ff12923df27d7eaa23b08198cceb3c23f91ba9472a)
 
# 特别感谢

- 广大的开源爱好者
- 无私的网友
- [gentelella](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304628ac2f83964d8a3a7702cbb4884f2c74cc30b09825f04e0fa719831c8b43f591): 一款开源的Bootstrap3后台管理模板
- [七牛云](http://u.720life.cn/g/ca7678111e5ab467b173497aa7fc524dd173935df99a070088aa287106bccdc2c278dcb058568ddbc8eeca30d48115a3e5758610c590120ea4d9a6907e00d6f3): 强大的对象存储、CDN等服务提供商
- [emoji表情列表](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304617a8d7f607e5e061ec649074c0fab9da8169e4b761c22f8788fe93365d0977f6): emoji表情列表
- [blog-hunter](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f92c45c88917e1e95ffdf9fe3b14fee81ba656b1c4bad35d4f3b98b945c4895b): 博客猎手，基于webMagic的博客爬取工具，支持慕课、csdn、iteye、cnblogs、掘金和V2EX等各大主流博客平台。
- [JustAuth](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9894d7f9ce3e60d4881ec4b106227d88476): 史上最全的整合第三方登录的工具,目前已支持Github、Gitee、微博、钉钉、百度、Coding、腾讯云开发者平台、OSChina、支付宝、QQ、微信、淘宝、Google、Facebook、抖音、领英、小米、微软和今日头条等第三方平台的授权登录。 Login, so easy!
- 待续...

# 开源协议

[![license](https://img.shields.io/badge/license-GPL%20v3-yellow.svg)](https://gitee.com/yadong.zhang/DBlog/blob/master/LICENSE)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e701f58f6bdcd664e67cf9230ed244504c4f05388a44be19104cabafc768a8c6032f5700f84a2eb5501ef3ca3aae57d03)