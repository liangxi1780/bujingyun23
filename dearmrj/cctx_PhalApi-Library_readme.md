## PhalApi框架扩展类库，欢迎大家一起来参与维护！
### -- 致力于与开源项目一起提供企业级的解决方案！
此部分类库为 [PhalAPi框架](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fe997c1a207321cbf4c7afe91f723bebfe) 下的扩展类库包，各个扩展包各自独立，可以根据需要自动下载安装。
  
虽然此部分的扩展很多都是基于已有的第三方开源实现，或者开发同学自己实现分享的，但我们所做的不只是代码的搬运工，更多的是在系统架构上的组件库重用，以及在此引入 **防腐层** ，避免进入 **供应商锁定（Vendor Lock-In）** 。  
  
除此之外，可以在PhalApi框架的基础上，快速引入符合我们国内实际项目开发需要的各种扩展。如时，您会发现，原来编程本来就是一件如此简单的事情，就像搭积木一样。  

  
正如我们一直推荐的：
```
接口，从简单开始！
```
  
## 目前已提供的扩展类库 - 针对使用者
### 1、微信开发
此扩展可用于微信的服务号、订阅号、设备号等功能开发，则PhalApi框架下简单配置即可开发使用。  

 [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116da40b4e6c77d8e47af60f64da23779941a1a5379afb22d76c4fca144c4b7302e1b73fc667c1a8d0d01aeff826e234e2a2782accf575884b66ad0ec7deabfb567c8596746e6a0ae2b8d28e50dc633c29941ee9ce6bc7925160d031c913d3f63a79a)
 
### 2、代理模式下phprpc协议的轻松支持
此扩展可用于phprpc协议的调用，服务端只需要简单添加入口即可完美切换。  
  
 [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116dacf11332bda8901eaf46f424068f4fcd547e58109c4a9bc4d74cba8f6ad5cc6d4366ce3cb3b6d3678cbac3d35e0a8dcf554e18ddac3521c204e4ba30e58c20fe750f05e6667d631732dd74da592a20ad59775f103a6658523cf11a58d39021d4fc43be24f2b4ed7584c105d9d764b86a2058ed2bbddf71d771a9b23c4ed0f9e82f53ecf68d2b83fbdf7c4f6f64992b32f05fd42f457f7d7e1d687cb126bf215948b9afda72d667a99a7da9c30c8c18c1f)
   
### 3、基于PHPMailer的邮件发送
 此扩展可用于发送邮件。  
 
  [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116da50a823cd4f15ccc02f5b1fcac71780e8d90b0260c61ca51922a4c26d2ef7ece260f982d902a9d4a5ce43d510a11b01a0c8a43ca3a1c1c43272ca1354b987281f6f40ba749eaea820f97a17a9b9834da0e71ee20d07918d7202dfea8fe323c9b5e151d4fedf3cf3311d7ab5e73df828c1bd0495433dfa1f4eb73dcd3796f97784)  
  
    
### 4、优酷开放平台接口调用
此扩展可用于调用优酷开放平台的接口。
  
  [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116da8be4971d563f9209629312d4ee872673c53688ce361236be1b6c03a7c933d0ecd621ed1d65816c3f3aa26c897927e387ee87265474aca6e162a3c5e3998e3197f733a11eb39d8c356e0ad46fdd0be34f98b7f571806e51e1d98c4e890b4a74b891d578a7bb972da3ad5bc61c776f579b0a2dc35b7720a7cf40e8207e189c1711d6506b8ba8b1a58110f03ea52def19f2)  
  
    
### 5、七牛云存储接口调用
此扩展可以用于将图片上传到七牛CDN，或者其他七牛接口的调用。  
  
  [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116da40ad80370cdd284ab6c79b352ea671a88d888bf51cdfd7053244a587fae85ba3c9266e4cf78ed571aa5ad798f216de95187c065b214853c517bcc2ee7e2eaa7260fd53ab3b762ee1f6be8a491c970de0a6f321cd07ab5682efc0c0d9ea82888c50418433b23c58c559d2436a77ce128148fba3d470ee24e053aef179c128d8c4e4ff4ae312998c6e895396c556c72d31)

### 6、用户、会话和第三方登录集成
此类库主要特点有：
 + 1、可以和第三方登录集成，包括：微信登录、新浪登录、QQ登录
 + 2、为客户端提供了直接可以调用的登录接口
 + 3、为服务端提供了直接可以检测用户登录态的操作
 + 4、支持token落地、高效缓存和分布式的数据库存储  
 + 5、展示了如何开发一个项目级的类库、包括数据库配置、翻译等
  
 [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116da0742db692594a537a24fee185d7e7a166b64ee928d87d1b430f094efb4fdb06ae3e91d31edfef52fb684d7fbac2eadf8e98ac39f3c04b91608b514758a1e079e98cdec1fb399de9e7ee7f9774a4efaed2cb72a3a9b0e160f86dbb23b25d0d8dc6c882da5800b2f17c7b92eea3eaaa8c8386c0060cf01a7222075b09ee4043817d6ef7bcc8238b4820057761cfd7b95e05fadb41cb0f9a2c73906076ace6bf553278662af4d4edf8fbc4c663b3c3043d8)
  
