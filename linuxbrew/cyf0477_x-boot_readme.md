# X-Boot
[![AUR](https://img.shields.io/aur/license/yaourt.svg)](https://github.com/Exrick/xmall/blob/master/License)
[![](https://img.shields.io/badge/Author-Exrick-orange.svg)](http://blog.exrick.cn)
[![](https://img.shields.io/badge/version-1.1-brightgreen.svg)](https://github.com/Exrick/x-boot)
[![GitHub stars](https://img.shields.io/github/stars/Exrick/x-boot.svg?style=social&label=Stars)](https://github.com/Exrick/x-boot)
[![GitHub forks](https://img.shields.io/github/forks/Exrick/x-boot.svg?style=social&label=Fork)](https://github.com/Exrick/x-boot)

> 作者大四作品 能力经验有限 如有错误欢迎指正 期待您的捐赠支持！

### 宣传视频
- [作者亲自制作XBoot文字快闪宣传视频](http://u.720life.cn/g/3dbdf3db25e44e8b8f39420676d0877f94476af631f1f9494a2f0f09dd05fd288eb2e1780fbf2599c8d7b5d183bd8a36)
- [作者亲自制作其他项目宣传视频](http://u.720life.cn/g/0b2e9c050c16e17e2de17da38fe221e14e891e7f464d808a8bfeaa8b64b73a975755db42cd94e8c8e680895eca0c9b51)
### [在线Demo](http://u.720life.cn/g/911ff1182f580031eaaecb3ee917ede7cd694e9fcaa1be403844b1b897cb652c)
http://xboot.exrick.cn
### 前台基于Vue+iView项目地址： [xboot-front](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460fc0e18d2093bbf257d725e3cb3b930e7361a44753394d2b8af4066c1c19bb4e)
### 项目简介 
- [x] 代码拥有详细注释 无复杂逻辑 核心使用 SpringBoot 2.0.5.RELEASE
- [x] JPA + Mybatis-Plus任意切换
- [x] 操作日志记录方式任意切换Mysql或Elasticseach记录
- [x] 极简代码生成 只需输入类名和字段 自动创建数据库表
- [x] 支持社交账号、短信等多方式登录 不干涉原用户数据 实现第三方账号管理
- [x] 基于Websocket消息推送管理、基于Quartz定时任务管理
- [x] Actuator可视化数据监控
- [x] 后台提供分布式限流、同步锁、验证码等工具类 前端提供空白Vue模版
- [x] 可动态配置SSO、短信、邮件、Vaptcha验证码等
- [x] 为什么要前后端分离
    - 都什么时代了还在用JQuery？ 

### 截图预览

![QQ截图20180826163917.png](https://i.loli.net/2018/08/26/5b826868e2359.png)

![QQ截图20180826163956.png](https://i.loli.net/2018/08/26/5b8268c57d1e3.png)

![QQ截图20180826164058.png](https://i.loli.net/2018/08/26/5b8268d63d156.png)

![QQ截图20180826164129.png](https://i.loli.net/2018/08/26/5b8268dec28ee.png)

![QQ截图20180826164144.png](https://i.loli.net/2018/08/26/5b8268e6a091f.png)

![QQ截图20180826164226.png](https://i.loli.net/2018/08/26/5b8268efab94a.png)

### [完整版截图细节展示](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1a64946d0a082f3f56e4996670bf7aa35d119bb3d3c3fa6a314d15d5aeef159e59d6464d43994652680a6040dc846c02a6e1ff7bf3af5cb44acb5dda8e229831798260408cd46e17f48832567bc042fac89fff26b18e6dde148041c7da5ecdf053)

### 前端所用技术
- Vue 2.5.x、Vue Cli 3.x、iView、iview-admin、iview-area、Vuex、Vue Router、ES6、webpack、axios、echarts、cookie等
- 前台为基于Vue+iView的独立项目请跳转至 [xboot-front](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460fc0e18d2093bbf257d725e3cb3b930e7361a44753394d2b8af4066c1c19bb4e) 项目仓库查看
### 后端所用技术
##### 各框架依赖版本皆使用目前最新版本
- Spring Boot 2.0.5.RELEASE
- SpringMVC
- Spring Security
- [Spring Data JPA](http://u.720life.cn/g/a8126de486174bbac1604ce886fda0d31a0321412be4829dd851399e1c6969acae9fe27f823c23e2bcefa6d37d49a83bac003efb7a03476e3d5fd57ee6f6a7dc5fbc8c4dd794765860733716ba48bc23)
- [MyBatis-Plus](http://u.720life.cn/g/cc2472c166ad93a8385c9f9684a56a6b1b30f5c30efcf10ccb085b1efd525bb1)
- [Redis](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046621f393e65c5d1a83526fbee5e95f767b84b880ad658a76463126efd4ccd71f21e27da5a5b8e8ea8e4b3c1094d5f5b30)
- [Elasticsearch](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046621f393e65c5d1a83526fbee5e95f767b84b880ad658a76463126efd4ccd71f2d8c8b9d30ea5d63dc18c57ca4ab7691c8b7daac68f14fd43ed40c46b3e2d4f5c)：基于Lucene分布式搜索引擎
- [Druid](http://u.720life.cn/g/b983aeda5211a3c813ce71b7178ba324)：阿里高性能数据库连接池 [Druid配置官方中文文档](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464e9ab1ba10d3588ded212abb6198c62a8699a8d98378f3094ad787d580b715b2a5f0da3526139dc91a414296f247ffb7e4a304f2d26d3304127224ec4893949c)
- [Json Web Token(JWT)](http://u.720life.cn/g/29b44050880331fd3d2682a984e1a32d)
- [Quartz](http://u.720life.cn/g/beb95a72271892e3173f0dad802e5ddf2956fdb02d87d3a76552cdc447c2fba3)：定时任务
- [Beetl](http://u.720life.cn/g/414ae20d41cd3495c197ae3ba6d18135cda59915f2a43fa2dbb5b39f6acfbae0)：模版引擎 代码生成使用
- [Hutool](http://u.720life.cn/g/17a180c798e6efa0a4495086733fde19b994d90e60e641368865fcaf5cdaf5d8)：Java工具包
- [Jasypt](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046dde8f0bd8190de39c77ec77ba08c6f2cdfff91b3105c7d9f5dba1be8f823c36bf10f051274e2e236ad9bcc24833cf51a)：配置文件加密thymeleaf作者开发
- [Swagger2](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046621f393e65c5d1a83526fbee5e95f767b84b880ad658a76463126efd4ccd71f25454f5e402ec875a280f760f94172aef)：Api文档生成
- MySQL
- [Nginx](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046621f393e65c5d1a83526fbee5e95f767b84b880ad658a76463126efd4ccd71f217fccfa33970fe39769d484342462181)
- [Maven](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046621f393e65c5d1a83526fbee5e95f767b84b880ad658a76463126efd4ccd71f294ce774a01a7afebfc6d8e8c13a28e51)
- 第三方SDK或服务
    - [七牛云文件存储服务](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b148468fe5a337933ee3e4dc0c976e35a408defe5fa513b350774ea0a7747ec0d3d10)
    - [Mob全国天气预报接口](http://u.720life.cn/g/30a395c9d5c18eaca077813853a1c8b54407882ed34a6e3d97c3bfb2b8a977c7a12e7f82b8e245c4f295489e28b86fe3)：需注册账号创建应用后申请填入AppKey后免费使用
    - 完整版
        - [Vaptcha人机验证码](http://u.720life.cn/g/2c4637848245fa6cc94ba816aac0e854f8382152adfa4631aeb40abce446d600)
        - [阿里云短信服务](http://u.720life.cn/g/eb87f0561ceb64c123dbcd0f1bea855beeec22b2eed5e2d1ffcf7937c86c3ec7)
- 其它开发工具
    - [Lombok](http://u.720life.cn/g/9cec729ef2d3c72b70f7caf7a64fe54c004be7f5a331560d74f301adfc8849d5)
    - ~~[JRebel](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046621f393e65c5d1a83526fbee5e95f767b84b880ad658a76463126efd4ccd71f242dccb893402bb55c66afecc00bd2e06)：开发热部署~~ 已无法免费使用 改回devtools
    - [阿里JAVA开发规约插件](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046eee1f37ed667d08f5c30df231e894fa2)

### 本地运行部署
- 安装依赖并启动：[Redis](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046621f393e65c5d1a83526fbee5e95f767b84b880ad658a76463126efd4ccd71f21e27da5a5b8e8ea8e4b3c1094d5f5b30)、[Elasticsearch]https://github.com/Exrick/xmall/blob/master/study/Elasticsearch.md
- [Maven安装和在IDEA中配置](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046621f393e65c5d1a83526fbee5e95f767b84b880ad658a76463126efd4ccd71f294ce774a01a7afebfc6d8e8c13a28e51)
- 建议使用IDEA([破解/免费注册](http://u.720life.cn/g/a951c120f3b4383a914a3c153183e0ac36630217d723a80f0d4836df3a2d9dc6) 安装 `Lombok` 插件后导入该Maven项目 若未自动下载依赖请在根目录下执行 `mvn install` 命令
- MySQL数据库新建 `xboot` 数据库，配置文件已开启ddl自动生成表结构但无初始数据，请记得运行导入sql文件
- 修改配置文件 `application.yml` 相应配置，其中有详细注释，所有配置只需在这里修改
- 编译器中启动运行 `XbootApplication.java` 或根目录下执行命令 `mvn spring-boot:run` 默认端口8888 访问接口文档 `http://localhost:8888/swagger-ui.html` 说明启动成功 管理员账密admin|123456
- 前台页面请启动基于Vue的 [xboot-front](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460fc0e18d2093bbf257d725e3cb3b930e7361a44753394d2b8af4066c1c19bb4e) 项目，并修改其接口代理配置
> 温馨提示：若更新代码后，记得更新sql并清空缓存
### 开发指南及相关技术栈文档
- [项目基本配置和使用相关技术栈文档【必读】](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1a8c4001642a8738eee5bf48363a0d9bf7bcb9566f025b39a2d4bd4392e17d769bcf7e574a0d9e3cc99959d7ee9877b9854b776ffe0cc388398595a29be8e4912b6c29fde9c04ac1a7dd8987bd8c326c2c40da82cc2c581703320fe28f33c179ee6cd9c664cea5cf0ca9f33e34f398373fb933125a12846a3a1ec4964e305a5d553bb8b50895dd0b8a250cc8267ef962bb99bf266fc7e79f46f8e27d8a65b5faf2632f009b6931191c260c93ac7a53b251a724ed444c7326dc03368b395d8b1a30)
- [如何使用XBoot后端在30秒内开发出增删改接口](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1a03f79fd83d9efec356eb7b5f6950853cc63c206fa0808dae2af82e38f00afdb48b8d8826841e8f472de4b5910da3abcadce5d4383096be179f108a21ea7433b1b66229554fe74aae10ab6c648523d4504079f0bd44bd9b406576bc2f696fdb5baf354842e5e8aea6ba04dc7db6280864a794ea008b88a720977278dbed5bd6b5108762a8a74e4745e897feb52616b8af5fdcf02c0aae856051cc8da50a0a732a61ec082177593812efd4a5e97d34dbb9)
- [具体X-Boot增删改文档示例](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1a90a70966141f2fd8d2920fa599ae8917)
- 完整版
    - [第三方社交账号登录配置](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1ad736781bd83ac6819265aba4c92ba4f45ed37da95b4085b7134c928610e8e5317fd0c01bde66f521bbdee418c731ccdef5ea46832461267b76bdf34672cffa70859c2113da0fc7956fa1fe6c6cecae170d5174fa659a8bbce7c458139599c4f53ac997072ef365859d7ce57e98f3da13)
    - [短信登录配置](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1ad10a3a6138e79224281d2463e8bca4111e5eedc1085778b9f51d51074207c8a73c6b0dae54a34003b266c45fb6b43507422be5d376070541e0b7c2eed4d5bf9a)
    - [Vaptcha人机验证码配置使用](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1a3e980d8959778162916771e3b6b9e4c6a931f52b30e9a337786d99d65c8b391f05df75be1fa61afe39fcd2d1dcf3be010d7c20eae315a173fe5012f2a08f910aa503d18bc372818cf20a2c36e8bd377504f5b397e44f4dd742f42402db3eafef)

### [分布式扩展](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d4a5102bc3f18e88a1add1b6e227ad9949be8e1b7f727bbbefdd46f2fc36a6b8d36b80a105f781bf9c2446fa6f94b410dfab1955301c5be13be4b8fd91a66318)

### XBoot后端学习分享（更新中）
1.[Spring Boot 2.x 区别总结](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1a81e42ca5e4366c83a1eae4636f650dbf415d1f8e31dcba51ebdc9a89c0ff17813dd0734149980ceff187a8d4d050cf528c4fe1f0f454e1f33a72e919e52703f5)

2.Spring Security整合JWT

3.Spring Security实现动态数据库权限管理

4.[Spring Boot 2.x整合Quartz](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1acfb22aff3a769e5f54aa0146e81edd0ae2acd8c881a288e0f171f2a1279373de20b09874a2acae5cad5a8aca557c2b5b)

5.[基于Websocket实现发送消息后右上角消息图标红点实时显示](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1a74a915fd9a6dce349bad090819acc0b49e2c3aa7fbb28a3ab5a7c36501549ec9ef9549f69b801606dd6cec0b1c647d6353ff03b16ccadf0fb6376752b6ff0f34d9090b78cd10be1a8b81f97dca8c83a31414795f65c1e318a628ced309957b0c5c6371c57da7e00fad283b69c3146e97b2f207857564cb83a1c9b6ddfc9efbfef6ea1ead58be1b28ab94e52206c316dcb335949fa82d80318d6609852c68e961d56cd8c632d4254752ae26a1d4d609d1a2cb7deb65272a10bf6b93c2cea68080cbeb2f8140de0e1fa2cb85853bb6c4558c63c18ad3d0b72ad07064c34b33c3e8)

### Docker下后端集群部署(更新中)

> 前端集群部署请跳转至[xboot-front](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460fc0e18d2093bbf257d725e3cb3b930e7361a44753394d2b8af4066c1c19bb4e)项目查看

1.[Docker的安装与常用命令](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304625e135afa21f441449ccd7e5d5020d1a60746a405f8ae48cb0a17f171bf725e8bdd05ee18ebf410212b63a850408ccff5d26e49b5e17adf9ff4a00004a27219f48bc6828a33303f3f6267f1327aa7c95fe4132683ab8538be376b9adeda4800fa13fdcf13719e87d7568ea6757c37886)

2.基于PXC架构Mysql数据库集群搭建

3.Redis集群搭建

4.Elasticsearch集群搭建

5.XBoot后端集群部署

### 作者其他项目推荐
- [XPay个人免签收款支付系统v1.2](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046336d47cc5a778493ecb22d7d19989437)

    - 现已支持移动端支付 手机扫码体验

    ![](http://p77xsahe9.bkt.clouddn.com/18-7-21/16350122.jpg)

- [XMall：基于SOA架构的分布式电商购物商城](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304632c7085a3fcc4563a9dbc223763a621d)

    ![](https://i.loli.net/2018/07/22/5b54615b95788.jpg)

- 微信小程序APP 
    - [前台源码点我提前获取](http://u.720life.cn/g/7f8859545e78c62e8ea6e10aaf83048f9cbff3222637e0063fd87f035d6b2159) [预览视频](http://u.720life.cn/g/cbad280c284c0afc32b549dc6e61524e7b5a28c21a3c86b889c69476b9042f8ff0c3b9576ba3ffd284b8e1936a8f8f1b)

    ![](https://i.loli.net/2018/07/21/5b52e1de385e7.png)
- 机器学习笔记
    - [Machine-Learning](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f60cde1810ebeaa233cfa5d468384efc12b8aca429340e4d8fba06fb0ef0b88d)
### 技术疑问交流
- QQ交流群 `475743731(付费)`，可获取各项目详细图文文档、疑问解答 [![](http://pub.idqqimg.com/wpa/images/group.png)](http://shang.qq.com/wpa/qunwpa?idkey=7b60cec12ba93ebed7568b0a63f22e6e034c0d1df33125ac43ed753342ec6ce7)
- 免费交流群 `562962309` [![](http://pub.idqqimg.com/wpa/images/group.png)](http://shang.qq.com/wpa/qunwpa?idkey=52f6003e230b26addeed0ba6cf343fcf3ba5d97829d17f5b8fa5b151dba7e842)
- 作者博客：[http://blog.exrick.cn](http://u.720life.cn/g/d9facb80ece1075627c5e84d9677b2c19a52006991cae3006c3cacccaf404d77)
### [捐赠](http://u.720life.cn/g/7f8859545e78c62e8ea6e10aaf83048f9cbff3222637e0063fd87f035d6b2159)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ece7357f576baa5c8a07a5ddbd11e129e5be12ae8973a57151dacd36fa08db60580a5882303a510d93d419e05333d5d1f)