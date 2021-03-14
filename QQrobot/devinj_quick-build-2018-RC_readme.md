## Quick-Build-2018-RC

快速构建系统(Quick Build System)最终测试版

* 开发作者：蒋锋(QQ:78580822)
* QQ讨论群:386100815
* 特别感谢：刘明(木人)
* 系统网址： 
* 演示地址： (用户名:administrator,密码:admin)

### 您所要准备的仅是一个业务数据库，其他的已就位!
* 模块和常规功能的前台配置、零代码的开发过程； 
* 快速开发中小型的管理系统、后台管理系统以及大型系统快速原型化； 
* 已有业务系统的商业智能(BI)分析的快速搭建；(可统一管理多个数据库服务器中的多个数据库) 
* 软件开发新方式的极速体验；

### 开发前的准备
* 如果你只想使用本项目来架构你的业务系统，你要会使用一种java开发工具(eclipse)，了解tomcat发布项目的过程，以及有基本的数据库知识；
* 如果你想深入了解本项目中的开发过程和源代码，你需要了解java,spring mvc,hibernate等后台框架,mysql数据库,以及前台框架extjs,echarts等;

### 系统导入安装及运行
* 克隆项目：`git clone https://github.com/jfok1972/quick-build-2018-RC.git`，然后在eclipse中导入项目； 或者在eclipse中从git导入项目：`https://github.com/jfok1972/quick-build-2018-RC.git`；
* 本项目是maven项目，开发工具中必须安装有maven插件，项目导入后会自动安装所有依赖的jar包。

> 请注意：更新依赖jar包时国外的Maven仓库可能会由于网络问题出现错误，有时候tomcat中无法启动项目也是由于这个原因，建议改为阿里云Aliyun仓库，教程请自行网上搜索。

* 创建mysql数据库，脚本在文件在 `/quick-build-2018-RC/WebContent/database/quickbuild-mysql.sql`中；安装时请参阅该目录下的数据库安装说明;
* maven安装好依赖的jar包后，将项目发布到tomcat后启动服务器。
* 打开浏览器输入网址:`localhost:8080/quick-build`运行程序。
* 系统中已建有一个超级管理员(administrator,主要用来进行系统架构)和一个系统管理员(admin,主要用来进行业务系统的相关设置)(初始密码均为:admin,其他用户和新建用户的初始密码均为：123456)。
* 当前版本中的快速构建部分为全开源的系统(遵循GPL3.0协议)；商业数据分析(BI)也集成在本系统内，前台开源但后台不提供源码，并且不能用于生产环境。

### 系统架构与开发资料

