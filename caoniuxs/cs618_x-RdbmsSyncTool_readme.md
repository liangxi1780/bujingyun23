RdbmsSyncTool 关系型数据库同步工具

**xJavaFxTool交流QQ群：== [387473650](http://u.720life.cn/g/55fcd4cfb32e35fc063cde71dfc8708f1616bfd7abbbc3d3a6948ee608e7fd334f56df463bdf0e71b90ddc10999d2b2a) ==**

#### 项目简介：
RdbmsSyncTool是使用javaFx开发的关系型数据库同步工具[xJavaFxTool](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e550861c6e2545846a56f6de25a00b38478a3de9974eb507ce6d982131c171065)的插件集合，可实现打包后让框架自动加载，可在线下载和更新工具，后续小工具将在这个项目中添加，实现动态jar包加载。

#### 环境搭建说明：
- 开发环境为jdk1.8，基于maven构建
- 使用eclipase或Intellij Idea开发(推荐使用[Intellij Idea](http://u.720life.cn/g/a27ddb2b79548d3a829f3f0224b2480d40c182108896ad3a7f25af80b989b1a9)
- 本项目使用了[lombok](http://u.720life.cn/g/9cec729ef2d3c72b70f7caf7a64fe54c004be7f5a331560d74f301adfc8849d5),在查看本项目时如果您没有下载lombok 插件，请先安装,不然找不到get/set等方法
- 依赖的[xcore包](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee26afa913660b47f2edcdba65877ed9f)已上传至git托管的maven平台，git托管maven可参考教程若无法下载请拉取项目自行编译

完成关系型数据库表结构获取，多种类型数据库直接数据转移，同步。

目前支持的数据库类型有mysql、Oracle、sqlserver、PostgreSql、达梦、sqlite、h2、access等

![数据库同步工具.png](images/数据库同步工具.png)

#### 版本记录
- 0.0.1  20200419
  1. 完成基本功能配置（对表进行查询、删除、建表语句、同步数据等操作）
  2. 支持mysql、Oracle、sqlserver、PostgreSql、达梦等数据库连接
- 0.0.2  20200421
  1. 添加sqlite、h2、access数据库支持
  2. 优化数据同步功能



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea3892426c461d893e6cb120f56bceb3c6c272ce4b82fe044764335db33daece5ac79e912bb2c1ba204a7408bded17ffc)