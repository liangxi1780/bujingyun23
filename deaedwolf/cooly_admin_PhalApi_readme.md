![apic](http://webtools.qiniudn.com/master-LOGO-20150410_50.jpg)  

## [PhalApi 1.4.2 - 助你创造价值！](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec59c6b9c40658eff1b4c982ae988586683a)  
PhalApi，简称π框架，是一个PHP轻量级开源接口框架，专注于接口开发，致力让接口开发更简单。它：  
+ 致力于快速、稳定、持续交付有价值的接口服务
+ 关注于测试驱动开发、领域驱动设计、极限编程、敏捷开发
+ 有众多的扩展类库，与更多开源项目一起提供高效便捷的解决方案
+ 支持HTTP、SOAP和RPC协议，可用于快速搭建微服务、RESTful接口或Web Services
   
PhalApi代码开源、产品开源、思想开源，请放心使用。更多请访问[PhalApi官网](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec59c6b9c40658eff1b4c982ae988586683a)。再次感谢**开源中国**、各位贡献者和同学。  
  
> RELATED: [PhalApi English Version at release-en](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463f6c936c4ed16a390973c0c6dc878331d92d1439f8ec0f50f93399c2eca678ea5c9bbdc0dfa85c9548ffddc8b462c3b8)。

### 导读
本文内容主要分为三部分，即：  
+ PART 1：安装、在线体验与在线接口文档
+ PART 2：快速开发、单元测试、目录结构、SDK包和Library扩展类库
+ PART 3：背景回顾、贡献者、许可与更新日记

更多请访问[在线文档](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec592d9eebf7964a4adc8b02e63299f6a86a)。  

## 1-1、安装
+ 请从release分支拉取发布版本的代码
+ 推荐部署于Linux服务器
+ 建议PHP >= 5.3.3

将代码下载解压到服务器后，打开浏览器，访问安装向导（推荐使用nginx，并将根目录设置为```Public```）：  
```
http://localhost/PhalApi/Public/install/
```
  
![](http://7xiz2f.com1.z0.glb.clouddn.com/QQ20151024155002.jpg)  


访问默认接口服务，验证是否安装成功：  
```
http://localhost/PhalApi/Public/demo/
```
![](http://webtools.qiniudn.com/20150211_default_index.jpg)  
更多其他创建项目的方式，请访问[创建一个自己的项目](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec596c7dfb5a64de8b10e4b81524022964c490835de4bd1bd1997516df1bbf9c755cc5f9a2fe3388bbcc76b55f33867fa8ae1d1e60b7e87df3ea0d6227ba6852a7d3b65747f95ffaa6d47a5afc6b672f27758d5ea9ee295277770d656fd1ee105179b2df51095a56f19b7dfce273118518f8)。  

### 框架升级与框架共享
我们会尽最大的努力保证完美兼容性的升级。当框架有新版本需要升级时，只需要简单一步：更新替换```./PhalApi/PhalApi```核心框架目录即可。  
  
如果需要多个项目共享使用PhalApi框架，可以把```./PhalApi/PhalApi```移到任何位置，然后对应修改```./PhalApi/Public/init.php```文件中引入路径即可（但会导致部分脚本命令不可用）。如：  
```
require_once API_ROOT . '/path/to/PhalApi/PhalApi.php';
```

## 1-2、在线体验

 + 默认的接口服务：  

```
http://demo.phalapi.net/
```

 + 带参数的示例接口：

```
http://demo.phalapi.net/?service=Default.Index&username=oschina

{
    "ret": 200,
    "data": {
        "title": "Hello World!",
        "content": "oschina您好，欢迎使用PhalApi！",
        "version": "1.3.4",
        "time": 1473863280
    },
    "msg": ""
}
```

 + 故意请求一个非法的服务：

```
http://demo.phalapi.net/?service=Demo.None

{
    "ret": 400,
    "data": [],
    "msg": "非法请求：服务Demo.None不存在"
}
```

## 1-3、在线接口文档（自动生成）
按框架指定的格式完成接口代码编写后，PhalApi会自动生成在线接口列表文档和在线接口详情文档，以方便客户端实时查看最新的接口签名和返回字段。   
  
### (1) 在线接口列表文档  
访问对应项目路径下的```listAllApis.php```可查看此项目下全部的接口服务，如访问：  
```
http://demo.phalapi.net/listAllApis.php
```
![](http://7xiz2f.com1.z0.glb.clouddn.com/QQ20160914230528.jpg)

### (2) 在线接口详情文档  
访问对应项目路径下的```checkApiParams.php```，并传递```?service=xxx.xxx```参数即可查看具体的接口文档，如访问：
```
http://demo.phalapi.net/checkApiParams.php?service=Default.Index
```
![mahua](http://7xiz2f.com1.z0.glb.clouddn.com/index20160728224002.jpg)

## 2-1、快速开发
### (1) 编写一个Hello World!接口  
以下代码需要放置到接口类文件```./Demo/Api/Welcome.php```中：  
```
 assertNotEmpty($rs);
        $this->assertArrayHasKey('code', $rs);
        $this->assertArrayHasKey('msg', $rs);
        $this->assertArrayHasKey('info', $rs);

        $this->assertEquals(0, $rs['code']);

        $this->assertEquals('dogstar', $rs['info']['name']);
        $this->assertEquals('oschina', $rs['info']['from']);
    }
```
运行效果：  
 ![运行效果](http://static.oschina.net/uploads/space/2015/0204/234130_GSJ6_256338.png)  

对于框架的核心代码，我们也一直坚持着单元测试，其核心框架代码的单元测试覆盖率可高达96%以上。
  

## 2-3、主要目录结构
```
.
│
├── PhalApi         //PhalApi框架，后期可以整包升级
├── Library         //PhalApi扩展类库，可根据需要自由添加扩展
├── SDK             //PhalApi提供的SDK包，客户可根据需要选用
│
│
├── Public          //对外访问目录，建议隐藏PHP实现
│   └── demo        //Demo服务访问入口
│
│
├── Config          //项目接口公共配置，主要有：app.php, sys.php, dbs.php
├── Data            //项目接口公共数据
├── Language        //项目接口公共翻译
├── Runtime         //项目接口运行文件目录，用于存放日记，可软链到别的区
│
│
└── Demo            //应用接口服务，名称自取，可多组
    ├── Api             //接口响应层
    ├── Domain          //接口领域层
    ├── Model           //接口持久层
    └── Tests           //接口单元测试

```

以下为一示例目录结构图解：
![](http://7qnay5.com1.z0.glb.clouddn.com/QQ-20151015214456.jpg)   

## 2-4、基于接口查询语言（ASL）的SDK包支持
目前已提供的SDK有：  
 + [JAVA版](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec596c7dfb5a64de8b10e4b81524022964c4668e4604ec82d197725d8751e56e52a8d4e400d40e15a3f383b65f8e47274a0eb52748acb183b8605d58abc22f554a0fe2318ebd27deb4edcf989c3e1ec13499)
 + [Objective-c版](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec596c7dfb5a64de8b10e4b81524022964c46f7fb167cff22e5ffe5e0624fc2cdea1dc56cddfb4388b8b5ae36f7fb0a8d4d7f283d31598e51d94cb1cc374a088179eb0eb0c874be16ad5cd7dce43131d9399)
 + [PHP版](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec596c7dfb5a64de8b10e4b81524022964c416d951daa595affc2b204eabcdfdc8335e44b5556a35031b4f6d75cee7cae43ae8347fb41690871444bfc6adb1fbf722a66ccc3a7fc73a4727e18546b43ca8fc)
 + C#版
 + JS版
 + Golang版
 + React-Native版
 + [Ruby版](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec596c7dfb5a64de8b10e4b81524022964c405749ef4165a75d417bb372893fcd2cf9858fd32fd43d4d45ae004b7d88023c0d0bd7db8bdcc92f726a91f07f73637cd0dbae93de65ad0b20461dda104c88e56)
 + Python版

基于接口查询语言，可用一句话来描述接口请求，如JAVA的请求示例：  
```
PhalApiClientResponse response = PhalApiClient.create()
       .withHost("http://demo.phalapi.net/")
       .withService("Default.Index")          //接口服务
       .withParams("username", "dogstar")     //接口参数
       .withTimeout(3000)                     //接口超时
       .request();
```
  
## 2-5、PhalApi-Library扩展类库
PhalApi框架扩展类库，致力于与开源项目一起提供高效便捷的解决方案，更多请查看：[PhalApi-Library](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d7a13a099f5b8bb392b16601f49c8c1fee177617c96a970ace65375e9d3f484ab)。

## 3-1、背景回顾
过去十年，是互联网时代；如今的十年，是移动时代。  
  
在iOS、Android、Windows Phone、PC版、Web版等各种终端和各种垂直应用不停更新迭代的大背景下，显然很是需要一组乃至一系列稳定的后台接口支撑。接口，显然是如此重要，正如Jaroslav Tulach在《软件框架设计的艺术》一书中说的：_API就如同恒星，一旦出现，便与我们永恒共存。_    

所以，这里希望通过提供一个快速可用的后台接口开发框架，可以：  
+ 一来，支撑轻量级项目后台接口的快速开发；  
+ 二来，阐明如何进行接口开发、设计和维护，以很好支持海量访问、大数据、向前向后兼容等；  
+ 三来，顺便分享一些好的思想、技巧和有用的工具、最佳实践。  
  
如果您有接口项目开发的需要，又刚好需要一个PHP接口框架，欢迎使用！我们也致力于将PhalApi维护成像恒星一样：**不断更新，保持生气；为接口负责，为开源负责！**  

## 3-2、加入我们
显然，这只是一个开始，我们要走的路还很长。PhalApi是我们（开发团队）的框架，更是我们（所有人）的框架。在一个人还年轻的时候，我觉得，就应该着手致力做一些对社会有意义的事情，一如开源。欢迎&期待你的加入！   
  
在加入前，可先查看[致框架贡献者：加入PhalApi开源指南](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec596c7dfb5a64de8b10e4b81524022964c476c5b37b762712585d3a40734310e81c8f207d274577b4964eb02b4b246c9cc9d7a4874cc6062a1034185bc520ecf1f664c5615ca2a862a020f1d0148009dd8ec26a2ffc37c353cc0e5db862b269c4cdee30a341b377860239c63d0fc5bd711879f5a132610e2dfcc6e4c858a75d0c3f54ee87354b347446184fd1e207a1519b5760125cb7d922b0af729022bfae34bd)。至此，感谢以下贡献者（排名不分先后）：  
+ Aevit
+ dogstar
+ George
+ Scott
+ Summer
+ zz.guo（郭了个治浩）
+ 小艾
+ 大蝉
+ 冰霜
+ 火柴
+ 黄苗笋
+ 文振熙（喵了个咪）
+ 爱编程的小逗比
+ ... ...
  
## 3-3、许可
PhalApi是开源框架，承诺永远免费，使用GPL协议，更多请访问[许可](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec59d99b4315a8c9871ced362dbf31c11bd2)。  

## 3-4、更新日记
此 [更新日记](http://u.720life.cn/g/8727bb51e13cb123f449c1dfc91dec596c7dfb5a64de8b10e4b81524022964c45c76f54bdc55df30dcd4fd5dd7b2ec512ec79103cc26820be1436e46ada6efd4297e7181a6b9245a7967c486e0647c21) ，主要是为了说明，我们一直在努力更新和维护。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e358c58ef9caee4939b686764ae069d189b47a3cb9c9acfd5718f5531fa490b6da88679c46f8dc278fc05ac49d3c84ee0)