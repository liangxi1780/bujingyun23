  
   
    
    
    
 
**Pig Microservice Architecture**   
   
- 基于 Spring Cloud Finchley 、Spring Security OAuth2 的RBAC权限管理系统  
- 基于数据驱动视图的理念封装 Element-ui，即使没有 vue 的使用经验也能快速上手  
- 提供对常见容器化支持 Docker、Kubernetes、Rancher2 支持  
- 提供 lambda 、stream api 、webflux 的生产实践   


 部署文档  |   在线体验  |   前端解决方案  |   1.0  版本 
    
  

   
![](http://a.pigx.top/20190201162417.png?imageView2/2/w/650)   

#### 核心依赖 


依赖 | 版本
---|---
Spring Boot |  2.0.8.RELEASE  
Spring Cloud | Finchley.SR2   
Spring Security OAuth2 | 2.3.3
Mybatis Plus | 3.0.6
hutool | 4.3.3
Avue | 1.5.0
   


#### 模块说明
```lua
pig
├── pig-ui -- 前端工程[8080]
├── pig-auth -- 授权服务提供[3000]
└── pig-common -- 系统公共模块 
     ├── pig-common-core -- 公共工具类核心包
     ├── pig-common-log -- 日志服务
     └── pig-common-security -- 安全工具类
├── pig-config -- 配置中心[8888]
├── pig-eureka -- 服务注册与发现[8761]
├── pig-gateway -- Spring Cloud Gateway网关[9999]
└── pig-upms -- 通用用户权限管理模块
     └── pigx-upms-api -- 通用用户权限管理系统公共api模块
     └── pigx-upms-biz -- 通用用户权限管理系统业务处理模块[4000]
└── pigx-visual  -- 图形化模块 
     ├── pigx-monitor -- Spring Boot Admin监控 [5001]
     └── pigx-codegen -- 图形化代码生成[5003]
	 
```
#### 提交反馈

1. 欢迎提交 issue，请写清楚遇到问题的原因，开发环境，复显步骤。

2. 不接受`功能请求`的 issue，功能请求可能会被直接关闭。  

3.  wangiegie@gmail.com   
4.  交流群 23754102    

#### 开源协议
![](http://a.pigx.top/20190201155120.png)


#### 鸣谢 

avue [@smallwei](http://u.720life.cn/g/0ab41158b362205dfed5842565baddd4)    
mica-auto [@dreamlu](http://u.720life.cn/g/0579a7623867565b3998f3c13b48373150bf4093a3374ede8e537addbdc03add)   
bladex [@smallc](http://u.720life.cn/g/73cd24c26271e277d38587c0bbe3b8493c8c713f0af7571de31193dcfe85270c)  
mybatis-plus [@青苗](http://u.720life.cn/g/cc2472c166ad93a8385c9f9684a56a6b1b30f5c30efcf10ccb085b1efd525bb1)     
hutool [@路小磊](http://u.720life.cn/g/0579a7623867565b3998f3c13b48373150bf4093a3374ede8e537addbdc03add)   




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0407b93f06a8eaff1b1b36881552594ebf21ec2f8aa4d67ab5521ca4f4e190d6c425ccd6680b9c62991e291308240b48)