# Magicodes.Admin

 
## 说明

Magicodes.Admin，是心莱科技团队打造的一套高效率、易扩展、基础设施强大、代码生成完备、理念和技术先进的敏捷开发框架，同时也是一套分布式、跨平台（**linux、Docker容器支持，已提供Docker教程、腾讯云容器托管教程、Azure DevOps教程**）、多终端（包括**Android、IOS、H5、小程序、微信公众号**）、前后端分离、持续集成（CI）、自动部署、监控支持的统一开发框架和开发解决方案。框架基于.NET Core 2.2、Angular、Ionic、EF Core、ABP和ASP.NET Zero，并在其基础上进行了封装和完善，并且编写了相关的工具（代码生成）、组件（云存储、支付、微信等等）、生成服务。

**注意：代码均开源免费，我方不收取任何授权费用。**


## 官方订阅号

关注“麦扣聊技术”订阅号获取：

* 最新文章、教程、文档
* 视频教程
* 解决方案
* 编程心得和理念

## 官方文档

* 地址： 
* 总体说明： 

## 免费的代码生成服务

* 在线免费生成服务地址（基本无限制，注册即可免费使用）： 
  * 使用指南： 
  * 支持后台服务生成
  * 支持语言字典翻译和生成
  * 支持后台UI生成
  * 支持自动合并（需下载客户端合并工具）

## 后台UI库

* Angular版本UI库地址： 
* Vue版本UI库地址（预计9月发布）： 

## VNext

* 新版UI+Demo
* 后台Vue版本UI
* 具体见： 

## 相关Nuget包

