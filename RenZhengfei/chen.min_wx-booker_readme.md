## wx-booker
微信小程序-图书共享预定  

# 体验效果
**在微信中搜索小程序【建始同城共享书】或扫码体验**  
![viewimg/01.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/01.jpg)

![viewimg/02.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/02.jpg)  

![viewimg/02.gif](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/02.gif) 


# 初衷
通过微信小程序向当地爱书者提供一个图书共享预定平台，前期期望投入费用越少越好。同时还要有一定的变现能力，例如图书借阅费、本地商家广告投放。

# 功能分解
1. 图书分类管理
2. 图书信息管理，包括介绍和图书相关ISBN、关联分类等
3. 预借功能与费用管理
4. 图书在馆状态
5. 全局搜索图书
6. 图书条形码扫码查询
7. 用户管理与用户等级
8. 广告管理
9. 本地商家服务投放
10. 图书订阅帮助信息
11. 用户浏览与喜欢统计
12. UI交互清爽简单

# 程序选型
- **域名：阿里云购买**  
制作小程序域名还是必须的，这个去阿里云买一个.com域名就好。年费50元+。
- **服务器：阿里云ECS**  
这个是做互联网没办法少的，选用ECS主要因为我服务器有其他建站需求，建立多个网站使用。年费：500元+。
- **后台：Wordpress**  
强大而免费，通过插件的使用可以打造出功能完善的CMS/商城系统。年费：0元。
- **RESTAPI:微慕小程序插件**  
这个是用于将wordpress和小程序通信的插件程序，我是用的是微慕小程序插件1.6.0。年费：0元。
- **小程序：微信小程序个人版**  
前期因为无法预测变现能力，所以考虑成本，我输出的是个人版小程序。未来有更多本地商业服务的时候，移植到企业版。年费：0元。
- **前端：微慕开源版+自己摸索完成**  
小程序的前端是我通过微慕开源版3.6的代码二次开发完成，我现在Github已开源，有需要的朋友可以Clone。费用：0元。

