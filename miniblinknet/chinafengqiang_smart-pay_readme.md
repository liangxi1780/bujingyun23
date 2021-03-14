# smart-pay

#### 项目介绍
聚合支付,源自jmdhappy的xxpay项目。在其基础上精简了一些代码，保留了微信支付宝扫码支付，增加了条码支付和对账下载服务。原版用的mysql，这里数据库用jpa重写，原则上能支持各种主流数据库。

- 目前已经接入支付渠道：微信(条码支付、扫码支付)、支付宝(条码支付、扫码支付)；

#### 软件架构
spring cloud


### 版本更新
***

版本 |日期 |描述
------- | ------- | -------
V1.0.0 |2019-07-08 |支持微信支付宝条码支付和扫码支付
V1.0.0 |2019-10-12 |补充建表语句及测试工具
V1.0.0 |2019-12-05 |发布正式版本v1.0
V1.0.1 |2019-12-15 |注册中心计划增加nacos（待）

### 项目结构
***
```
smart-pay
├── smart-cloud-eureka -- 注册中心
├── smart-cloud-fiance -- 对账服务
├── smart-cloud-mgr -- 配置中心
├── smart-cloud-pay -- 支付服务
├── smart-cloud-web -- 对外接口
├── smart-core-bean -- 公共模块
```

项目启动顺序：
```
smart-cloud-eureka > smart-cloud-mgr > smart-cloud-pay > smart-cloud-web > smart-cloud-fiance
```

服务器配置为：

| CPU  | 内存 | 操作系统
|---|---|---
|2核 | 8 GB | Windows 2008 R2 64位

安装的各软件对应的版本为（仅供参考）：

| 软件  | 版本 | 说明
|---|---|---
|JDK | 1.8 | spring boot 2
|ActiveMQ|  5.11.1 | 高版本也可以，如：5.14.3
|MsSQL | 2008 R2 | 其他版本没测过

#### 运行截图

![商户信息](https://images.gitee.com/uploads/images/2019/1205/222015_602813fc_535810.png "11.png")

![支付渠道](https://images.gitee.com/uploads/images/2019/1205/222138_b0743d95_535810.png "22.png")

#### 参与贡献

1. Fork 本项目
2. 新建 Feat_xxx 分支
3. 提交代码
4. 新建 Pull Request


#### 码云特技

1. 使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2. 码云官方博客 [blog.gitee.com](http://u.720life.cn/g/4d9d51ba66eeb41dfb9759648c593bf554785fd0e6ab49d2f13e98afcb69bbc7)
3. 你可以 [https://gitee.com/explore](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed27d15edf43aa40a6d37a2a10b263e5a) 这个地址来了解码云上的优秀开源项目
4. [GVP](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb5ad9b84ebe402667383e4a11c785b2d) 全称是码云最有价值开源项目，是码云综合评定出的优秀开源项目
5. 码云官方提供的使用手册 [https://gitee.com/help](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ebbaab544314b1a4bd89bdd984a12bd00)
6. 码云封面人物是一档用来展示码云会员风采的栏目 [https://gitee.com/gitee-stars/](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e43c4696b881f436e3c9d0b3d64c264cb)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e544aa008e6e3ec181a38004a66bd4df0492ac87a988f6f069c0657ac92a76de182e89cddaff716decb624de11d7ffc62)