| 名称     |      Nuget      |
|----------|:-------------:|
| Magicodes.Alipay  |  [![NuGet](https://buildstats.info/nuget/Magicodes.Alipay)](https://www.nuget.org/packages/Magicodes.Alipay) |
| Magicodes.Alipay.Global |    [![NuGet](https://buildstats.info/nuget/Magicodes.Alipay.Global)](https://www.nuget.org/packages/Magicodes.Alipay.Global)   |
| Magicodes.Pay.WeChat | [![NuGet](https://buildstats.info/nuget/Magicodes.Pay.WeChat)](https://www.nuget.org/packages/Magicodes.Pay.WeChat) |
| Magicodes.PayNotify | [![NuGet](https://buildstats.info/nuget/Magicodes.PayNotify)](https://www.nuget.org/packages/Magicodes.PayNotify) |
| Magicodes.WeChat.MiniProgram | [![NuGet](https://buildstats.info/nuget/Magicodes.WeChat.MiniProgram)](https://www.nuget.org/packages/Magicodes.WeChat.MiniProgram) |
| Magicodes.Sms.Aliyun | [![NuGet](https://buildstats.info/nuget/Magicodes.Sms.Aliyun)](https://www.nuget.org/packages/Magicodes.Sms.Aliyun) |
| Magicodes.Storage.Core | [![NuGet](https://buildstats.info/nuget/Magicodes.Storage.Core)](https://www.nuget.org/packages/Magicodes.Storage.Core) |
| Magicodes.Storage.AliyunOss.Core | [![NuGet](https://buildstats.info/nuget/Magicodes.Storage.AliyunOss.Core)](https://www.nuget.org/packages/Magicodes.Storage.AliyunOss.Core) |
| Magicodes.Storage.Local.Core | [![NuGet](https://buildstats.info/nuget/Magicodes.Storage.Local.Core)](https://www.nuget.org/packages/Magicodes.Storage.Local.Core) |
| Magicodes.Storage.Tencent.Core | [![NuGet](https://buildstats.info/nuget/Magicodes.Storage.Tencent.Core)](https://www.nuget.org/packages/Magicodes.Storage.Tencent.Core) |
| Magicodes.WeChat.SDK.Core | [![NuGet](https://buildstats.info/nuget/Magicodes.WeChat.SDK.Core)](https://www.nuget.org/packages/Magicodes.WeChat.SDK.Core) |
| Magicodes.SwaggerUI | [![NuGet](https://buildstats.info/nuget/Magicodes.SwaggerUI)](https://www.nuget.org/packages/Magicodes.SwaggerUI) |
| Magicodes.IE.Excel | [![NuGet](https://buildstats.info/nuget/Magicodes.IE.Excel)](https://www.nuget.org/packages/Magicodes.IE.Excel) |
| Magicodes.IE.Core | [![NuGet](https://buildstats.info/nuget/Magicodes.IE.Core)](https://www.nuget.org/packages/Magicodes.IE.Core) |

相关源代码地址：
 

## Demo

敬请期待新版UI。

## 开发组件、套件、解决方案、理念

目前框架中包含以下开发组件、套件、解决方案、理念：

* 通用功能权限
* 数据权限（框架中尚未提供Demo）
* 多租户
* 版本
* 组织机构
* 多语言
* 审计日志（操作审计和数据审计）
* 缓存管理（支持内存和Redis）
* 日志（Log4net、**NLog**、**阿里云日志**）
* 设置管理器
* **短信服务（Magicodes.Sms【https://github.com/xin-lai/Magicodes.Sms】）**
* **支付、统一支付回调（使用Magicodes.Pay【https://github.com/xin-lai/Magicodes.Pay】，支持微信、支付宝、国际支付宝支付和分账）**
* **微信SDK（Magicodes.WeChat.SDK【https://github.com/xin-lai/Magicodes.WeChat.SDK】）**
* **微信模块，已完成公众号的配置，并且提供了公众号API Token获取和更新机制的封装，支持分布式架构**
* **小程序SDK（Magicodes.WeChat.SDK【https://github.com/xin-lai/Magicodes.WeChat.SDK】）**
* **微信扫码登录（Magicodes.WeChat.SDK【https://github.com/xin-lai/Magicodes.WeChat.SDK】）**
* 通用异常处理
* **领域驱动**
* **依赖注入**
* **接口权限以及授权**
* **在线接口文档（Magicodes.SwaggerUI+Swagger UI【https://github.com/xin-lai/Magicodes.SwaggerUI】）**
* 数据验证
* 调度任务（Quartz）
* 后台任务（Hangfire）
* 数据筛选器（租户筛选器、软删除、是否激活）
* **跨平台以及Docker支持（目前基于.NET Core 2.2），支持Visual Studio Tools for Docker**
* 通知系统
* **支持通过配置文件配置Kestrel服务器（比如启用HTTPS，以便更好地支持Docker）**
* **支持HTTPS重定向**
* **支持HTTP严格传输安全协议(HSTS)**
  * 在浏览器将会阻止通过 HTTP 发送的任何通信的域的配置存储。 在浏览器强制通过 HTTPS 进行的所有通信。
  * 在浏览器可防止用户使用不受信任或无效的证书。 在浏览器禁用允许用户暂时信任此证书的提示。
* **即时消息（SignalR）支持，并且支持Redis集群**
* ORM和数据迁移(Entity Framework Core)
* **通用导入导出（Magicodes.ExporterAndImporter【https://github.com/xin-lai/Magicodes.ExporterAndImporter】）**
* **通用存储（Magicodes.Storage，支持本地存储,阿里云存储,腾讯云存储【https://github.com/xin-lai/Magicodes.Storage】）**
* 全国行政区域抓取和初始化（Magicodes.Districts【https://github.com/xin-lai/Magicodes.Districts】）
* **移动端统一开发解决方案和模板（Angular+Ionic）**
* 前后端分离
* **后台前端解决方案和UI（Angular、primeng、bootstrap）**
* **简单CMS**
* **移动端通用接口（登陆注册找回密码等）**
* 邮件服务
* **移动端多语言支持**
* **交易流水以及多国货币支持**
* **大量后台UI组件（除了常用组件，还支持Tree Table、图片展示、文件批量上传、枚举下拉、关联项下拉、审计）**
* 单元测试（后台服务、移动端服务）
* **代码生成（后台服务、后台UI功能、多语言定义、权限定义、移动端服务）**
* **一键部署（后台服务、前台服务、后台前端）**
* **接口调用代码生成（nswag，后台前端和移动端前端）**
* **支持Dapper，作为ORM辅助库**

加QQ群 **85318032** 获取最新动态和文档。

## 推荐开发环境

![推荐开发环境](./documents/Magicodes.Admin推荐开发环境.png)

已升级到到.NET Core 2.2，请先下载SDK： 

## 官方博客

 

## 相关QQ群

编程交流群 

产品交流群 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e915ac19bb0f1c48f661c28a694b1a9e02ba3986b97cf4a355890c73fa4cbbf59ebba1b475976c5469b06ac9e2ee34fe31f8a528a39fb60024882b06c7165559a)