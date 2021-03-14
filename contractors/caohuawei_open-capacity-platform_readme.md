# open-capacity-platform 微服务能力开发平台 
 
简称ocp是基于layui+springcloud的企业级微服务框架(用户权限管理，配置中心管理，应用管理，....),其核心的设计目标是分离前后端，快速开发部署，学习简单，功能强大，提供快速接入核心接口能力，其目标是帮助企业搭建一套类似百度能力开放平台的框架；

 
##   技术介绍 
![](https://i.imgur.com/29QKUkG.png)  
##   框架设计
![](https://i.imgur.com/vn03vIX.jpg)

## 开发环境  
redis3.X  
jdk1.8  
MySQL Server 5.6  
maven3.3.9  
sts-3.8.0.RELEASE  

##  框架使用资料   
链接：https://pan.baidu.com/s/10Kae9_YotU5GnneaCk_p5Q 
密码：xqjb


##  项目地址
http://47.94.252.160:9999/index.html 用户名/密码：admin/admin

##  ocp项目演示
 
![](http://img1.ph.126.net/WAraEeweVw2SyTUSG1dT6Q==/3887169428474612491.gif) 


## 阿波罗配置中心演示  
![](http://img2.ph.126.net/-cKtj6Wia_q6YiZKV-IOsQ==/295548725646480248.gif)


## oauth认证方式    
![](https://i.imgur.com/MUCa4x6.gif)
## oauth单点登录   
![](https://i.imgur.com/PwcuvoC.gif)

## 项目组织结构分析 

![](https://i.imgur.com/aFptzQl.jpg)




## 一. open-capacity-platform能力开放平台管理    
   
01.用户登录
![](https://i.imgur.com/Wpo9STn.png)

02.用户管理

![](https://i.imgur.com/Ud65k7j.png)

03.角色管理

![](https://i.imgur.com/Vl4n8Wr.png)

04.菜单管理
![](https://i.imgur.com/DXFAsUy.png)



05.注册中心   
![](https://i.imgur.com/L1RMEoq.png)

 ![](https://i.imgur.com/IKHAQ1c.png)

06.配置中心   
![](https://i.imgur.com/PrHbd6P.png)
![](https://i.imgur.com/Zyy4XjQ.png)


07.应用管理  
![](https://i.imgur.com/ED2DSzi.png)


08.定时任务

![](https://i.imgur.com/boiJhNU.jpg)





## 部署 
1.cd /root/sop/eureka-server/bin/ &&  ./start.sh  启动注册中心服务   
2.cd /root/sop/config-center/configservice/bin/ &&  ./start.sh 启动配置中心configservice服务     
3.cd /root/sop/config-center/adminservice/bin/  &&  ./start.sh  启动配置中心adminservice 服务  
4.cd /root/sop/config-center/portalservice/bin/ &&  ./start.sh 启动配置中心portalservice服务   
5.cd /root/sop/apollo-zuul/bin/ &&  ./start.sh 启动演示apollo-zuul项目   


启动后效果预览   
![](https://i.imgur.com/H0CiqbD.jpg)


待续。。。。。。。。   


技术交流群:  
![](https://i.imgur.com/YowTMtG.jpg)

  


 


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e07467817a552e727242581e33b5626326babf7689f6fce6113c3590b75dd512817a0032b0e0bfaa34beed09e329e6fb38e0e54b1265aceadb19f6016de83db9a)