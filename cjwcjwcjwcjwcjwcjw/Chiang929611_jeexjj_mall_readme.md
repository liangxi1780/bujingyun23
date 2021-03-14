#### 特别致谢
- 架构借鉴[xmall](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5942597dfece292f4f4928296d19981b)项目，本前端项目[mall-front]https://gitee.com/zhanghejie/jeexjj_mall/mall-front
- 向xmall致敬https://gitee.com/Exrick/xmall.
- 感谢 [yucccc](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cd7017a4f1aa1f7d34b7a3c3cee04ce4) 的开源[vue-mall](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046972527ba0da1295bf647a094e05ea6bd1e24e4d1f8ba19c2f56965bef13b40ec) 项目提供前端页面及框架支持

#### 单体版
一个后台，一个前端，部署简单。请移步[https://gitee.com/zhanghejie/jeexjj_mall_single](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e789c43b0e1a4ed787a11eafbb7a93d70ef04633dd2303a70a0a1ee1e50269a66),

#### 项目介绍
- 是基于jeexjj轻量级快速开发框架开发的商城。QQ交流群：174266358。
- 基于springboot的微服务模式，可平滑升级为微服务高并发架构。
- 高仿锤子科技商城，商城前端使用vue2.0前后端分离，后端使用jeexjj框架开发。
- 了解jeexjj轻量级快速开发框架，请移步 [码云开源地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e789c43b0e1a4ed787a11eafbb7a93d7099586d9ed71a6f54aea49c4c1afb08b1) 或  [github开源地址](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304631739ba00703141f47fa56aafd0cc690d16bfa06fe78d93926aaf771bc343e3f)。
- jeexjj_mall是基于jeexjj轻量级快速开发框架开发的高仿锤子科技商城，商城前端使用vue2.0前后端分离，自适应移动端，帮助中小企业快速搭自已的B2C商城。
- 使用redis缓存，提高商城的响应速度，减轻数据的压力。


#### 项目架构
- mall-common 是最核心的模块
- mall-dao 是操作数据库的模块,依赖关系为mall-dao <== mall-common
- mall-admin 是后台管理端,基于springboot，依赖关系为 mall-admin <== mall-dao <== mall-common
- mall-api是商城的前端api,基于springboot，依赖关系为 mall-api <== mall-dao <== malll-common
- mall-front商城的前端,基于vue2.0,前后端分离.

#### 技术选型
#### 后端技术:
技术 | 名称 | 官网
----|------|----
redis | nosql DB  | [https://redis.io/](http://u.720life.cn/g/70336383bbe1092dca9fcec94f2fd10823c1cea91ac1108405bfbd56f5b819fc)
spring-boot | 后端框架  | [http://spring.io/projects/spring-boot](http://u.720life.cn/g/f979f566e9f1eb43d4a867743a4b0ee43e5c42bd03943a23ec4566678bf3695b9f5f9278273ac2c29634d23f71d87631)
Spring Framework | 容器  | [http://projects.spring.io/spring-framework/](http://u.720life.cn/g/e0845233bf5cae93142c4c8e1c8864d4e670a90f87afc2ad04fb4c1d1899c07fdd2c7fa40574a04f80c374ab3968c758)
SpringMVC | MVC框架  | [http://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/#mvc](http://u.720life.cn/g/a6ba8c6b0e93c9f31bd435772627160d78653d6a55dc6315bda807ef09f29a08138b35c7e95760a878e8a0494b6946c305ffdacf75171f9fb043ea8675f3d72d7a4c2af751af247d69b57160e21c66cf4b1624d4570ec58555958c387c809a0d)
MyBatis | ORM框架  | [http://www.mybatis.org/mybatis-3/zh/index.html](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a215e4d93221eb26b660bea25686b89be63142caf406b6e1c14d3ab51db921e10ca)
Maven | 项目构建管理  | [http://maven.apache.org/](http://u.720life.cn/g/bc840264f6cc23df0a8935b6f2922fec747e8988e9d6774b642901b9662b323f)
freemarker | 页面模板引擎  | [http://freemarker.foofun.cn/](http://u.720life.cn/g/91631dc92407872deef9e7c2f21c90370ec42bca0660599fef01f69ddec2c69d)


#### 前端技术:
技术 | 名称 | 官网
----|------|----
Vuejs | 前端框架  | [https://vuejs.org/](http://u.720life.cn/g/1c3db3fec6433a3fb191bb48af91f3bb055304712f0641658c814ca15fec0089)
nodejs | JavaScript engine  | [https://nodejs.org/](http://u.720life.cn/g/6dd25ec2eceebbb6348ad519a7343cbc690041c96fefc0320d9aace915151649)
Bootstrap | 前端框架  | [http://getbootstrap.com/](http://u.720life.cn/g/e23be2821e5181a1a46a005bc6e93d9dc1c8dad0ef41593aa593e12a30fc455b)
Font-awesome | 字体图标  | [http://fontawesome.io/](http://u.720life.cn/g/214bbe9ff6ad53005f2a6de3696f36fffcfbfc1374f8d2fb41b782949ee44927)
zTree | 树插件  | [http://www.treejs.cn/v3/](http://u.720life.cn/g/498bbd2d294e9101825c13f60c5e8cb3f681e96d109cd0ce72a74684c0f7e9ca)
layui | 前端框架  | [http://layer.layui.com/](http://u.720life.cn/g/d6276f71012dea0742ec9af0acbaffd3bd2dc9703f25e563fbb8b365fdb374da)
ace | 前端框架  | [http://ace.jeka.by/](http://u.720life.cn/g/1287cf99d0ed059c558f0a16455fa008a310849f0f1c5cff7cb0a49bfa81ed65)


#### 后台管理项目mall-admin安装教程
1. 安装jdk1.8+、mysql5.7+、maven3.5+、redis
2. 下载代码并初始化数据库doc/db/mall_*.sql
3. 下载myeclipse2017(后面有地址)，导入maven项目 mall-common、mall-dao、mall-admin
4. 每个项目依次执行maven install
5. 运行mall-admin的application.java的main方法。
6. 访问http://localhost:8081/mall-admin

#### 商城mall-front运行步骤
1. 运行springboot项目mall-api
2. 本地安装node3.js
3. 在mall-front根目录运行命令npm install 等待执行完毕
4. 在mall-front根目录运行命令npm run start即可在浏览器中 的localhost:9999查看项目

#### 技术交流
1. QQ群：174266358
2. 开发工具下载地址：https://pan.baidu.com/s/1BXnWGkASzmYDroIYtJbCBg

#### 后台管理端页面效果
![](doc/images/admin1.png)
![](doc/images/admin2.png)

#### 商城页面效果
![](doc/images/mall1.png)
![](doc/images/mall2.png)
![](doc/images/mall3.png)
![](doc/images/mall4.png)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5345b21439780f53aafafe3397cb45caf0756efe179901b86f8c05cb9cc9702f95de71dd5923af91d817db33041625cc)