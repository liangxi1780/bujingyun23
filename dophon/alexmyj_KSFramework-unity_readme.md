
![KSFramework](Docs/KSFramework-logo.png)

[![Build status](https://ci.appveyor.com/api/projects/status/lt34ynvl3lac62ln/branch/master?svg=true)](https://ci.appveyor.com/project/mr-kelly/ksframework/branch/master)

[**K**Engine](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304692321edbee162c630f07d7f459bd096e1b30e07aea23db4cde03cf4877a9a41b) + [**S**Lua](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678019a6bcb6776d2d4f92ecf4f8dfe6f)|[XLua]https://github.com/Tencent/xLua **Framework** = KSFramework


**[KSFramework](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8b1f807ecf60a790843af82589332f86b9252ce93bfed337cf91e59193e7596)是一个整合KEngine、SLua或XLua、ILRuntime 5 Asset Bundle开发框架，并为程序、美术、策划、运营提供辅助工具集。**

---------------------

**热重载**是KSFramework的开发重点——在不重启游戏的前提下，重载代码、配置表可立刻看到修改效果，最大限度的提升开发、调试的速度，方便运营阶段热更新。

对于程序人员，可以使用AssetBundle加载与打包、脚本化的UI、配置表代码自动生成、下载更新等基础功能模块，大大减少游戏周边基础功能的工作量；

对于策划人员，使用Excel进行编辑，可以在编辑过程中添加注释、图标、预编译指令，KSFramework会根据配置内容自动生成代码供程序使用。

对于美术人员，只需将项目需要用到资源放到指定目录，将会自动的生成Asset Bundle；程序加载Asset Bundle跟Resources.Load一样方便。


对于运营人员，利用KSFramework的热重载特性，可以针对运营需求，在项目运行过程中配置表、脚本代码在用户无知觉的情况下进行热更新。

# 安装

可以从两种方式中选择其中一种，

## 方式1，从产品包安装

您可以从[KSFramework Release](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a8b1f807ecf60a790843af82589332f80bff9fc2c4a6b81b1d927951df389800)页面下载最新版本的产品包。

解压后直接用Unity打开KSFramework目录，或直接双击场景KSFramework/Assets/Game.unity。

> 如遇到无法下载的网络问题, 备选下载站:
> - [KSFramework Appveyor Artifacts](http://u.720life.cn/g/134499da667fce84d5b0b80ba6e1ebd79098c3a605934ce27d196f93c34181db71e859719974dfe7cd5184af1e31d35957e2bb2ec9e4f5a3ac730f660d702ca9121015856f92945dab0bc2676c604f8b): 包含每次提交的构建结果
> - [KSFramework OSChina镜像](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d31a0e73dfba1ed292d4bb7c87bea09d119ccbb7781738853a8a1bfe757983d00) 国内的镜像Git


## 方式2，从源码安装

获取到源码后，需要通过git submodule命令获取KEngine和SLua
```shell
git submodule init
git submodule update
```

拉取submodule后，Windows下双击执行源码Install.bat进行安装，把KEngine和SLua相关代码链接到KSFramework各目录，然后用Unity打开

# 教程

- [**KSFramework: Unity3D开发辅助框架快速入门**](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9edebbcf20a5513138c13771a8fafcdb767b5d91ebf0eddbb2fb53bc2752b561a8)
- [KEngine策划指南: 配置表格的编辑与编译](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e0ab2bd783b4f9aaac4742ed9eedf0fb5c4b9d7e358dcdbce6e83200b9b9ad5fc)
- [KEngine: 资源的打包、加载、调试监控](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e8119ebc30404fea0a86088905e3d7a343af94889e643b701a42eaae88ed69d58)
- [KSFramework常见问题：Lua脚本热重载，内存状态数据会不会丢失？](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e18374308d3213054e6de11d88f3125801aa23fae39ae702215752f091ae63812)
- [KSFramework常见问题：Excel如何进行SVN协作、差异比较？](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e8c3e12bac3fdf50248dfee1fdb73eb55ddb291449a9b74db9f0ceb831cb6ac10)
- [KEngine配置表：扩展表格解析类型](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9ec271b56c822a0d67bf041d76f71f64d5bae51f663a194e958b47c39a7c79b0ca)
- [KEngine:配置表的条件编译](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e07e53218b1a4f3f0c1b087972c68e4a595c27f0827a03a3a29845c3569d20969)

# 文档

- [【查看完整文档】](http://u.720life.cn/g/e4a92fc4ad555a3a77e1e3da6bbe42cf23f3ecb454b15a73f3fe62c08dafac3bb4107a79a85cf43f0adb0e0f3cc41454)
- [功能特性](http://u.720life.cn/g/e4a92fc4ad555a3a77e1e3da6bbe42cf23f3ecb454b15a73f3fe62c08dafac3b8510357faabd3e52d71084c801f07ebed1252dcaeaf83f5ac0d7b7a3fa84a69f)
- [策划指南：配置表的使用](http://u.720life.cn/g/e4a92fc4ad555a3a77e1e3da6bbe42cf23f3ecb454b15a73f3fe62c08dafac3b2917cd46cb6f6e237a0bf40359c852af6adfcf9a9a3491acbda22243ac27f2ed)

...

# 结构组成

![KSFramework由KEngine和SLua结合组成](Docs/Structure.png)

# 涉及第三方库

- [SLua:基于Unity的Lua引擎，也可用于C#独立程序](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465ba8a9266206eb3be0fe58f919281b28bdc7d8bfdb4911c768281c8db1846e10)
- [xLua is a lua programming solution for C# ( Unity, .Net, Mono) , it supports android, ios, windows, linux, osx, etc.](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046feb499908ec86c7d70c81bade9b36765),从XLua分支获取
- [ILRuntime项目为基于C#的平台（例如Unity）提供了一个纯C#实现，快速、方便且可靠的IL运行时，使得能够在不支持JIT的硬件环境（如iOS）能够实现代码的热更新](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461739ab85cf701970d1e00fa439de37c2ee6ba8c67f3131e434eb0a0b10f66565) ,从ILRuntime分支获取
- [KEngine:AssetBundle打包加载框架](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304692321edbee162c630f07d7f459bd096e1b30e07aea23db4cde03cf4877a9a41b)
  - [ini-parser:Ini配置文件解析器，支持多文件合并](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466b80a517f8f8661d927c6caae6dbec12b18ffe941bd9f43ccca1ff785874caff)
  - [Premake:VS工程生成](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c05cd3b91ed380b066c01ee742536d23663318a9514655cc5f3db398350830f3)
- [TableML:表格标记语言，运行时与编译器](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467950affe1ad7b4d404a9e36748b92a3baebea1845b3a870c21582aa13e94ac50)
  - [NPOI:强大的Excel读写库](http://u.720life.cn/g/9dc0bab007a5d86377911954dffdff3002470258079089edb14b43bd5eec7fa6)
    - [ISharpZipLib:Zip格式读写库](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046be84eba58c6dd4042a21db235b376eca7cd76f1dcb35268324b2f5658ea1abba)
  - [DotLiquid:模板语言引擎](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c46e21ae932bead891849d38525296e83ea1724b385dc6f27decb815778d6a25)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb4154a0969769a3abae0c6a2d0478229c7fb8501b7827f0488e6b55ab3a3ee7c90a8604c86a69ddf46057bffb745cf8bcd0feb7f50530d74e2ea5bf5d604a1b4)