# DBlog简介
DBlog是一款简洁美观、自适应的Java博客系统。使用springboot开发，前端使用Bootstrap。支持移动端自适应，配有完备的前台和后台管理功能。
  
**网站预览**    
 
[https://www.zhyd.me](http://u.720life.cn/g/18bbd2c33807f8b838ed0a0ae89d415bad18847e42c683d71d6b91f29869e34a)  

**开源地址**   
1. [Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4b774c2ac54f756cf8eb6d8afc642938ec)    
2. [Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d0c258f370fd1193f4dd9436d1c75cb1d6107d1a4c7f3af9faf0245cb6eeadef)    

## 写在前面的话
ps: 虽然我知道，大部分人都是来了**直接下载源代码**后就潇洒的离开，并且只有等到下次**突然想到**“我天~~我得去看看DBlog这烂项目更新新功能了吗”的时候才会重新来到这儿，即使你重新来过，我估计你也只有两个选择：    

发现更新代码了 --> 下载源码后重复上面的步骤    
发现没更新代码 --> 直接关闭浏览器

虽然我知道现实就是如此的残酷，但我还是要以我萤虫之力对各位到来的同仁发出一声诚挚的嘶吼：

**如果喜欢，请多多分享！！多多Star！！fork可以，但还是请star一下！！**


### 开发环境

| 工具    | 版本或描述                |
| ----- | -------------------- |
| OS    | Windows 7            |
| JDK   | 1.7+                 |
| IDE   | IntelliJ IDEA 2017.3 |
| Maven | 3.3.1                |
| MySQL | 5.6.4                |

### 模块划分

| 模块         | 释义                      |
| ---------- | ----------------------- |
| blog-core  | 核心业务类模块，提供基本的数据操作、工具处理等 |
| blog-admin | 后台管理模块                  |
| blog-web   | 前台模块                    |


### 技术栈

- Springboot 1.5.9
- Apache Shiro 1.2.2
- Logback
- Redis
- Lombok
- Websocket
- MySQL、Mybatis、Mapper、Pagehelper
- Freemarker
- Bootstrap 3.3.0
- wangEditor
- jQuery 1.11.1、jQuery Lazyload 1.9.7、fancybox、iCheck
- 阿里云OSS
- kaptcha
- Qiniu
- ...


### 使用方法

1. 使用IDE导入本项目
2. 新建数据库`CREATE DATABASE dblog;`
3. 导入数据库`docs/db/dblog.sql`
4. 修改(`resources/application.yml`)配置文件
   1. 数据库链接属性(可搜索`datasource`或定位到L.19) 
   2. redis配置(可搜索`redis`或定位到L.69)
   3. mail配置(可搜索`mail`或定位到L.89)
   4. 【[七牛云](http://u.720life.cn/g/758b471f436f1c487fed420972dad3d6)】配置可搜索`qiniu`或定位到L.135
5. 运行项目(三种方式)
   1. 项目根目录下执行`mvn -X clean package -Dmaven.test.skip=true`编译打包，然后执行`java -jar target/blog-web.jar`
   2. 项目根目录下执行`mvn springboot:run`
   3. 直接运行`BlogWebApplication.java`
6. 浏览器访问`http://127.0.0.1:8443`


**后台用户**

_超级管理员_： 账号：root  密码：123456  （本地测试使用这个账号，admin没设置权限）

_普通管理员_： 账号：admin  密码：123456

更多详情，请参考【[Wiki](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4b545911174146a7e5e4f8f8fe023eb3c5)】

### 更新日志

2018-05-18

**修复bug：**

1. web端自动申请友链后不显示的问题
2. config表修改后不能实时刷新的问题
	
**增加功能：**
1. 网站赞赏码
2. 百度推送功能(链接提交到百度站长平台)
	
**修改功能：**
1. 百度api的ak和百度推送的token以及七牛云的配置改为通过config表管理
3. admin模块菜单通过标签实时获取
3. 弹窗工具类js结构调整

你能看到这儿已经很不容易了，剩下的自己先摸索摸索吧，实在不行，加QQ群[190886500](http://u.720life.cn/g/88d3be70c797d2a69a24ab56221f9e0339fd68ed2b2e8afb401b350bf89ee6214ab4efd73aab4738933ec8b1029c1e65fb5466d813a40a55500c576446f4f18cd61680ff111410d62d24ab81fd94f98721b060f0b021f2f4b7e9a34c75968e98c85fa40d8344991ff2a9ab52e0db7b2e)，进群可以选择性的备注：~~欧巴群主我爱你~~咳咳，鉴于部分群友的抗议，该备注就不用了

### 图片预览

**前台页面**
![PC-首页](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/pc-index.png?v=1.0)
![PC-文章详情页](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/pc-detail.png?v=1.0)
![手机](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/m.png?v=1.0)
**后台页面**
![首页](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/admin-index.png)
![菜单](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/admin-menu.png)
![文章列表](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/admin-articles.png)
![发表文章](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/admin-article2.png)
![角色列表](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/admin-role.png)
![角色分配](https://gitee.com/yadong.zhang/DBlog/raw/master/docs/img/admin-role2.png)


 ### 生命不息，折腾不止！ 更多信息，请关注：
 1. [我的博客](http://u.720life.cn/g/18bbd2c33807f8b838ed0a0ae89d415bad18847e42c683d71d6b91f29869e34a)
 2. [我的微博](http://u.720life.cn/g/c1e3906cb73241d8bdbe53b5d457b17dc5e7cf5c1bd2599d2e47e0359722cd11)
 3. [我的头条号](http://u.720life.cn/g/118b7af38f18204760fd37a6bfa049ce966f36fd837fb4636774805882b6e67bf4ba6b0df274ad1d0f31575221ab137b)
 4. [我的mooc](http://u.720life.cn/g/9bdca284b716378ad8944a645c76d01825cac3ba4c37de1f1e3f15ff12923df27d7eaa23b08198cceb3c23f91ba9472a)

 ### 有任何问题可以
- [给我留言](http://u.720life.cn/g/18bbd2c33807f8b838ed0a0ae89d415b550d1e46debbe31233e96fe2aa0dc388)


### 开源协议

 [MIT](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8b522db5d81d0ec8c59230a5fb41b4b05e6af079e83c97b1c6913dbb9723c8fab045d52719580033ccb6c3a7275eddb)






 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed00cfb9d6d8eef9ad5bbb329d225a6488a7fa5c5961d0846a3c63eebd0c4a64152a4e1a900d7eba2d2e5ed7a723539ef)