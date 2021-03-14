## 魔方 NewLife.Cube
魔方 是一个基于 ASP.NET MVC 的 用户权限管理平台，可作为各种信息管理系统的基础框架。

源码： https://github.com/NewLifeX/NewLife.Cube  
演示：[http://cube.newlifex.com](http://u.720life.cn/g/4655d9117043739bd057f6e4541ffee76ca98531facc8ddee49fed3cf1657824) [源码](http://u.720life.cn/g/939ad666a2cfd771f2e999fba1f71ee5aba6fa803060d41c77dcf2dadb64bc60c9b224603147e2c056ff88810eb0edf4)  

---
### 特性
* 通用权限管理，用户、角色、菜单、权限，支持控制器Action权限控制
* 多数据库，支持 `SQLite / Sql Server / Oracle / MySql / SqlCe / Access` 
* 免部署，系统自动创建数据库表结构，以及初始化数据，无需人工干涉
* 强大的视图引擎，支持子项目视图重写父项目相同位置视图，任意覆盖修改默认界面

---
### 系统要求
* [IIS 7.0](http://u.720life.cn/g/29d9369db99598358fdb154d794648688d06f5928626f258766d3f6308e37626)
* [.NET Framework 4.5](http://u.720life.cn/g/43d8d3d99c8fd8af6c240816f866ce0cdffc38afc19bf609838a5e7d0ae1c8e0480872d1c57f7edae7269e6f68aafeae2e299aeadd241b0015c17721ff26f8f8)
* [ASP.NET MVC 5](http://u.720life.cn/g/7b22188e20b0d12293a7ac3741ba1c13293b678c312e32c90986619044602ca64c1b719a381bb1eda50232e2f6e5a272)
* [SQLite](http://u.720life.cn/g/084e08ae90031c8a5f221733ad029715662b90fc9bc10feefd549a106715acc13c659e3949ff4bb07e006979d99a72f71c5a46fdc0bbe7c1b0e11ba33e48358f2beaa8efc3cba0ede976568cf987081e) / Sql Server / Oracle / MySql / SqlCe / Access

---
### 安装
* 在 *Visual Studio* 中新建MVC5项目
* 通过 *NuGet* 引用`NewLife.Cube`，或自己编译最新的[魔方](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d30dd7cda8f253ade13defbc9640d828358d7487d5942081a2d67cd94988d60bd2)源码
* 在`Web.config`的` `段设置名为`Membership`的连接字符串，用户角色权限菜单等存储在该数据库
* 系统自动识别数据库类型，默认`\ `
* 编译项目，项目上点击鼠标右键，`查看`，`在浏览器中查看`，运行魔方平台
* 系统为`SQLite`/`Oracle`/`MySql`/`SqlCe`数据库自动下载匹配（`x86/x64`）的数据库驱动文件，驱动下载地址可在`Config\Core.config`中修改`PluginServer`
* 系统自动下载脚本样式表等资源文件，下载地址可在`Config/Cube.config`中修改`PluginServer`
* 默认登录用户名是`admin`，密码是`admin`
* 推荐安装 *Visual Studio* 插件 *Razor Generator*，给`.cshtml`文件设置`自定义工具``RazorGenerator`，可以把`.cshtml`编译生成到`DLL`里面
* 项目发布时只需要拷贝`Bin`、`web.config`、`Global.asax`，以及其它自己添加的资源文件

---
### 教程
[【演示】教务系统](http://u.720life.cn/g/4655d9117043739bd057f6e4541ffee76ca98531facc8ddee49fed3cf1657824)  
[【源码】教务系统](http://u.720life.cn/g/939ad666a2cfd771f2e999fba1f71ee5aba6fa803060d41c77dcf2dadb64bc60c9b224603147e2c056ff88810eb0edf4)  

[【教程】魔方平台NewLife.Cube基础教程（附例程源码）](http://u.720life.cn/g/c121359f48414f9252bafe84eca571da5a2661c96482e499863ef60d066050c424753850491491ff433f7555c885622f)  
[【教程】魔方平台NewLife.Cube模板结构详解](http://u.720life.cn/g/c121359f48414f9252bafe84eca571da5a2661c96482e499863ef60d066050c43cb10c74d86f472df1807d449c620b1e)  




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e6962aba638ed677007c0e5d1a1c31db24c871c8885a3184afd54d21dbf82d269defbaf197f18ce277f4d5874a6749577)