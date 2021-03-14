# AnjukeSpider
### 简介
爬去安居客房源，筛选房源，微信提醒

### 环境搭建

1. 安装**python2.7**、**pip**、**setuptools**    
2. 安装requests   
```shell
pip2.7 install request
```

### 使用

#### 安居客相关
1. 访问安居客网站，选择城市和小区后，复制当前网址，替换**AnjukeUrl**后面的网址   
2. **SizeRange**为面积区间，既筛选**面积<SizeRange**的房源   
3. **PriceRange**为总价区间，既筛选**总价<=PriceRange**的房源     
4. **UnitPriceRange**为单间区间，既筛选**单价<=UnitPriceRange**的房源    
5. **NumEnd**为页码区间**1-NumEnd**   
6. **SizeRange**、**PriceRange**、**UnitPriceRange**、**NumEnd**值必须为**数字**     
   
#### 微信企业号相关   
1. [点击创建微信企业号](http://u.720life.cn/g/0782a1a2d2d0fe6b898571c90469e31dcf3697d0a756f67420c80fd69fdc4aa9),并获取**CorpID**与**Secret**   
2. 在通讯录中创建**标签**，并记录标签ID，添加到**Totag**     
3. 创建**app**，并记录应用ID，添加到**AgentID**    
    
### 未完善  
1. 未对接redis，因此循环执行脚本时，房源会重复提醒  
2. 未使用代理模式，因此ip存在被封的可能，因此每次获取房源后会sleep 3秒  



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e03f76159ff31a4c0deb18851221a13ec3e43d771fbac2f56559a90798d15e896e08a4595ca3656f1a19c647f43331cd2)