#JFinalBlade java开发平台
## 平台简介
JFinalBlade是是基于多个优秀的开源项目高度整合封装而成的快速开发平台。内置了 用户管理、 角色管理、 菜单管理、字典管理、部门管理、附件管理、参数管理、连接池监视、日志管理、代码生成等基础模块。是SpringBlade的 JFinal版本！

## 鸣谢
1.[SpringBlade](http://u.720life.cn/g/1dbc517b01e71dde51eaf55b6f5fa83357d937bba06b5c3d9027f141fa14763056c8fb99f30255db954e65c0c7728573)
2.[JFinal](http://u.720life.cn/g/1dbc517b01e71dde51eaf55b6f5fa8333018ed342f2b9d69f897ca32ee70a26c)
3.[beetl](http://u.720life.cn/g/1dbc517b01e71dde51eaf55b6f5fa8333232f5bd30d25cf6f3497d7bfa3828e8)
4.[beetlsql](http://u.720life.cn/g/1dbc517b01e71dde51eaf55b6f5fa833162970b0284aabb90548394964ef043a710fdd2363d125a0664c0d95432aaa66)
5.[dreamlu](http://u.720life.cn/g/1dbc517b01e71dde51eaf55b6f5fa833071fa71f29e123a2adc72d3236f87c9f297755222392c459af7df912b8f3dd61)
6.[JFinalShiroPlugin](http://u.720life.cn/g/1dbc517b01e71dde51eaf55b6f5fa8333018ed342f2b9d69f897ca32ee70a26ceebc8762a2b7bafc52d1138da01c5041)

## 技术选型

1、后端

* 核心框架：JFinal
* 安全框架：Apache Shiro
* 服务端验证：Blade Validator
* 持久层框架：beetlsql
* 模板引擎：beetl
* 数据库连接池：Alibaba Druid
* 缓存框架：Ehcache
* 日志管理：SLF4J
* 工具类：Apache Commons、FastJson、JFinal-ueditor、BladeToolBox

2、前端

* JS框架：jQuery
* CSS框架：Bootstrap
* 客户端验证：JQuery-html5Validate
* 富文本：KindEditor、UEditor
* 数据表格：jqGrid
* 树结构控件：jQuery zTree
* 弹出层：Layer
* 日期控件： LayDate

## 部分后台界面
![后台界面](http://git.oschina.net/uploads/images/2016/1103/162134_4875c1d2_64709.png "后台界面")
![后台界面](http://git.oschina.net/uploads/images/2016/1103/162152_197d4be2_64709.png "后台界面")
![后台界面](http://git.oschina.net/uploads/images/2016/1103/162206_60005d2d_64709.png "后台界面")
![后台界面](http://git.oschina.net/uploads/images/2016/1103/162224_b80d40ad_64709.png "后台界面")

## 权限相关
1、配置文件 shiro.ini 配置默认规则
2、仅允许管理员访问 可在控制器配置 RequiresRoles 注解
3、允许权限表中配置的权限 可直接继承 UrlPermissController

注：
=======

jetty启动入口： com.ikkong.common.MainConfig.java
登陆名、密码 均为  admin





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3a703aeb9015fb58b180f8ea513d292597efdcb0b256fc7848e06c520322c9fca1817e3f9e46c599d500ecceb3b4f34b)