### 7、swoole支持下的长链接和异步任务实现
目前，此扩展类库提供了：
 + 长链接的接口调用
 + 异步计划任务的调用
  
 [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116da00c498750a875254cb9468193960975f90b477bcf766f60a5d0a485d4a5b4d159f8f55d5b67bdfdf3cc4d83c6d4c3c3059ee180c722bd2874e33a4def6a4599bbbb5a343ea4c3002b85e20e9046e85be3773d570a99924ff346994b0ce59a53ba67ce3c3bbb5d2a5e6d59f6d63c2988aaa36a6e0e526dfbb936e7ac0309d68a469d33dbd60a69a8efde5a8ddeaa3c9d11fe3860ec9e2f696a72f2c76fd1afff49697b2af5c09c679f1f0bd5ed6e9db46a8bca727040e9145d85506471a4ba5b7)

### 8、新型计划任务
此扩展类型用于后台计划任务的调度，主要功能点有：
 + 1、提供了Redis/文件/数据库三种MQ队列
 + 2、提供了本地和远程两种调度方式
 + 3、以接口的形式实现计划任务
  
[更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116daf4ab5384268d07ff51f546fd4f61916054648e3893a79953f170ac71b2d552346771c1da2e56cdf6d39ef172a9cfab721d172844d1e2c3e7b176d10248a0a9a6080175b11a8fe6232e96ea792dfd2cf95dcfab63a707596a65fa898beb10208cfe664879f07ed656e00dda4cbea25db5)

  
### 9、Auth 权限扩展 (由@黄苗笋提供)
实现了基于用户与组的权限认证功能，与RBAC权限认证类似，主要用于对服务级别的功能进行权限控制，主要功能点有：
 + 1、提供了接口服务维度的权限验证
 + 2、提供了可配置的组与规则
 + 3、支持免检用户
 
[更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fefe2497f079bbcedd9d157f612e0a782ab3784526a70d9ee140775657ef15bd4acc7d27e996ffafb730c00a1d958e9cb35a6c55121b8d722de05accb263453df9d6827a4d4400b5c9740197eb6d4171c45b83356fc5e22f0cfc8e5cd58bacbc823db85be03020a0e926b8808d99b490c7)

