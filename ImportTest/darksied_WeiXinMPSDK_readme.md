 

Senparc.Weixin —— 微信 .NET SDK 
=================
 
 
[![Build Status](https://travis-ci.org/JeffreySu/WeiXinMPSDK.svg?branch=master)](https://travis-ci.org/JeffreySu/WeiXinMPSDK)
[![NuGet](https://img.shields.io/nuget/dt/Senparc.Weixin.MP.svg)](https://www.nuget.org/packages/Senparc.Weixin.MP)
[![GitHub commit activity the past week, 4 weeks, year](https://img.shields.io/github/commit-activity/4w/JeffreySu/WeiXinMPSDK.svg)](https://github.com/JeffreySu/WeiXinMPSDK/commits/master)
[![license](https://img.shields.io/github/license/JeffreySu/WeiXinMPSDK.svg)](http://www.apache.org/licenses/LICENSE-2.0)

[[English Version]](readme.en.md)

使用 Senparc.Weixin，您可以方便快速地开发微信全平台的应用（包括微信公众号、小程序、小游戏、企业号、开放平台、微信支付、JS-SDK、微信硬件/蓝牙，等等）。

目前 Senparc.Weixin 已经支持几乎所有微信平台模块和接口，并同时支持 
[.NET 3.5 / 4.0 / 4.5 / .NET Core 2.0 / .NET Core 2.1](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0edb7971d861ceb82c3231a5130cd74551dc39eed3f3419ed5374cc7cf2e1e1dec) 多种框架。

Senparc.Weixin SDK 是目前使用率最高的微信 .NET SDK，也是国内最受欢迎的 .NET 开源项目之一。

立项五年多来，我们一直保持着项目的持续更新，将完整的源代码以及设计思想毫无保留地分享给大家，希望有更多的人可以从中受益，理解并传播开源的精神，一同助力中国开源事业！感恩一路上给我们提供帮助的朋友们！

如果你喜欢并希望我们继续优化这个项目，请给我们一个 ★Star ：)

## 公告
> _Senparc.Weixin SDK 全系列将从 2018年12月24日起停止对 .NET Framework 3.5 的更新。历史稳定版本仍然可用。_


  -->
 


 

下文索引
----------------

* [各模块类库](#各模块类库)
* [私人定制你的微信项目 Sample](#私人定制你的微信项目-sample)
* [资源](#资源)
* [:book: Senparc 官方图书教程](#senparc-官方图书教程)
* [:computer: Senparc 官方视频教程](#senparc-官方视频教程)
* [贡献代码](#贡献代码)
* [如何使用.net core开发](#如何使用net-core开发)
* [关注测试账号（SenparcRobot）](#关注测试账号senparcrobot)
* [项目文件夹说明（src文件夹下）](#项目文件夹说明src文件夹下)
* [Demo 文件夹说明（Samples文件夹下）](#demo-文件夹说明samples文件夹下)
* [Senparc.Weixin.MP.Sample中的关键代码说明](#senparcweixinmpsample中的关键代码说明)
    * [/Controllers/WeixinController.cs](#controllersweixincontrollercs)
    * [如何处理微信公众账号请求](#如何处理微信公众账号请求)
* [使用Nuget安装到项目中](#使用nuget安装到项目中)
* [如何开发小程序](#如何开发小程序)  
* [如何部署](#如何部署)
* [各分支说明](#各分支说明)
* [感谢贡献者](#感谢贡献者)
* [捐助](#捐助)
* [License](#license)

本库为包含了 .NET 3.5/4.0/4.5/.NET Core 2.0/2.1 多个版本的源代码（核心逻辑完全一致）：

* 使用 Visual Studio 2017 打开 Demo（支持所有版本）：[Senparc.Weixin.MP.Sample.vs2017.sln](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0edb7971d861ceb82c3231a5130cd745512d0b67d429777cddec05e9f29f89ab5b364919c71039e73686d501be6b6dbb4152968e8526c3079866a9ae1b257f1877)
* 使用其他版本 Visual Studio 打开 Demo（仅支持 .NET 4.5）：[Senparc.Weixin.MP.Sample.sln](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0edb7971d861ceb82c3231a5130cd745512d0b67d429777cddec05e9f29f89ab5b364919c71039e73686d501be6b6dbb41b1fc46349c7e4b1c330c0ed5e075dcf7)
* 使用 Visual Studio 2010 SP1 打开 Demo（仅支持 .NET 4.5）：[Senparc.Weixin.MP.Sample.vs2010sp1.sln](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0edb7971d861ceb82c3231a5130cd745512d0b67d429777cddec05e9f29f89ab5b364919c71039e73686d501be6b6dbb41b1fc46349c7e4b1c330c0ed5e075dcf7)


各模块类库
----------------

| # | 模块功能                                            | DLL                                             | Nuget                          | 支持 .NET 版本 
|---|----------------------------------------------------|-------------------------------------------------|---------------------------------------|--------------------------------------
| 1| 基础库                                               |Senparc.Weixin.dll                               | [![Senparc.Weixin][1.1]][1.2] [![Senparc.Weixin][nuget-img-base]][nuget-url-base]  |  ![.NET 3.5][net35Y]    ![.NET 4.0][net40Y]   ![.NET 4.5][net45Y]    ![.NET Core 2.0][core20Y]
| 2| 微信公众号 /  JSSDK / 摇周边  等等 |Senparc.Weixin.MP.dll                           | [![MP][2.1]][2.2] [![MP][nuget-img-mp]][nuget-url-mp]  |   ![.NET 3.5][net35Y]    ![.NET 4.0][net40Y]   ![.NET 4.5][net45Y]    ![.NET Core 2.0][core20Y]
| 3| [微信小程序 （支持小游戏） （独立项目）](https://github.com/JeffreySu/WxOpen)  |Senparc.Weixin.WxOpen.dll  |  [![WxOpen][9.1]][9.2] [![WxOpen][nuget-img-wxopen]][nuget-url-wxopen] |   ![.NET 3.5][net35N]  ![.NET 4.0][net40Y]  ![.NET 4.5][net45Y]  ![.NET Core 2.0][core20Y]
| 4| 微信支付                                             |Senparc.Weixin.TenPay.dll  |  [![TenPay][12.1]][12.2] [![TenPay][nuget-img-tenpay]][nuget-url-tenpay] |   ![.NET 3.5][net35Y]  ![.NET 4.0][net40Y]  ![.NET 4.5][net45Y]  ![.NET Core 2.0][core20Y]
| 5| ASP.NET MVC 扩展 .NET Framework +  Core               |Senparc.Weixin.MP.MVC.dll                 | [![MP.MVC][3.1]][3.2] [![Mvc][nuget-img-mvc]][nuget-url-mvc] | ![.NET 3.5][net35N]    ![.NET 4.0][net40Y]   ![.NET 4.5][net45Y] ![.NET Core 2.0][core20Y]
| 6| 微信企业号                                           |Senparc.Weixin.QY.dll                            | [![QY][4.1]][4.2] [![QY][nuget-img-qy]][nuget-url-qy]  |    ![.NET 3.5][net35Y] ![.NET 4.0][net40Y] ![.NET 4.5][net45Y] ![.NET Core 2.0][core20Y]
| 7| 企业微信                                             |Senparc.Weixin.Work.dll                          | [![Work][5.1]][5.2] [![Work][nuget-img-work]][nuget-url-work]  |   ![.NET 3.5][net35Y]    ![.NET 4.0][net40Y]   ![.NET 4.5][net45Y]    ![.NET Core 2.0][core20Y]
| 8| 微信开放平台                                         |Senparc.Weixin.Open.dll                          | [![Open][6.1]][6.2] [![Open][nuget-img-open]][nuget-url-open]|  ![.NET 3.5][net35Y]    ![.NET 4.0][net40Y]   ![.NET 4.5][net45Y]    ![.NET Core 2.0][core20Y]
| 9| Redis 分布式缓存                                     |Senparc.Weixin.Cache. Redis.dll               | [![Cache.Redis][7.1]][7.2] [![Redis][nuget-img-redis]][nuget-url-redis] |    ![.NET 3.5][net35N]    ![.NET 4.0][net40N]   ![.NET 4.5][net45Y]    ![.NET Core 2.0][core20Y]
| 10| Memcached   分布式缓存                            |Senparc.Weixin.Cache. Memcached.dll           | [![Cache.Memcached][8.1]][8.2] [![MC][nuget-img-mc]][nuget-url-mc] |  ![.NET 3.5][net35N]    ![.NET 4.0][net40N]   ![.NET 4.5][net45Y]    ![.NET Core 2.0][core20Y]
| 11| [WebSocket  （独立项目）](https://github.com/JeffreySu/Senparc.WebSocket)    |Senparc.WebSocket.dll |  [![Senparc.WebSocket][10.1]][10.2] [![WebSocket][nuget-img-ws]][nuget-url-ws]  |   ![.NET 3.5][net35N]    ![.NET 4.0][net40N]   ![.NET 4.5][net45Y]    ![.NET Core 2.0][core20Y]


| ![.NET 3.5][net35Y] | ![.NET 4.0][net40Y] | ![.NET 4.5][net45Y] | ![.NET Core 2.x][core20Y] |
|--|--|--|--|
| .NET 3.5            | .NET 4.0            | .NET 4.5            |  .NET Core 2.0 + 2.1       |

[1.1]: https://img.shields.io/nuget/v/Senparc.Weixin.svg?style=flat
[1.2]: https://www.nuget.org/packages/Senparc.Weixin
[2.1]: https://img.shields.io/nuget/v/Senparc.Weixin.MP.svg?style=flat
[2.2]: https://www.nuget.org/packages/Senparc.Weixin.MP
[3.1]: https://img.shields.io/nuget/v/Senparc.Weixin.MP.MVC.svg?style=flat
[3.2]: https://www.nuget.org/packages/Senparc.Weixin.MP.MVC
[4.1]: https://img.shields.io/nuget/v/Senparc.Weixin.QY.svg?style=flat
[4.2]: https://www.nuget.org/packages/Senparc.Weixin.QY 
[5.1]: https://img.shields.io/nuget/v/Senparc.Weixin.Work.svg?style=flat
[5.2]: https://www.nuget.org/packages/Senparc.Weixin.Work
[6.1]: https://img.shields.io/nuget/v/Senparc.Weixin.Open.svg?style=flat
[6.2]: https://www.nuget.org/packages/Senparc.Weixin.Open
[7.1]: https://img.shields.io/nuget/v/Senparc.Weixin.Cache.Redis.svg?style=flat
[7.2]: https://www.nuget.org/packages/Senparc.Weixin.Cache.Redis
[8.1]: https://img.shields.io/nuget/v/Senparc.Weixin.Cache.Memcached.svg?style=flat
[8.2]: https://www.nuget.org/packages/Senparc.Weixin.Cache.Memcached
[9.1]: https://img.shields.io/nuget/v/Senparc.Weixin.WxOpen.svg?style=flat
[9.2]: https://www.nuget.org/packages/Senparc.Weixin.WxOpen
[10.1]: https://img.shields.io/nuget/v/Senparc.WebSocket.svg?style=flat
[10.2]: https://www.nuget.org/packages/Senparc.WebSocket
[11.1]: https://img.shields.io/nuget/v/Senparc.Weixin.MP.CoreMVC.svg?style=flat
[11.2]: https://www.nuget.org/packages/Senparc.Weixin.MP.CoreMVC
[12.1]: https://img.shields.io/nuget/v/Senparc.Weixin.TenPay.svg?style=flat
[12.2]: https://www.nuget.org/packages/Senparc.Weixin.TenPay

[net35Y]: https://img.shields.io/badge/3.5-Y-brightgreen.svg
[net35N]: https://img.shields.io/badge/3.5-N-lightgrey.svg
[net40Y]: https://img.shields.io/badge/4.0-Y-brightgreen.svg
[net40N]: https://img.shields.io/badge/4.0-N-lightgrey.svg
[net40N-]: https://img.shields.io/badge/4.0----lightgrey.svg
[net45Y]: https://img.shields.io/badge/4.5-Y-brightgreen.svg
[net45N]: https://img.shields.io/badge/4.5-N-lightgrey.svg
[net45N-]: https://img.shields.io/badge/4.5----lightgrey.svg
[net461Y]: https://img.shields.io/badge/4.6.1-Y-brightgreen.svg
[net461N]: https://img.shields.io/badge/4.6.1-N-lightgrey.svg
[coreY]: https://img.shields.io/badge/core-Y-brightgreen.svg
[coreN]: https://img.shields.io/badge/core-N-lightgrey.svg
[coreN-]: https://img.shields.io/badge/core----lightgrey.svg
[core20Y]: https://img.shields.io/badge/core2.x-Y-brightgreen.svg
[core20N]: https://img.shields.io/badge/core2.x-N-lightgrey.svg

[nuget-img-base]: https://img.shields.io/nuget/dt/Senparc.Weixin.svg
[nuget-url-base]: https://www.nuget.org/packages/Senparc.Weixin
[nuget-img-mp]: https://img.shields.io/nuget/dt/Senparc.Weixin.MP.svg
[nuget-url-mp]: https://www.nuget.org/packages/Senparc.Weixin.MP
[nuget-img-mvc]: https://img.shields.io/nuget/dt/Senparc.Weixin.MP.Mvc.svg
[nuget-url-mvc]: https://www.nuget.org/packages/Senparc.Weixin.MP.Mvc
[nuget-img-tenpay]: https://img.shields.io/nuget/dt/Senparc.Weixin.TenPay.svg
[nuget-url-tenpay]: https://www.nuget.org/packages/Senparc.Weixin.TenPay
[nuget-img-qy]: https://img.shields.io/nuget/dt/Senparc.Weixin.QY.svg
[nuget-url-qy]: https://www.nuget.org/packages/Senparc.Weixin.QY
[nuget-img-work]: https://img.shields.io/nuget/dt/Senparc.Weixin.Work.svg
[nuget-url-work]: https://www.nuget.org/packages/Senparc.Weixin.Work
[nuget-img-open]: https://img.shields.io/nuget/dt/Senparc.Weixin.Open.svg
[nuget-url-open]: https://www.nuget.org/packages/Senparc.Weixin.Open
[nuget-img-redis]: https://img.shields.io/nuget/dt/Senparc.Weixin.Cache.Redis.svg
[nuget-url-redis]: https://www.nuget.org/packages/Senparc.Weixin.Cache.Redis
[nuget-img-mc]: https://img.shields.io/nuget/dt/Senparc.Weixin.Cache.Memcached.svg
[nuget-url-mc]: https://www.nuget.org/packages/Senparc.Weixin.Cache.Memcached
[nuget-img-wxopen]: https://img.shields.io/nuget/dt/Senparc.Weixin.WxOpen.svg
[nuget-url-wxopen]: https://www.nuget.org/packages/Senparc.Weixin.WxOpen
[nuget-img-ws]: https://img.shields.io/nuget/dt/Senparc.WebSocket.svg
[nuget-url-ws]: https://www.nuget.org/packages/Senparc.WebSocket


* 已经支持所有微信6 API，包括自定义菜单/个性化菜单、模板信息接口、素材上传接口、群发接口、多客服接口、支付接口、微小店接口、卡券接口等等。
* 已经支持用户会话上下文（解决服务器无法使用 Session 处理用户信息的问题）。
* 已经全面支持微信公众号、企业号、开放平台的最新 API。
* 已经支持分布式缓存及缓存策略扩展。

> 目前官方的 API 都已完美集成，除非有特殊说明，所有升级都会尽量确保向下兼容，所以已经发布的版本请放心使用或直接升级（覆盖）最新的 dll，[Release生成目录](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e230c727acd71aa454e6fe2e4ebdf63600edcc47fa094cfda2dde0c4a9b46d5108f80962d4ca4037a6e9b97656f9933884ea99fbf548597c6c49e253b8e4f3058)，建议使用 [Nuget]() 进行更新。



## 私人定制你的微信项目 Sample

1. 方法：登录  https://weixin.senparc.com/User 下载 WeChatSampleBuilder 工具，并查看使用说明；
2. 打开 WeChatSampleBuilder.exe，在 `Source Peoject Path` 中选择克隆了本项目的本地文件夹（根目录），根据需要配置 Sample 项目类型、需要生成的类库 .NET 版本、所需使用的微信模块，以及支持缓存类型；
3. 点击 Build 按钮，即可在同级目录下看到 `OutputSample` 开头的文件夹，并自动打开解决方案！

 


资源
----------------
1. 官网地址：http://weixin.senparc.com/
2. 在线 Demo 地址：http://sdk.weixin.senparc.com/
3. 微信开发系列教程：http://www.cnblogs.com/szw/p/weixin-course-index.html
4. 微信技术交流社区：http://weixin.senparc.com/QA
5. 自定义菜单在线编辑工具：http://sdk.weixin.senparc.com/Menu
6. 在线消息测试工具：http://sdk.weixin.senparc.com/SimulateTool
7. 缓存测试工具：http://sdk.weixin.senparc.com/Cache/Test
8. chm帮助文档下载：http://sdk.weixin.senparc.com/Document
9. 源代码及最新更新：https://github.com/JeffreySu/WeiXinMPSDK
10. 微信开发资源集合：https://github.com/JeffreySu/WeixinResource
11. 《微信开发深度解析》阅读辅助系统：https://book.weixin.senparc.com
12. 购买《微信开发深度解析》：[https://item.jd.com/12220004.html](http://u.720life.cn/g/58c34c411e53b9427017785d88b345f54ad78da7bc38b910ccaf6e8324d1bda54e85282fb4996cfb5284bae005849b24a152acb05fab4db9444a52d4948593fe2db4c525b3864a5183a5655895bf5249)
13. 《微信公众号 + 小程序快速开发》视频教程：[https://github.com/JeffreySu/WechatVideoCourse](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046124662392b5b95cdb729990341fe96ffa5a1a2dcd3b5451ed7b7134f2176ca20)

* 技术交流QQ群：

> 14群（视频课程学员群）：588231256 
> 15群（公众号）：289181996 
> 10群（分布式缓存群）：246860933 
> 12群（微信小程序）：108830388 
> 16群（开放平台）：860626938 
> *`以下群已满：`* 
> `1群：300313885（已满），2群：293958349（已满），3群：342319110（已满）` 
> `4群：372212092（已满），5群：377815480（已满），6群：425898825（已满）` 
> `7群：482942254（已满），8群：106230270（已满），9群：539061281（已满）` 
> `11群：553198593（已满），13群：183424136（开放平台，已满）`

* 业务联系QQ：498977166

 

如果这个项目对您有用，我们欢迎各方任何形式的捐助，也包括参与到项目代码更新或意见反馈中来。谢谢！


资金捐助：[进入](http://u.720life.cn/g/7d3743023a6594b5e5077ad06104a21314a391a225350386a79c3c133f0578a629b0f05227517c85bf3b195ed6222011)


Senparc 官方图书教程
----------------

 

> 由 Jeffrey Su 和盛派团队耗时 2 年完成的微信开发图书已经出版，书名：《微信开发深度解析：公众号、小程序高效开发秘籍》，全书配套辅助阅读系统已经上线： [BookHelper](http://u.720life.cn/g/7bb62a43e091a0c2542eaa1e24912633f06a13b9f0969cba1a7b11c9a37a228c)。 
> 欢迎购买正版图书：[【购买正版】](http://u.720life.cn/g/58c34c411e53b9427017785d88b345f54ad78da7bc38b910ccaf6e8324d1bda54e85282fb4996cfb5284bae005849b2405970f9968ed8d769f49bdd15dd72891) 
> 图书出版时的代码版本快照见分支 [BookVersion1](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e99abb27e977c61c1ed0cb307506f501cab8e4249c0ab724081c28fcf58d02f0b)。


Senparc 官方视频教程
----------------

> 为了帮助大家更直观地了解微信开发细节，同时结合《微信开发深度解析》图书进行学习，我们成立“盛派课堂”小组，开设了微信开发视频课程，帮助大家从多个维度学习微信开发以及 .NET 开发过程中的诸多技巧。 
> 视频包含两大部分： 
> 1. 微信开发基础技能 
> 2. 公众号及小程序案例实战 
> 
> 共计 60 课时，配有番外篇。 
> 目前视频已经在网易云课堂上线，课程制作精良、内容充实，被选为“A”级课程，[【观看视频】](http://u.720life.cn/g/58c34c411e53b9427017785d88b345f54ad78da7bc38b910ccaf6e8324d1bda558c1e7299c39dd3471a1cdf2672679c387effac54d78a061861b70a726622d4b26cf0897b12081e737d125ff68a8907a)，[【查看课程代码及课件】]https://github.com/JeffreySu/WechatVideoCourse


### 关注测试账号体验功能（SenparcRobot）：
|盛派网络小助手公众号|盛派网络小助手小程序|BookHelper|
|--|--|--|
|   |   |   |

## 如何使用.NET Core开发

> 当前分支包含了 .NET Framework 3.5 / 4.0 / 4.5 / 4.6.1 及 .NET Core 2.0 / 2.1 的全版本代码。 
> 其中 .NET Framework 4.5 的 Demo 位于 `/src/Senparc.Weixin.MP.Sample` 目录下， 
> .NET Core 2.0 的 Demo 位于 `/src/Senparc.Weixin.MP.Sample.vs2017` 目录下。 
> 注意：以上两个 Demo 所引用的 Senparc.Weixin SDK 库源代码是完全一致的，只是在编译运行的时候会根据条件自动选择输出版本。

> 以下所有介绍以 .NET Framework 4.5 版本为例。

## 贡献代码

> 如果需要使用或修改此项目的源代码，建议先Fork。也欢迎将您修改的通用版本Pull Request过来。

1. Fork
2. 创建您的特性分支 (`git checkout -b my-new-feature`)
3. 提交您的改动 (`git commit -am 'Added some feature'`)
4. 将您的修改记录提交到远程 `git` 仓库 (`git push origin my-new-feature`)
5. 然后到 github 网站的该 `git` 远程仓库的 `my-new-feature` 分支下发起 Pull Request
（请提交到 `Developer` 分支，不要直接提交到 `master` 分支）


## 项目文件夹说明（src文件夹下）

| 文件夹 | 说明 |
|--------|--------|
|[Senparc.WebSocket](src/Senparc.WebSocket/)|WebSocket 模块|
|[Senparc.Weixin.Cache](src/Senparc.Weixin.Cache)							|Senparc.Weixin.Cache.Memcached.dll 、 Senparc.Weixin.Cache.Redis.dll 等分布式缓存扩展方案|
|[Senparc.Weixin.MP.BuildOutPut](src/Senparc.Weixin.MP.BuildOutPut)		    |所有最新版本DLL发布文件夹|
|[Senparc.Weixin.MP.MvcExtension](src/Senparc.Weixin.MP.MvcExtension)		|Senparc.Weixin.MP.MvcExtension.dll源码，为 MVC 项目提供的扩展包 |
|[Senparc.Weixin.MP](src/Senparc.Weixin.MP)									|Senparc.Weixin.MP.dll 微信公众账号SDK源代码|
|[Senparc.Weixin.Open](src/Senparc.Weixin.Open)								|Senparc.Weixin.Open.dll 第三方开放平台SDK源代码|
|[Senparc.Weixin.QY](src/Senparc.Weixin.QY)									|Senparc.Weixin.QY.dll 微信企业号SDK源代码|
|[Senparc.Weixin.Work](src/Senparc.Weixin.Work)								|Senparc.Weixin.Work.dll 企业微信SDK源代码|
|[Senparc.Weixin.WxOpen](src/Senparc.Weixin.WxOpen)							|Senparc.Weixin.WxOpen.dll 微信小程序SDK源代码，包括小游戏|
|[Senparc.Weixin](src/Senparc.Weixin)										|所有Senparc.Weixin.[x].dll 基础类库源代码|


## Demo 文件夹说明（Samples文件夹下）

| 文件夹 | 说明 |
|--------|--------|
|[Senparc.Weixin.MP.Sample](Samples/Senparc.Weixin.MP.Sample)						|可以直接发布使用的Demo（.NET Framework 4.5 + ASP.NET MVC）|
|[Senparc.Weixin.MP.Sample.WebForms](Samples/Senparc.Weixin.MP.Sample.WebForms)		|可以直接发布使用的Demo（.NET Framework 4.5 + + ASP.NET WebForms）|
|[Senparc.Weixin.MP.Sample.vs2017](Samples/Senparc.Weixin.MP.Sample.vs2017)			|可以直接发布使用的Demo（.NET Core 2.0 + MVC）|


## Senparc.Weixin.MP.Sample中的关键代码说明

>注：这是MVC项目，WebForms项目见对应Demo中的Weixin.aspx。

### /Controllers/WeixinController.cs

下面的Token需要和微信公众平台后台设置的Token同步，如果经常更换建议写入Web.config等配置文件（实际使用过程中两列建议使用数字+英文大小写改写Token，Token一旦被破解，微信请求将很容易被伪造！）：
```C#
public readonly string Token = "weixin";
```
下面这个Action（Get）用于接收并返回微信后台Url的验证结果，无需改动。地址如：http://domain/Weixin 或 http://domain/Weixin/Index
```C#
///  
/// 微信后台验证地址（使用Get），微信后台的“接口配置信息”的Url填写如：http://weixin.senparc.com/weixin
///  
[HttpGet]
[ActionName("Index")]
public ActionResult Get(PostModel postModel, string echostr)
{
    if (CheckSignature.Check(postModel.Signature, postModel.Timestamp, postModel.Nonce, Token))
    {
        return Content(echostr); //返回随机字符串则表示验证通过
    }
    else
    {
        return Content("failed:" + postModel.Signature + "," 
            + MP.CheckSignature.GetSignature(postModel.Timestamp, postModel.Nonce, Token) + "。" +
            "如果你在浏览器中看到这句话，说明此地址可以被作为微信公众账号后台的Url，请注意保持Token一致。");
    }
}
```
上述方法中的PostModel是一个包括了了Signature、Timestamp、Nonce（由微信服务器通过请求时的Url参数传入），以及AppId、Token、EncodingAESKey等一系列内部敏感的信息（需要自行传入）的实体类，同时也会在后面用到。


下面这个Action（Post）用于接收来自微信服务器的Post请求（通常由用户发起），这里的if必不可少，之前的Get只提供微信后台保存Url时的验证，每次Post必须重新验证，否则很容易伪造请求。
```C#
///  
/// 用户发送消息后，微信平台自动Post一个请求到这里，并等待响应XML
///  
[HttpPost]
[ActionName("Index")]
public ActionResult Post(PostModel postModel)
{
    if (!CheckSignature.Check(postModel.Signature, postModel.Timestamp, postModel.Nonce, Token))
    {
        return Content("参数错误！");
    }
    ...
}
```
### 如何处理微信公众账号请求？

Senparc.Weixin.MP提供了2中处理请求的方式，[传统方法](https://github.com/JeffreySu/WeiXinMPSDK/wiki/处理微信信息的常规方法)及使用[MessageHandler](https://github.com/JeffreySu/WeiXinMPSDK/wiki/%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8MessageHandler%E7%AE%80%E5%8C%96%E6%B6%88%E6%81%AF%E5%A4%84%E7%90%86%E6%B5%81%E7%A8%8B)处理方法（推荐）。上面两个方法在wiki中已经有比较详细的说明，这里简单举例MessageHandler的处理方法。

MessageHandler的处理流程非常简单：
``` C#
[HttpPost]
[ActionName("Index")]
public ActionResult Post(PostModel postModel)
{
    if (!CheckSignature.Check(postModel.Signature, postModel.Timestamp, postModel.Nonce, Token))
    {
        return Content("参数错误！");
    }

    postModel.Token = Token;
    postModel.EncodingAESKey = EncodingAESKey;//根据自己后台的设置保持一致
    postModel.AppId = AppId;//根据自己后台的设置保持一致

    var messageHandler = new CustomMessageHandler(Request.InputStream, postModel);//接收消息（第一步）

    messageHandler.Execute();//执行微信处理过程（第二步）

    return new FixWeixinBugWeixinResult(messageHandler);//返回（第三步）
}
```
整个消息除了postModel的赋值以外，接收（第一步）、处理（第二步）、返回（第三步）分别只需要一行代码。

上述代码中的CustomMessageHandler是一个自定义的类，继承自Senparc.Weixin.MP.MessageHandler.cs。MessageHandler是一个抽象类，包含了执行各种不同请求类型的抽象方法（如文字，语音，位置、图片等等），我们只需要在自己创建的CustomMessageHandler中逐个实现这些方法就可以了。刚建好的CustomMessageHandler.cs如下：

```C#
using System;
using System.IO;
using Senparc.Weixin.MP.MessageHandlers;
using Senparc.Weixin.MP.Entities;

namespace Senparc.Weixin.MP.Sample.CustomerMessageHandler
{
    public class CustomMessageHandler : MessageHandler 
    {
        public public CustomMessageHandler(Stream inputStream, PostModel postModel, int maxRecordCount = 0)
            : base(inputStream, postModel, maxRecordCount)
        {

        }

        public override IResponseMessageBase DefaultResponseMessage(IRequestMessageBase requestMessage)
        {
            //ResponseMessageText也可以是News等其他类型
            var responseMessage = CreateResponseMessage ();
            responseMessage.Content = "这条消息来自DefaultResponseMessage。";
            return responseMessage;
        }

        public override IResponseMessageBase OnTextRequest(RequestMessageText requestMessage)
        {
            //...
        }

        public override IResponseMessageBase OnVoiceRequest(RequestMessageVoice requestMessage)
        {
            //...
        }

        //更多没有重写的OnXX方法，将默认返回DefaultResponseMessage中的结果。
        ....
    }
}
```

其中OnTextRequest、OnVoiceRequest等分别对应了接收文字、语音等不同的请求类型。

比如我们需要对文字类型请求做出回应，只需要完善OnTextRequest方法：
```C#
      public override IResponseMessageBase OnTextRequest(RequestMessageText requestMessage)
      {
          //TODO:这里的逻辑可以交给Service处理具体信息，参考OnLocationRequest方法或/Service/LocationSercice.cs
          var responseMessage = CreateResponseMessage ();
          responseMessage.Content = string.Format("您刚才发送了文字信息：{0}", requestMessage.Content);
          return responseMessage;
      }
```
这样CustomMessageHandler在执行messageHandler.Execute()的时候，如果发现请求信息的类型是文本，会自动调用以上代码，并返回代码中的responseMessage作为返回信息。responseMessage可以是IResponseMessageBase接口下的任何类型（包括文字、新闻、多媒体等格式）。

从v0.4.0开始，MessageHandler增加了对用户会话上下文的支持，用于解决服务器上无法使用Session管理用户会话的缺陷。详见：[用户上下文WeixinContext和MessageContext](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e54efea5a9677d4e416e82d72631f761a23ac4f67dfee0a2af4af5dcca03d188402e18f7f6c0c7a7992910c6332be66e91a84c3e70a8e9ac6ece57ba126c6e0af5bf2fcdfce3a8b4d8b70c3c941a473c74ddf5fc080edcda0ebee33238bc762e9)


使用Nuget安装到项目中
--------------

各个模块的 Nuget 安装方式：《[使用 Nuget 将 SDK 安装到项目中](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e54efea5a9677d4e416e82d72631f761ad148d49dd9cbf0fe256852d0526a978baca2aaba9450cf7add9e1b7e48a02c58e8676847298bc977d7fb02c404736992d848fe0b29d1759a8308fbf35424e2385d1ca033a8a372a4a139dcaf8288533919369a10fbd6c4ebefb125766d762a15)》

如何开发小程序
--------------
小程序的后端架构和公众号保持了高度一致，
只需要使用Nuget安装[Senparc.Weixin.WxOpen](http://u.720life.cn/g/fc22af1986001aaffae545db699770d8e2199eb7088257368945b3ef3c935898ceaa717efaa66c7597f3b7221c7b05096489dd59fc63116429196437f531d8cb)库即可开始使用小程序。
Senparc.Weixin.WxOpen目前包含了所有小程序需要用到的消息处理、AccessToken管理、模板消息、二维码生成等全套功能。

如何部署
--------------
### 1) 部署到 Azure App Service

[App Service]( https://docs.microsoft.com/zh-cn/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview ) 是 Microsoft Azure 推出的 Web 服务，对 .NET 有很好的支持。部署步骤详见：[《将微信站点部署到 Azure 中》](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e54efea5a9677d4e416e82d72631f761a85ce7fd98b57cadfefac3ff44dd24fd2e015fadbac5ddd85fc2ddc2468cd63543decca64678acd5f1b3023b17e7edae4a1bed74d510073e957346eea180454cae17beb2a500050bdf9f458cf5bcfe3bbb22ae58a2d63876d4587e4454770139d)。

### 2) 部署到任意服务器的 FTP

在 Web 服务器上安装 FTP 服务（推荐 [FileZilla Server](http://u.720life.cn/g/ddf87ba1941172a8e00a29541a50b312976c9e914d2ac785342e0da57af33306c67ff1ce2bcd8d273e33b5019f223fc213781944fb89acb55c8436df1c797e3b)），直接使用 FTP 直接上传本地已经编译好的代码（本项项目 [Samples](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e230c727acd71aa454e6fe2e4ebdf6360c76d66b4b6022f3efa8aaf33f61e8ba8) 中对应的是 [Senparc.Weixin.MP.Sample](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e230c727acd71aa454e6fe2e4ebdf6360378232888df7f0e9f1c53d9084a792b06f65e4e5b707e0fc0738d8fb128ceebe2b1a14f8cb0981e46b9f064fef25ea417b755d81374f6a70f5beeee5854be700) 或 [Senparc.Weixin.MP.CoreSample](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e230c727acd71aa454e6fe2e4ebdf6360378232888df7f0e9f1c53d9084a792b06f65e4e5b707e0fc0738d8fb128ceebeec16fab5219fcb9af5bd5cd1df7a4f478d1ef67a8dc17ace1508d7b549751100b0375d583f7cd432945453fce6afc11c)，编译后即可直接使用，无需修改代码）。如果使用 Azure App Service 或其他云服务，通常 FTP 也都是开通的。


    - [x] 接收/发送消息（事件）
>   - [x] 自定义菜单 & 个性化菜单
>   - [x] 消息管理
>   - [x] OAuth授权
>   - [x] JSSDK
>   - [x] 微信支付
>   - [x] 用户管理
>   - [x] 素材管理
>   - [x] 账号管理
>       - [x] 带参数二维码
>       - [x] 长链接转短链接接口
>       - [x] 微信认证事件推送
>   - [x] 数据统计
>   - [x] 微信小店
>   - [x] 微信卡券
>       - [x] 卡券事件推送
>           - [ ] 买单事件推送
>           - [ ] 会员卡内容更新事件推送
>           - [ ] 库存报警事件推送
>           - [ ] 券点流水详情事件推送
>   - [x] 微信门店
>   - [x] 微信智能
>   - [x] 微信设备功能
>   - [x] 多客服功能
>   - [x] 微信摇一摇周边
>   - [x] 微信连WI-FI（未完整）
>   - [x] 微信扫一扫（商家）
>       - [ ] 扫一扫事件推送
>           - [ ] 打开商品主页事件推送
>           - [ ] 关注公众号事件推送
>           - [ ] 进入公众号事件推送
>           - [ ] 地理位置信息异步推送
>           - [ ] 商品审核结果推送

* 微信开放平台
>   - [x] 网站应用
>   - [x] 公众号第三方平台


* 微信企业号
>	- [x] 管理通讯录
>	- [x] 管理素材文件
>	- [x] 管理企业号应用
>	- [x] 接收消息与事件
>	- [x] 发送消息
>	- [x] 自定义菜单
>	- [x] 身份验证接口
>	- [x] JSSDK
>	- [x] 第三方应用授权
>	    - [x] 第三方回调协议
>	        - [ ] 授权成功推送auth_code事件
>	        - [ ] 通讯录变更通知
> 	- [x] 企业号授权登陆
>	- [x] 企业号微信支付
>	- [x] 企业回话服务
>	    - [ ] 企业会话回调
>	- [x] 企业摇一摇周边
>	- [ ] 企业卡券服务
>	    - [ ] 卡券事件推送
>	- [x] 企业客服服务
>	    - [ ] 客服回复消息回调
	    


* 缓存策略
>   - [x] 策略扩展接口
>   - [x] 本地缓存
>   - [x] Redis 扩展包
>   - [x] Memcached 扩展包

 欢迎开发者对未完成或需要补充的模块进行 Pull Request！
-->

各分支说明
--------------

|  分支      |     说明         
|-----------|---------------
| master    | 正式发布的主分支，通常这个分支比较稳定，可以用于生产环境。
| Developer | 1、开发分支，此分支通常为 Beta 版本，新版本都会先在此分支中进行开发，最后推送稳定版到 master 分支，如果想对新功能先睹为快，可以使用此分支。  2、此分支同时兼容 .NET 4.5 / .NET Core / .NET Core 2.0 版本，建议 Pull Request 的代码都到这个分支下，而不是 master
| BookVersion1 | 此分支为[《微信开发深度解析：微信公众号、小程序高效开发秘籍》](http://u.720life.cn/g/58c34c411e53b9427017785d88b345f54ad78da7bc38b910ccaf6e8324d1bda54e85282fb4996cfb5284bae005849b24277437bcfe7106a59cd2ad2e6323055c)图书出版时对应代码快照。
| DotNET-Core_MySQL | 此分支为 .NET Core 环境下的 [Pomelo.EntityFrameworkCore.MySql](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d87021eb1e7731a3f098bcc455f9a5c4bf7886987ddee9d153e965af09e4145fabd0b9cf561f826b0ffb001b09446a30411f96034355f8cf4203c70002910a78) 框架集成演示分支。
| NET4.0     | 仅支持 .NET 4.0 的分支，此分支已于2017年停止更新。.NET 4.0 最新代码随 master / Developer 分支同步更新
| NET3.5     | 仅支持 .NET 3.5 的分支，此分支已于2015年停止更新。.NET 3.5 最新代码随 master / Developer 分支同步更新
| Developer-Senparc.SDK | 此分支仅用于 Senparc 团队内部测试，可忽略。


感谢贡献者
--------------
感谢为此项目做出贡献的开发者，你们不光完善了这个项目，也为中国开源事业出了一份力，感谢你们！名单[点击这里](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469978141a6238329b8780e9712b831f0e465a0167c5ae33fa7b7499b0dec15b4dad7d3dae185778b6e5c0d6614ddc364e9fe6a6ac6894fbaedfa72fb4eb03ee69)查看。

捐助
--------------
如果这个项目对您有用，我们欢迎各方任何形式的捐助，也包括参与到项目代码更新或意见反馈中来。谢谢！

资金捐助：

[![donate](http://sdk.weixin.senparc.com/Images/T1nAXdXb0jXXXXXXXX_s.png)](http://sdk.weixin.senparc.com#donate)



License
--------------
Apache License Version 2.0

```
Copyright 2018 Jeffrey Su & Suzhou Senparc Network Technology Co.,Ltd.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file 
except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the 
License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, 
either express or implied. See the License for the specific language governing permissions 
and limitations under the License.
```
Detail: https://github.com/JeffreySu/WeiXinMPSDK/blob/master/license.md



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e49e7651efc446abaaa229266430f238378b36da7566560583bad79ce7d39426bef2bd0e0e3edabcbaedf01a8dcf6ffd3)