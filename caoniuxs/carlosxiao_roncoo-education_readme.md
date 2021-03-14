# 领课教育 - 领课网络在线教育系统

### 项目介绍（如果对你有用，请给个star！）
> 领课教育系统（roncoo-education）是基于领课网络多年的在线教育平台开发和运营经验打造出来的产品，致力于打造一个全行业都适用的分布式在线教育系统。基于MIT协议，无论是个人还是公司都可以利用该系统快速搭建一个属于自己的在线教育平台。系统前台采用前后端分离模式，vue.js为核心框架，后台采用Spring Cloud为核心框架，Eureka为注册中心，Config为配置中心，SBA为应用监控，Zipkin为链路监控。

### 前台功能介绍
* 页面展示，课程程的展示和购买功能、讲师招募等功能
* 个人中心，具有个人信息设置、密码修改、订单管理、学习记录等功能
* 讲师中心，讲师信息管理、课程管理（课程的添加、修改）、收益管理等功能

### 后台功能介绍
* 权限管理功能，多角色多用户自定义配置
* 系统配置功能，自定义进行站点配置及第三方参数配置
* 讲师管理功能，讲师申请入驻，后台具有审核功能
* 课程管理功能，讲师管理自有课程，后台具有审核功能
* 用户登录功能，同一时间只允许同一个账号在同一个地方登录，防止账号共享
* 广告管理功能，后台自定义广告设置，增加营销效果
* 支付功能模块，系统无缝集成了龙果支付

### 相关工程
##### 前端工程（roncoo-education-web）：[码云地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e41a652f917c164e70295da5a6f902e19724624dea27025957c12d3a115351a71) | [Github地址](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467bd4dd4cc03e6391d138519bf5f96755c670b2caa44e32124b18b1a483c11b74)
##### 配置工程（roncoo-education-config）：[码云地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e41a652f917c164e70295da5a6f902e1986213867a61e4489f65e794f4366672e0c8c487468fad44dc6d321a49b333dcf) | [Github地址](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467bd4dd4cc03e6391d138519bf5f96755b1e3af467e68a7b2e261f6059e024965f2a0eb27121d94d0f6cd54a8e7df7f55)

### 使用文档
##### [项目介绍](http://u.720life.cn/g/e9ebdf7a2da6cb735cbe7695cff80fc6f394601fe47d54fa59486d6698f30521874d48641f26501e6747c82076a9b95a1b0ffe0a841b23eee0667328adbb6494) | [部署文档](http://u.720life.cn/g/e9ebdf7a2da6cb735cbe7695cff80fc6f394601fe47d54fa59486d6698f30521902c4b5e74f8cfab903a6c93ac91b9518c4e05aeba9004ee562001f2ada6bc33) | [常见问题](http://u.720life.cn/g/e9ebdf7a2da6cb735cbe7695cff80fc6f394601fe47d54fa59486d6698f30521b66530d0c780d79f245cc9a4dc2336a5592747ec920a75e359d8a9b1bd6f7b3e)

### 演示地址
##### 前端演示地址：[领课教育](http://u.720life.cn/g/8c571719c33567a16cd84331785533d1fd5c539dc74a1a032cf74bbb60dda76a) | 后台演示地址：[管理后台](http://u.720life.cn/g/a710d429e037acae8ee051c30ea4b417fe58b5be9f6ea41dd044adefec70f5a2676d203176e6082104a12078be0441ef)

### 商业合作
* 如果想定制开发，我们提供有偿服务支持
* 如果想运营平台，我们云平台提供平台入驻
* 商业合作联系QQ：513781560 
* 官网地址：[http://www.roncoo.net](http://u.720life.cn/g/3c006c6033444dfeb0cd74fd94c28bf6282a349a8fba87cf9a93e825cd336aef)

### 升级说明：2.0.0 版本
* 集成了链路监控：roncoo-education-server-zipkin
* 新增站内信功能，推荐课程功能，发送验证码功能，密码修改功能
* 增加文件存储类型，修改bug若干
* 升级swagger-models版本， 更换Swagger的UI为swagger-bootstrap-ui

### TODO
* 动态更新配置(spring cloud bus + kafka + spring cloud config)
* 日志收集统计(kafka + Elasticsearch + Logstash + Kibana)

### 项目截图
![SBA](/doc/images/img_01.png)
![zipkin](/doc/images/img_02.png)

### 流程图说明
* 系统架构图
![系统架构图](/doc/images/01.jpg)

* 课程播放流程
![课程播放流程](/doc/images/course.png)

* 播放鉴权流程
![播放鉴权流程](/doc/images/course_callback.png)

* 课程下单流程
![课程下单流程](/doc/images/pay.png)

* 下单回调流程
![下单回调流程](/doc/images/pay_callback.png)

### 官方QQ群（加群免费获取sql脚本）
   826617734 

## 项目推荐
##### roncoo-recharge：[码云地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e41a652f917c164e70295da5a6f902e1964ecdce15eb2d9e2aedc7e7df23f3550) | [Github地址](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467bd4dd4cc03e6391d138519bf5f96755745e3fd4364258479d2e1f9fed8e9a69)
##### roncoo-jui-springboot：[码云地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e41a652f917c164e70295da5a6f902e1998ec28e6b60b40100732c159b6d3e8c1afeb209d72687ed9a33a23a802011240) | [Github地址](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467bd4dd4cc03e6391d138519bf5f96755ab321d626349a6320c3f7d65fef196a5)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecfaa097c03c322494bcf5f5896ba798bf52a47780a7ca4aa7036f4e675b5f24ac1e4f44046afe198f8f1018435fa5313f82e1ccb12fb2f33ae9c0df070f6d4da)