[系统的获得安装与运行视频讲解](http://u.720life.cn/g/f18b4a37eaf8af1318d738e4ab50599579e26468ca5b657e37710243a17c3366cd9a6d6506749b10193a27aa05e210d9f0ff4955cabb606fa2d83e704f4ce63c97d3387a527e0f1bf2cb817fe16cc3eb4ebafd6446f522f55ef8bd32304316583450856454b7f1e6622c1c28aadaaef6)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9382695a94a4990f0b4b5535d0c856f43ee739d69635a0978cbc19467e2e11d30a); 
[快速构建系统开发手册(PDF)](http://www.jhopesoft.com/快速构建系统开发手册.pdf)； 
[快速开发系统extjs4版开发博客专栏](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded6f0d8d98025dcea0f6b7cfc16638e4323de7e93cee7a5f6a669588c2bc132f05ea2970478cef283817b13dd828b5c1e4); 
[快速开发系统extjs5版开发博客专栏](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded6f0d8d98025dcea0f6b7cfc16638e43211280fbf9db423f472ff6bfef1941f1f); 
[快速开发系统extjs6版(当前版本)开发博客专栏](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded6f0d8d98025dcea0f6b7cfc16638e432f3e25ffdb27d02d2790c12957d75e3aa);

为了更直观的展示系统开发的速度，特录制了一个20分钟快速搭建某小型业务系统的商业数据分析(BI)的视频，建立数据分析并把查询结果显示在首页上。 
[20分钟快速塔建业务系统的商业数据分析(BI)视频教程](http://u.720life.cn/g/f18b4a37eaf8af1318d738e4ab50599579e26468ca5b657e37710243a17c3366b0881af368ecc29e21082c1a73cfa4754ac5e1cd18e179ceb6810d38a8646764fe32ce7a7ba1764cc3355767025159dd68dba2e426487655e7b1960c221e0046)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93108b5d62a0bb2f7db0b35e06a035d1daa383bf4c4a750a4e51dff4bbbe3162a9)

### 系统基本功能、业务系统架构以及商业数据分析开发视频教程(不断更新中)

* [系统概述及主页面的说明](http://u.720life.cn/g/f18b4a37eaf8af1318d738e4ab50599579e26468ca5b657e37710243a17c33660fdc26e1085ffd07d3a97f3f05dbcb9c6e4f408d195a1c76e52cfe9caa6ae2f47589d76eb2014ba1b85e0eb2d26d5007b3690910dc7b228db16451ad0f9d0689)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba933853f32926b31d9cb8c04136a1861662d3a8f182aef259465f9139947cf84643)；
* [系统所有菜单功能简介](http://u.720life.cn/g/f18b4a37eaf8af1318d738e4ab50599579e26468ca5b657e37710243a17c33669cb47d48474bf52635648edea9e8d9750bddac03f6c41d857a016c027024730e1e335e28dde8a130cb46c4905ee8cd2a185e3a16ec0924e00c3a10be44b2279b)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93fa1966874df00be3a3c683bad1dcafd8557c8fbbc5ef0a13c033631e300214f1)；
* [系统模块界面及基本功能简介](http://u.720life.cn/g/f18b4a37eaf8af1318d738e4ab50599579e26468ca5b657e37710243a17c33668fc42dfa897d4e65432d843340896507400cac51a39c94fb3ea00853eeb43a0e21ca9e3ff649f0a020e710cd89dd194b35510821a52afe81740edade648e8adda39169e8606910e686c1ff8bb108aa7e)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9316bd686903f3af152a285c567611c6fe43d0a7d9487d08522c233b8470adfce3)；
* [系统内部配置表结构图说明](http://u.720life.cn/g/f18b4a37eaf8af1318d738e4ab50599579e26468ca5b657e37710243a17c33660b048869b9588c5b5e0450299e221adf2b7b1b99bff7bb5a855fa0cd6726c115abb1b654c317917a10aea021e50433efa9c84b833701782f8ce07107794b43809ffc47f9f78946a4f854693761770cac)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba931d7ff910330961f6ef3b2f3bbe69dcea55dd8a8717ce54d2a990b9cfcdbab66a)；
* [实体对象和字段及关联关系](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0adbb3f7e74cdacbeaedcfd6747215c306db414905ad12c5d6ea07f77ddd1f64654)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93f1f8b3d3ca141b99b15e31c01fbff4bf7ff89f1fa8426576b71f99688ef8c2c2)；
* [业务系统第一个模块的导入](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad686c4d6e45068ea9ef890e46ac694e1794d2c6ddd261c72f081a0ecfd32cb1a7)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba933c72a5616a02ac5a79d161218ffa814b2bcfdcd99857bc5a74112cbcfed1ba3b)；
* [业务系统第一个模块导航筛选导出](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad9396015749b48db38f84a1679e98985f91d6a5aef8b63c34913802f917051993)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9324d526234e3dc88dceefdf9001aa01ab60244580ef1de6886c19967ce22e9082)；
* [业务模块的附件功能](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad327202295b252582b3d30bd185a28bfc5d1ab419a81773e41772b87b4dd04e94)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93e96346dd2ce7cc07f3d83db2bfd27c9a953932a4ccfccab5b541592389daf79f)；
* [导入第二个模块及多对一字段的使用](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0adcf4b647b04e7a73583100aa59cf73b5ac8b935cd8614fe196b769f68f6c04f4d)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93f7c6b454a1738848c04f7d2cd6be0fe81386a8ba1956cc5ef78ac323bc200c2d)；
* [模块的一对多字段及应用场景](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0adeb3c617915e013d36ae9b6f64c6b151bf85fc2ea1f4563064e113eef983fd4e2)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93faf8c999f1167d731624bcb45e569093f341b370b61dcf690c18a4e15f1d8a0b)；
* [导入第三个模块和祖孙关联关系](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0adebc29151e2afa11d5c5146233e657881f01ca965751868491761594364dbdd67)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93f8b6a533debf3cfd0285aa8679367fb47c34bab0e1ab284e0005461b5bc0d68a)；
* [导入系统的其他模块和多级关联关系](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ada5e1058c4ef0cef6be941177171bc614e9294fea017f7e5c0a2460dfee9084df)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9331720709869917186fea61392128b4c20d1191f3ec16f084ae0fa7453797ffae)；
* [业务数据的导入及订单的基本操作](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad860425a7c62b1d44797f78e21b5c2f42bc603944d7d1ac016e75dd0fc07db639)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba935d07ff4249fda18843543c9edc191fabaf162d88e8ac664125a06db3e78243a3)；
* [实体对象附加字段的创建和用法](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0adad43de88c4a960304d0bf06aaad0428bd63082805ade44abd97ae4cfd1bee733)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9383a49f92ab70213efec22cf4a2e48f9a0063e9e157fce93c2960a2ce8696eef9)；
* [复杂的附加字段和sql语句的生成](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad40581159946b44a0ba8adb80ffd57185457b0a117cef845dbc4d8a11db683bdf)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba939b6ec08b7faf71ac060fadbe2af319fa5c451edaa73ca73f2e29388ce834976f)；
* [模块视图方案的用法](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad92b0df1f71a2c68da7a4496e8167a9a3f5950bf84d218c5b261d850ab35a66df)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9348512b865125e4f254ce5d3ab58693803028f8a4a1a778c4f78522978146d257)；
* [数据权限的用法和说明(核心功能)](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0adf27b988882cac5de608b47f978a1290ecbff9915c5c349cd0156e330d896ffc6)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9304394cd34ca7335819fc2af55fede058909e091fe92f9cd82c689bc71664f9ff)；
* [可选数据权限的用法和说明(核心功能)](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad9e0ed7b133d65f1f5d6289d0936207b8fec3d3a321356529f14cc53d2b8a9e25)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93268cf8b977a5bac3475bba45363bfc3faedde97f682466676bb49253f5fbf7d2)；
* [模块图表和自定义排序功能](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0adf25b9fbdfd201056993e7e23145d577e9be155d384217f867b4abfc61815c769)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba939cd4800ffc5a3b0f2d6bb551142fe3defeb63c72dd76fabfcd7b4e0e3b5bb4ad)；
* [业务系统加入工作流](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad905c2422060994fdff72a4b54f480fea2ee8c4d2559618c1be18577ffb5b0934)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba937aa0653f83900e7016a180bbb3e0d6273cb611449d183f9e06abe8e958ba78ca)；

