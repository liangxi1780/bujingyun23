 
   
     
   

   
     
   
 

# chao-cloud-im
spring-boot为基础，websocket+mybatis-plus+layui+layim+腾讯闲聊机器人+百度聊天机器人

## 集成

- [腾讯ai@申请](http://u.720life.cn/g/ca04da77debd996a922ac69632e8798f4d0b5f0c91c86746ecd01a0de8a7df42)
- [百度ai@申请](http://u.720life.cn/g/ce7a1b04eb5360d8685be43a24b62fc514757d8c4636fb43f97099887ae361da)

``` 
//1.导入sql
	resource
	  │
	  └─sql/mysql-im.sql
//2.修改 bootstrap.yaml 
		chao:
		  cloud:
		    im:
		      tai: #腾讯AI-机器人
		        app-id:  
		        app-key:  
		        session:  
		      bai: #百度Ai-机器人
		        app-id:  
		        api-key:  
		        secret-key:  
//3.引入layim.js
	resource
	  │
	  └─static   		 
	     └─layui 		
	   	  └─lay		
	 	     └─modules/layim.js
```

## 注意

- layim是收费UI，请大家自行前往官网授权
- 项目源代码中不包含layim.js包
- 拿去玩吧，禁止不授权使用，[贤心](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468a0479ad1dc55d7a6c2f68b68b6ceee1)会找你的
- [LAYIM@官网](http://u.720life.cn/g/2d38e9fd455c79aaf10c9a602a2ea1fcc9b4a0af45937a7e73078ee316f60770)

## 效果图展示

![Image text](screenshot/1.png)
![Image text](screenshot/2.png) 
![Image text](screenshot/3.png) 
![Image text](screenshot/4.png) 
![Image text](screenshot/5.png) 
![Image text](screenshot/6.png) 
![Image text](screenshot/7.png) 
![Image text](screenshot/8.png) 
![Image text](screenshot/9.png) 

## 版权

### Apache License Version 2.0  

- 如不特殊注明，所有模块都以此协议授权使用。
- 任何使用了chao-cloud-im的全部或部分功能的项目、产品或文章等形式的成果必须显式注明chao-cloud-im。

### NPL (The 996 Prohibited License)

- 不允许 996 工作制度企业使用该开源软件

### LAYIM

- LayIM 受国家计算机软件著作权保护（登记号：2018SR064263）
- 未经官网正规渠道授权擅自公开产品源文件、和直接对产品二次出售的，将追究法律责任

### 鸣谢
- [java-sdk@百度AI](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465ba5d0542ea777c13a8e36a46b7376078c73c8cfaf38bb5c6c88b262bfdd0f5c)  
- [xshuai@腾讯AI](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0322ad01f528fd8fbca9c89dd7834681)  
- [hutool-超级工具类](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046192789c630b5317627ad6852e6adac00)  
- [lombok](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304667e1b2f7ca2a7abf102cdf9e5fa5070a803dc1dd5f1c376fd8d7fb727fc2defd)  
- [layim-js](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e571de250c9dae82fb1fe954985549e2517fa1e201c5fedd379b34b7e1bde4c6e)  
- [mybatis-plus](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460e2dfceae48b05605c598cf2ee6246f3286c928f0d280aedceae7dfb4305194b)  
- [layui](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046bb20c8282dde15bbe4519b9ce18cefecb01eef0f62333198de4c1626175e8a27)  
- [......](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d45c0ae7090bb1b2bd83912ab32555db)  

感谢诸位用户的关注和使用，chao-cloud-im并不完善，未来还恳求各位开源爱好者多多关照，提出宝贵意见。

作者 [@chaojunzi 1521515935@qq.com]

2019年8月15日


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94fe4a657cf4184c580bef434084497bef8f5da496f58e573f570e3dea7d8b12be6c1d0b4d44711e8d6a543679da3067)