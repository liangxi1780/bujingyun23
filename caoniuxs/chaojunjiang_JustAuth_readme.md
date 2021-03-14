 
	   
 
 
	 Login, so easy. 
 
 
	 
		  
	 
	 
		  
	 
	 
		  
	 
 

 
     
         
                 
                 
                 
                 
                 
                 
                 
                 
                 
                 
                 
                 
                 
                 
                 
         
     
 

-------------------------------------------------------------------------------



JustAuth，如你所见，它仅仅是一个**第三方授权登录**的**工具类库**，它可以让我们脱离繁琐的第三方登录SDK，让登录变得**So easy!**

项目开源地址：[gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9894d7f9ce3e60d4881ec4b106227d88476) | [github](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046066dd74459bee98bfd188515b03f16770c296c2a74d25b559d1d9874813de6f8)

## 快速开始
- 引入依赖
```xml
 
     me.zhyd.oauth 
     JustAuth 
     1.2.0 
 
```
- 调用api
```java
// 创建授权request
AuthRequest authRequest = new AuthGiteeRequest(AuthConfig.builder()
        .clientId("clientId")
        .clientSecret("clientSecret")
        .redirectUri("redirectUri")
        .build());
// 生成授权页面
authRequest.authorize();
// 授权登录后会返回一个code，用这个code进行登录
authRequest.login("code");
```

**配套Demo**：[JustAuth-demo](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d98962baab8e3c248c30c9d34dcaa7c90d6a)

具体的例子可以参考：

