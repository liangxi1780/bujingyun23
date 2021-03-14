### 一、前言

最近整合`Spring Boot`+`Spring Security`+`JWT`+`Vue` 完成了一套前后端分离的基础项目，这里把它开源出来分享给有需要的小伙伴们

功能很简单，单点登录，前后端动态权限配置，前端权限精确到 `按钮` 级别，后端权限精确到 `url` 上，剩下的就是一些关联表的增删改查，例如：用户管理，角色管理，菜单管理，系统日志等...

###### Spring Security入门系列教程：

1. [SpringBoot集成Spring Security入门体验（一）](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded28042e95d1048f38817fd9571c443d94544bf0e97d7cf5586ea9b11446aaf2b8dcd6062c131886da3044da4502439b74)
2. [Spring Security 自定义登录认证（二）](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded28042e95d1048f38817fd9571c443d94544bf0e97d7cf5586ea9b11446aaf2b87d962352266dbaf2f741a31ede646e31)
3. [Spring Security 动态url权限控制（三）](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded28042e95d1048f38817fd9571c443d94544bf0e97d7cf5586ea9b11446aaf2b84ec39f00c7b3048df2ee306943cab16f)
4. [Spring Security 整合JWT（四）](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded28042e95d1048f38817fd9571c443d94544bf0e97d7cf5586ea9b11446aaf2b8fccfdaf00079944c4f0056d2f62188c0) 

###### 项目部署

[docker-compose部署项目到服务器](http://u.720life.cn/g/35b21c43ae5f5910eefb82bca3ede319adb5fde5a0738bd84a747d2df5bff9de2e11779f012cf245e680673362c54791c1a347ed2e619dbc194c3094a3f7ebf0) 

###### 开发环境：

1. JDK 1.8
2. IDEA 2019.2
3. MySQL 5.7
4. Node.js 10.15.3
 
###### 项目使用技术栈：

前端：Vue + Axios
后端：Spring Boot 、 MyBatis-Plus
权限：Spring Security
.......

### 二、页面截图

###### 1、登录页面
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191023183018204.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly96aGVuZ3FpbmcuYmxvZy5jc2RuLm5ldA==,size_16,color_FFFFFF,t_70)
###### 2、首页
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191023183238343.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly96aGVuZ3FpbmcuYmxvZy5jc2RuLm5ldA==,size_16,color_FFFFFF,t_70)
###### 3、用户管理
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191023183257905.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly96aGVuZ3FpbmcuYmxvZy5jc2RuLm5ldA==,size_16,color_FFFFFF,t_70)
###### 4、角色管理
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191023183325162.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly96aGVuZ3FpbmcuYmxvZy5jc2RuLm5ldA==,size_16,color_FFFFFF,t_70)
###### 5、菜单管理
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191023183352498.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly96aGVuZ3FpbmcuYmxvZy5jc2RuLm5ldA==,size_16,color_FFFFFF,t_70)
###### 6、系统日志
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191023183430412.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly96aGVuZ3FpbmcuYmxvZy5jc2RuLm5ldA==,size_16,color_FFFFFF,t_70)

---

### 项目源码

> 觉得还可以的话，请给个❤

###### GitHub地址：[https://github.com/zhengqingya/xiao-xiao-su](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467e9770690d506ace33e09e5930e7777a7945b7215f7540495cabad2f957e5639)
###### 码云地址：[https://gitee.com/zhengqingya/xiao-xiao-su](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edb6d09daf6ee6a786f1cefbfead7779c3e3a85ddce1c69abda1f4551612c300b)




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec6020cd0e1167935304c81a15dacc0200cc705dd7b34b2cc86239dc136d2c4bfbbe6b716e93f36683f250ba65706f8eb)