### 商业数据分析(BI)的使用(此功能为本系统的最终目标。不断更新中)
* [商业智能分析(BI)的使用(1)选择分析字段、行展开、列展开、分析方案、字段列行的方案的初步介绍](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ade7e474ce5bd99b9827101dab36d21fdb97765cf013f964c3fc3ac6cf8891025f)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9376be5bf83754553083f7f19bfbdd567c718e7380814f68b7a59a309b08a4fedc)；
* [商业智能分析(BI)的使用(2)聚合字段的设置](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad510d2deeabc220e15c12c8d521281b0f128c186e7e17efb33d3d2d85392ed114)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93dfe0a22d5e2730c8398c1f5030f3297f2134acca62beb2d09597bf5fed7db056)；
* [商业智能分析(BI)的使用(3)可分组字段或表达式的设置](http://u.720life.cn/g/925895ada1ac79725dd88bd9d2bedc98eecff88275787f2dbe75ce15e9dbd0ad2f74b6f15fcc8df2403e6af25991d5383017184af3ea42f2b4484379b6212786)　[(网盘下载)](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9389fb75d654977151ca3d46b425f744947b870dd6eb491335445bdcb0ee3275a6)；
* 商业数据分析(BI)的进阶功能及图表；

### 系统源码分析和开发视频


### 建议和意见
* 如在使用过程中有任何建立或意见，以及发现有bug请联系我。

### 新版本的展望
* 新版本的开正在筹备中，后台准备使用spring boot,前台使用react + antd开发，如您有能力且有兴趣想参与后续版本的开发，可以与我联系。


开始加入吧！




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec71fb227601224877001492c6a412c9bed19cf2f81d2ef468f3271d6fb27b92a2dd6f2800fc4b8933e2cb91ff8689ff7052e00537484bd685e52664b4482a9c2)