# 使用
- **环境准备** [服务器选型](http://u.720life.cn/g/cc176fdce68265104b8a4a80987ffe391b38d10272d6f7e6bbea5e66f680df668c0ac7807e4ac9887212ef722fef59fd87b89f990a95e53a49e616f49986001b)购买、[域名购买]https://wanwang.aliyun.com/  

- **程序安装**
 1. *Wordpress安装*  
 前往[官方下载](http://u.720life.cn/g/dcd7b76a8d6b9c5a21d51e955ea7019529f5dc02095c86db5a202fb781922b4d)或者[https://github.com/WordPress/WordPress]https://github.com/WordPress/WordPress
 2. *Wordpress主题安装*  
 我使用[raz主题](http://u.720life.cn/g/140b6851a48bee45977417ce305d514764240a89f6f8a5f38258049224b28aceee6a26e2e06fb3aeed58229956d6ec9d)，主要是我比较懒，这个主题不光是因为我网站商城需要简洁的效果，自带的文章自定义字段也方便我定义。
 ![viewimg/03.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/03.jpg)  
 3. *Wordpress插件安装*  
 这里用到两个插件：微慕的小程序插件[https://github.com/iamxjb/rest-api-to-miniprogram](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e3b2986d36ebcf786ce6498cd20dc61a64a6dc5309874278d4a317e1fcb57e7c63540c40084df0ece067e1b3ad80d43d)+全局搜索插件Search Everything，在wordpress后台安装新插件搜索进行安装。前者的RestAPI用于与微信小程序通信，后者用于小程序支持字段搜索。
 ![viewimg/04.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/04.jpg)   
 ![viewimg/05.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/05.jpg)   
 ![viewimg/06.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/06.jpg)   
 4. *微慕开源版下载*  
 微慕算很良心的小程序开源商，功能多，文档详细，社区活跃，值得使用。需要高级功能的可以去[微慕商城](http://u.720life.cn/g/9bf7b12c42ab322ad2fb5aca0c80fca43d7cb8704a5b2bdfeb2439c2eca9c174)购买专业版，提供在线技术支持。微慕开源版本在Github的传送门：[https://github.com/iamxjb/winxin-app-watch-life.net]https://github.com/iamxjb/winxin-app-watch-life.net
 5. *微信小程序账号申请*  
 前往[微信官方](http://u.720life.cn/g/408fb60b53d11d245635ad5e8e8cd69793d6149b863acfe48bae0405393bdbc1)注册小程序账号，后台获取你的appid和秘匙，填写相应的小程序信息。选择服务类型时要注意，个人类型的小程序在服务类型选择上要慎重，看[官方文档]https://developers.weixin.qq.com/miniprogram/product/material/
 6. *微信小程序开发环境安装*  
 前往[微信官方下载](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484c20708e11463bd684459f5de41dafa7d0c3e1211843e1cdbef7a640a8fe47dc75e47294b5e75d000ca479e5d58269765021b8fbabad90318955d5cae729789a9)最新版本的微信开发者工具，安装后启用微慕开源版的代码，按[微慕官方的帮助文档]https://www.minapper.com/doc/web/#/3?page_id=54
 ![viewimg/07.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/07.jpg) 

至此，程序安装完成，这一步预览小程序的效果是微慕小程序的模板。

- **微信小程序-图书共享预定模板安装调试**  
 1. *Wordpress插件替换*  
 Clone [微信小程序-图书共享预定](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463e8e24dd0b84f9a9aec2a6a1108918f94b2d773dcaad9e7e17592dd77caa0ffe)到本地，其中code是小程序前端代码。plug是微慕的小程序插件的修改版，该插件务必配合使用[raz主题]http://appbeebee.com/product/raz/  
 ![viewimg/08.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/08.jpg) 
 2. *小程序前端代码替换*  
 将code里的代码复制替换微慕的前端代码即可。  
 ![viewimg/09.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/09.jpg) 
 3. *建立分类*  
 代码中的书籍、帮助FAQ、本地活动调用的是Wordpress的三个父级目录。在Wordpress的文章分类中首先创建三个父级目录，将目录ID分别替换代码的中cateparentID/categories。三个id分别在page/index/index.js,page/faq/faq.js,page/act/act.js  
 ![viewimg/10.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/10.jpg)   
 ![viewimg/11.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/11.jpg)  
 4. *写文章*  
 自定义字段和分类记得填写和选择。注意书目、本地活动对应的字段对应不同的用途。  
 ![viewimg/12.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/12.jpg) 
 ![viewimg/13.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/13.jpg)    
 5. *配置本地活动轮播*  
 进入wordpress后台微慕的小程序插件，输入要在小程序中轮播显示的本地活动文章ID。用于轮播显示在详情页底部和我的信息页入口。  
 ![viewimg/14.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/14.jpg) 
 6. *天气和地址配置*  
 使用[高德SDK](http://u.720life.cn/g/4f6da1cb7df68c5e971e5bc2f806831c4d7f029fa106cdc38ed2b944565badde60186e62b1ecb298d12ac7b30fe7af83)，前往并注册账号获取key，key和city需要配置成你的信息。需要配置的文件pages/mine/mine.js,pages/amap/amap.js。SDK在Github的传送门：[https://github.com/amap-demo/wx-regeo-poiaround-weather]https://github.com/amap-demo/wx-regeo-poiaround-weather  
 ![viewimg/15.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/15.jpg)

# 感谢
- 感谢[https://hellobeebee.com/](http://u.720life.cn/g/2f927350a697e1679e844852ebfb8a458d6be4de8e6b962c444052ea9e581243) 提供空间  
- 感谢[https://appbeebee.com/](http://u.720life.cn/g/5522e96a418dc0d71630e37ad9196fb50426ce82a436e0534e84430d2d94d431) 提供主题  
- 感谢[https://shops.minapper.com/](http://u.720life.cn/g/9bf7b12c42ab322ad2fb5aca0c80fca43d7cb8704a5b2bdfeb2439c2eca9c174) 提供小程序代码  
- 如果你觉得这个模板不错，请打赏馆长。  
![viewimg/16.jpg](https://raw.githubusercontent.com/shiheme/wx-booker/master/viewimg/16.jpg) 

# 相关资源  
- *github*  
[https://github.com/shiheme/wx-booker](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463e8e24dd0b84f9a9aec2a6a1108918f94b2d773dcaad9e7e17592dd77caa0ffe)
- *gitee镜像*  
[https://gitee.com/week7day/wx-booker](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec15f822070f42a9f7b45c67b682cce4c6f3a0ea03f4a638f1c87cca0a59c55f8)




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8d712d675316aaa0fcccdeaadb04387cd43b1734df6516b5b59e86393e9812706de256169a415820d5cc122caeea550)