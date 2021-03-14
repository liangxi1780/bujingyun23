
![kisso图标](http://git.oschina.net/uploads/images/2015/1122/122054_3b6813fa_12260.png "爱心萝卜 kisso")

kisso  =  cookie sso 基于 Cookie 的 SSO 中间件，它是一把快速开发 java Web 登录系统（SSO）的瑞士军刀。


> 技术讨论 QQ 群 492238239 

http://baomidou.com/

http://www.oschina.net/p/kisso

[kisso 升级日志](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d626733fb1ef81dd3de8db53ee7f8d946a31198ff9f1a75ebe4908414586f0999c8c0f81a2cb19cd4b6f69b304d44c3cbbcf0585160165e0c9c3cc4a40b674eb353f4310ef1f5ee567203a393399c6aa4) 

[kisso捐赠记录,感谢你们的支持！](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d626733fb1ef81dd3de8db53ee7f8d946987a3e824d1a81180e085eb36d1f01e4bcd190be28bf8812334197fb39ce0ef25f6b38c12d2cd725524b2480faa4db01) 

ki﻿sso
===

kisso = java cookie sso framework


Maven 坐标
===
```
 
   com.baomidou 
   kisso 
   3.5.1 
 
```

Usage
===========
[kisso 依赖 jars](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d626733fb1ef81dd3de8db53ee7f8d946c6cb707275777c7114bade5d1fa8d727bef6fb85a41a2293b215cf7bae3400a9a70a48f37f9c62e231a37f980a80b45e) 

[kisso_Jfinal 演示 demo](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d626733fb1ef81dd3de8db53ee7f8d946560e622961fc9dfd70a15db73525b4cf) 

[kisso_SpringMvc 演示 demo](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d626733fb1ef81dd3de8db53ee7f8d9468864a06bc6489160f87c5f46ca33f568) 

[kisso_crossdomain 跨域演示 demo](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d626733fb1ef81dd3de8db53ee7f8d9464567cdf594eb0c999368ef17e93be7ea) 

捐赠 kisso
====================

![捐赠 kisso](http://git.oschina.net/uploads/images/2015/1222/211207_0acab44e_12260.png "支持一下kisso")


说明文档
===========
[sso.properties 配置说明](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d626733fb1ef81dd3de8db53ee7f8d946498ec7d6b66148d81582993009686f7eacee12523c260ba169719f81d528c281f2be3d42f99390719cd3eb9077a731c7db36fc0a634410d101db5019f4d3454a265ea6ef996088ccca3947e20e6cada792831e1b1f18cc00ffb9ff084224dd6c7c5de33b8180d106c5a95e7404900f1f83606798b73db6f808f7a0a7504e9761a895ddb93b5fe99b684cdf2819a0663bd0c66426a10a2f9de0a3f9d2a90810b3613305c4c5007c08534652b077fc494701caa84db161cc0e4ce98d577f478c70) 

[SSO 跨域登录实现方案](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d626733fb1ef81dd3de8db53ee7f8d946498ec7d6b66148d81582993009686f7eacee12523c260ba169719f81d528c2813cbf9cbdd7dc31f52ab19dcd6a2b2d1b9a6594007a964d76ddb41d3702955c78150d91d671850641b7a9f791b5e2e8f77a106bdd48338fe13e09c41a7209ea9b84de320da3640ba596e4c70b6f4ce8af9f641927bddf05a1d8163381ca2d3976eb1296f7a82a80536f1fec65c27015be0c99f18751d9c4c2e0348c7a593003b9cb8857ba8ac6e30433ede67522ed761322b86f74ab0ef39bdc746d129a45d3dd709f95ce74115cdadcd4138e99079feb) 


（1）sso 登录状态
--------------------------------------------

 #登录

 

 #登录成功

 



（2）跨域登录
--------------------------------------------

![crossdomain](http://git.oschina.net/uploads/images/2015/1208/101724_845ea916_12260.jpeg "Kisso,crossdomain login")

hosts:
--------------------------------------------
127.0.0.1 sso.test.com

127.0.0.1 my.web.com

--------------------------------------------

访问 my.web.com:8090/index.html  如果未登录会重定向至sso域登录页面

![kisso login](http://git.oschina.net/uploads/images/2015/1208/101635_99913d35_12260.jpeg "Kisso,crossdomain login")

登录成功 my.web.com 如图

![kisso login](http://git.oschina.net/uploads/images/2015/1208/101605_2037b254_12260.jpeg "Kisso,crossdomain login")


Supports
====================
1、支持单点登录

2、支持登录Cookie缓存

3、支持防止 XSS攻击, SQL注入，脚本注入

4、支持 Base64 / MD5 / AES / PBE / RSA 算法

5、支持浏览器客户端校验

6、支持Cookie参数配置及扩展

7、支持跨域登录，模拟登录

8、支持在线人数统计

9、支持生成动态图片验证码

Futures
====================
1、欢迎提出更好的意见，帮助完善 KISSO 

copyright
====================
Apache License, Version 2.0


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)