- [实现Gitee授权登录](http://u.720life.cn/g/5d81a8ca0ea302f3ba1dc8d3b9aead0f8e6c7cc866eb89b5f0e55201f8c0f704)
- [实现Github授权登录](http://u.720life.cn/g/0da1eacdf39532cff4a861ca237e150c75f8555b84cea17342cdf7e96795b642)

#### API列表
|  :computer: 平台  |  :coffee: API类  |  :page_facing_up: SDK  |
|:------:|:-------:|:-------:|
|     |  [AuthGiteeRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f3128dae0ea4c36b11fcb1f1e3c8a74047cb4f203c0f6a67ed2c5982d823e4628)  |  参考文档  |
|     |  [AuthGithubRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f3128dae0ea4c36b11fcb1f1e3c8a74047cb4f203c0f6a67ed2c5982d823e4628)  |   参考文档  |
|     |  [AuthWeiboRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f3128dae0ea4c36b11fcb1f1e3c8a74047cb4f203c0f6a67ed2c5982d823e4628)  |   参考文档   |
|     |  [AuthDingTalkRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f2d12f60ea75700c025625584043b3a38a449e546136bd9efe4b83dce1a627ee5)  |   参考文档   |
|     |  [AuthBaiduRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f475a630befad01e9fa80e73fdd53cff1788817dd9f3c4ad9136c0d472c086ac0)  |   参考文档   |
|     |  [AuthCodingRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f3d58dbc6e4461a215c8d5b42d37a46e8a754c5f9752f273526f9e51596569dc6)  |   参考文档  |
|     |  [AuthTencentCloudRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670fd68c97c77feda923ba6d3352e24518060678dbe0a81f009ec38eda256b0048b3a70ac4315186f3c07d889025a72d1759)  |   参考文档  |
|     |  [AuthOschinaRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670fb3ed3e2599032fb18a5dfe1f8a33003a9d898503310a6a728d13844736a95844)  |   参考文档  |
|     |  [AuthAlipayRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670ffd9d76414bc3572a7a4c5c381fd3e37bc6585f2f4e658586c8193bf232c17a9f)  |   参考文档  |
|     |  [AuthQqRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f55527daab1e867bd87be3f40b647d1fde7e0b096911071082ec3f928e8b5714f)  |   参考文档   |
|     |  [AuthWeChatRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f8488741c91f92cef8b2c57cd2db87f221fb63db4ca2e9faa0973bfe807f63763)   |   参考文档   |
|     |  [AuthTaobaoRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670fce9f6c0a8ec4635c464c0f3c0200361e516a94adaac9f3b97fca9ca7510a631b)   |   参考文档   |
|     |  [AuthGoogleRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670fb9da3bf2d65cf8640a2f4d90737862c34a94e983b15f7ac571de5e3e727da351)   |   参考文档   |
|     |  [AuthFacebookRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670fd5775d0dc0cadd6f1b2ac44d6f1ae690cbfe14b2728aa3599ec9f123172e1927)   |   参考文档   |
|     |  [AuthCsdnRequest](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d9895bc80d6dabcc37cc4c7b319724e866a9233daa93b433be27917dd69b095cc11b85684adfa5580dddcd9e60f9218e670f67b3907488011ecabd2af8f503485e205accc9a3cd71fc0f1355ff8ca49b5015)  |  待续 |

## 后续开发计划

参考：[[开发计划] 待扩展的第三方平台](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e94d1794846e62207de06f8cd5ec9d98934e21571d60b4b0876bfc1219983457baf4935a05c4692e189ff9fa7b7f7f264)

另外，期待您和我一起完善这个项目！

## 贡献代码

1. fork本项目到自己的repo
2. 把fork过去的项目也就是你仓库中的项目clone到你的本地
3. 修改代码
4. commit后push到自己的库
5. 发起PR（pull request） 请求
6. 等待作者合并

## 致谢

在项目立项初期，也对当前开源圈的一些相同类型的项目作过调研，同时本项目也参考过这些项目，再次感谢开源圈内的朋友。

[YurunOAuthLogin](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e740458cdac3393b70d8851ad27141bff096038aaa6c173ef858f3044b79c9a0c): PHP 第三方登录授权 SDK


## 参考授权图例

#### 授权gitee

![Gitee授权登录](https://images.gitee.com/uploads/images/2019/0221/140015_4c09610e_784199.png "Gitee授权登录")

#### 授权github

![Github授权登录](https://images.gitee.com/uploads/images/2019/0221/140032_58f7dfb5_784199.png "Github授权登录")

#### 授权weibo

![微博授权登录](https://images.gitee.com/uploads/images/2019/0222/191210_67d5597c_784199.png "微博授权登录")

#### 授权钉钉

![钉钉授权登录](https://images.gitee.com/uploads/images/2019/0221/140540_8da8d959_784199.jpeg "钉钉授权登录")

#### 授权百度

![百度授权登录](https://images.gitee.com/uploads/images/2019/0221/140607_ebf1dcb6_784199.png "百度授权登录")

#### 授权coding

![Coding授权登录](https://images.gitee.com/uploads/images/2019/0224/192106_fd53b3d7_784199.png "Coding授权登录")

#### 授权腾讯云开发者平台

![腾讯云开发者平台授权登录](https://images.gitee.com/uploads/images/2019/0224/192128_db9e203b_784199.png "腾讯云开发者平台授权登录")

#### 授权oschina

![授权oschina登录](https://images.gitee.com/uploads/images/2019/0322/230652_05b4fd8a_784199.png "授权oschina")

#### 授权支付宝

![授权支付宝登录](https://images.gitee.com/uploads/images/2019/0327/183654_3d4b94eb_784199.png "授权支付宝登录")

#### 授权qq

待续

#### 授权csdn

待续

#### 授权微信

待续

#### 授权淘宝

![授权淘宝登录](https://images.gitee.com/uploads/images/2019/0518/154604_68b38305_784199.png "授权淘宝登录")


#### 授权Google

![授权google登录](https://images.gitee.com/uploads/images/2019/0521/190650_85c5f1c7_784199.png "授权google登录")

#### 授权Facebook

![授权facebook登录](https://images.gitee.com/uploads/images/2019/0521/233647_6a89fb45_784199.png "授权facebook登录")

## 关注&交流

|  公众号  |  微信(备注:加群)  |
| :------------: | :------------: |
|   |   |

 **QQ群** 
 
- JustAuth交流群 （230017570）：专业交流该项目

- 开源总群 （190886500）：各个开源项目的都有，也有博客建设等方面的朋友。（注意，该群需付费进入，防止发垃圾广告、垃圾推广等人士）


## 请喝咖啡

| 支付宝  | 微信  | 
| :------------: | :------------: | 
|   |   |




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e470836ff4cfad6957ef6d3e1ea5cfa46270ce1909ffd04d6f1bcb728157a07b3beabe52b7d8a7e447fcc316fa55c717d)