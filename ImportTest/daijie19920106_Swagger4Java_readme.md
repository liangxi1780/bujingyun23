# 简介

**`server-api`** 是一个GUI的WEB接口管理工具，基于 [swagger-ui](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ee873d8b7265bda98dbeb1b913855dc8cc8fe4f2d8a7cf6393aeda706a915000) 的后台API开源项目，采用SpringMvc+Maven3+Jdk1.7+Tomcat7,该项目的初衷是为了更好的去发展Swagger-ui与SpringMvc的结合，希望能够更加灵活，轻量化的根据后台不同的数据源展示出不同接口文档，满足日益增长的接口文档需求，这里包括（接口文档的格式，权限，视图，Mock数据，Api监控,自动化测试,接口文档分享，版本管理等），**`server-api`** 可以帮助后台开发人员解放双手，直接用注解生成文档，省去与前端、测试的沟通，以及项目上线后问题的监控和排查。

# 特色

- 完美融合Spring3.2.9+,采用注解编写文档
- 最简项目架构，方便快速上手，排除其他干扰
- 免费的技术支持

# 部署
## 准备工作
- Eclipse/MyEclipse/IDEA
- JDK1.7+
- Tomcat7.*+
- Git
- Maven3插件

## 构建项目
### 获取源代码

#### 如果你只是使用

```
git clone git@github.com:mousycoder/server-api.git

git checkout master
```

#### 如果你也想和我一起开发
- 先Fork
- PR一下我的最新代码(develop分支)
- 贡献代码
- PR你的代码到我的仓库

若是好的建议和方案，你将会在作者的仓库看到你贡献的代码，这将是多么让人兴奋的事情。


### 导入到IDE
以Eclipse为例，在File->Import->Existing Maven Projects,将server-api项目导入进来。


### 启动项目

- `maven clean install`
- 右键Run As-> Run on server (前提配置好tomcat)

### 日志
- 改变日志级别 src/main/resources->log4j.properties->`log4j.rootLogger=DEBUG, Console`改成ERROR级别 默认是debug调试级别













 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e60197232646e853e29399ee1a1d64a60ad546511e472f77b3c874043325d5d007a74d0f12678c0f2937d0d919c1a278f69b81d01dcf56b13a61fbc67a2465432)