### 11、FastRoute快速路由
此扩展基于 ![FastRoute](https://github.com/nikic/FastRoute) 实现，需要 **PHP 5.4.0** 及以上版本，可以通过配置实现自定义路由配置，从而轻松映射到PhalApi中的service接口服务。，主要有：

 + 1、基于FastRoute实现
 + 2、需要PHP 5.4.0 及以上版本  
 + 3、通过配置文件来实现自定义路由，并映射到service
 + 4、可兼容无路由的历史URI

 [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1feea427bd8bd9527b8ec26805d33c116daa98c03de67afe5d68c9c96780b9ed59b1c0c2845e4d71c45e9ff8fe20ca78ce3153bb83ba7f60637013de625328747911df83b8092f00e0d2be888bc465228ec2514b633e7329000ffa619c6ef77ee8732b4fad674c805e10f1bd1f4858ccd80b2603b1f7a4fe90c552f357444ebc9ffeced5b8bfce34ce2411f1314c0e5ecdc)
 
### 12、基于PhalApi的DB集群拓展DB_Cluster (由@喵了个咪提供)
为应对海量数据分析与统计，提供针对分表分库统一封装的数据库操作接口，主要用于解决大量数据写入分析的问题。请注意：V0.1bate版本,很多功能尚不完善,只提供技术交流使用,请不要用户生产环境。主要特点有：
 + 1、适用于大量select和大量的insert的业务场景
 + 2、基于架构思维的实现
 + 3、分表分库算法介绍
 + 4、基准测试对比
  

 [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fea988caaca725341dc69ae266ab79dd9a977323837822ae2b528d9738e53dc765b159a39e0689e456edb916d31f47dd374d9f944bc2b17edda27ace505c26e9544255b2cf33224749b94ec1bdfc494790f39d48e41625d22998f016396e6434d8bda4ed57b9c1605626d8bb3ec5ec17ed34e267bce4c07ee9165566ace9413fc378f134822bb5efad22eb51454db1b963852f228b93c4a978e894b1d78f57fced)

### 13、基于PhalApi的Redis_Base拓展 (由@喵了个咪提供)
主要提供更丰富的Redis操作,并且进行了分库处理可以自由搭配
 + 1、适用于对Redis需要其他数据类型操作的业务
 + 2、可以用于队列脚本,封装了队列处理


 [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fefe2497f079bbcedd9d157f612e0a782a6274649a6d663d088b6645a5d8ddc25ec7a983d1567b82e25f4247f19d48c7858154172515c18b987a9caef779459a951fa55e9c57fef90b019e67eee8eb5a56620b56e26999b2a28d51bc6e72198438dafcedf0acb1e4ee83965e311e0d0c46)

### 14、基于PhalApi的图片上传拓展 (由@SteveAK提供)
此扩展可用于图片等文件的上传，使用云上传引擎,并支持local,oss,upyun。

 [更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fea988caaca725341dc69ae266ab79dd9a946eb8c52c2ea6b96c0ff554414ee5af1a7a2b8357aaf25155ea5c9fdb2ab82b74b64b18064f6b5d44d8fde16e1c78fbe844802d9d4686839e6e5bf41c85ab31cf0e69fd36f6e28a196b3dde4fdbfae703c829e8d75e51b14fe06ce94b1f8cb9f6b27c94dc96a29e53353354c57c25e2945e3d5d0ee90aaa586d50bfd1eb9d7728895480af7b4eb2d57e24dafb31c7f1)


### 15、基于PhalApi的第三方支付拓展 (由@SteveAK提供)
目前此扩展支持：
 + 1、支付宝支付
 + 2、微信支持
 + 3、支持第三方支付添加


[更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fea988caaca725341dc69ae266ab79dd9a85df22285e27b77db3ae1ac7aa33564ca24db367e253a01bd61b602dfe6adb92374818df4b00cb9c833575a11963a55053f7bae35ad6b08b2f789bcd271a1fa18c2c27b7b1509d7b65c648c2260e0a4401de8ec8ccbebc742d1b24be2f5052831f6d942d7309162e60fd0c2d41dfe8f3e5463fcd51a5eb75de8aeb83989bce5e)

### 16、PhalApi-Image -- 图像处理 (由@喵了个咪提供)
目前此扩展支持：
 + 1、压缩裁剪
 + 2、图片水印
 + 3、获取图片基础信息
 + 4、GIF图片处理

[更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fea988caaca725341dc69ae266ab79dd9a9bd6aff7601683f694e4028cca0bddf1113635418fdae69c5eb623a329a0f9594a70abe50f5907583d7d9c05f99e5d79631cdf5849d8d0d8b4456cab279833f46e2b6a484493496bbd30ccd67b35558ccd1022294de6e7717e0cc9ca42a073687a5d14ff12ae6575257ba59f1ba8f3649d54bb10adcb6251e9b0f6b627da592f)

### 17、PhalApi-SMS基于PhalApi容联云短信服务器拓展 (由@喵了个咪提供)
目前此扩展支持：
 + 1、普通短信发送
 + 2、语言短信发送
 + 3、IVR外呼

### 18、PhalApi-ThirdLogin -- 第三方登录 (由@SteveAK提供)
 目前此拓展支持：
 + 1、QQ登录
 + 2、支持第三方登录添加

[更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fea988caaca725341dc69ae266ab79dd9a5554a8340f0871c594bb5fca5cefd257006a57e793e7edc071e86b5b346e7f70fdda54ad20c0fed8980c000a04eb047f27de1e95a5417f79a145179975c6720eedd88b7d42e08c5dd3e3650539373ab83ece8b2cb4950df06a7c196696a722769a6b6a8e4245e9e4aa0e8334ad222a8a7e93f1aa0db64bec66b8400dec045000)

## 19、PhalApi--Workman

本扩展旨在让socket编程，像用PhalApi开发接口一样简单，让开发者只需专注于业务逻辑，创建相应的Server类并编写action方法即可。此外，Server层还可以和其它接口共用Domain层和Model层，实现功能上的复用。

[更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fea988caaca725341dc69ae266ab79dd9a9d4600695bba129167219e372cc73fe0cbc0bcbf8c6df5eea1dd227f8d7b6678)

## 20、PhalApi-RongYun融云扩展类库  

基于融云官网上server-sdk的一个及时通讯的扩展类库。  

## 21、PhalApi-PHPWord

在接口开发中遇到需要生成Word文档的需求，发现一个PHPWord的第三方库能满足大部分需求，于是整合到了PhalApi框架中。

[更多请点这里查看使用文档](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fea988caaca725341dc69ae266ab79dd9ab6628e615b3e89bd95a4f562cadcd47b11ade144a872b7d37eece1bc8cf79093)

## 扩展开发指南 - 针对开发者
为了统一扩展类库的风格、便于用户更容易使用，这里建议：  

 + 代码：统一放置在Library目录下，各扩展包各自一个目录，尽量Lite.php入口类，遵循PEAR包命名规范；
 + 配置：统一放置在DI()->config->get('app.扩展包名')中，避免配置冲突；
 + 文档：统一提供WIKI文件对扩展类库的功能、安装和配置、使用示例以及运行效果进行说明；


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2e122d5ea525ac03a79237a7b4990825ed6db6a218abd9bb2b5e718d45306813b05dfc1b429880e1ac02170084c2edf8)