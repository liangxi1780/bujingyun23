android-app
===========

本项目采用 GPL 授权协议，欢迎大家在这个基础上进行改进，并与大家分享。

如您感觉本项目中有不妥之处或者有不爽的地方，欢迎提交问题或更改方案，项目小组会
及时的对您提交的修改给予反馈。希望能为开发者提供一款开源好用的Android版客户端产品。
一款好产品需要大家共同努力，大家共勉！

# **eoe社区 Android 客户端项目简析** #

*注：本文假设你已经有Android开发环境*

本文以eclipse为例 
启动Eclipse，导入Android客户端项目，请确保你当前的Android SDK是最新版。
如果编译出错，请修改项目根目录下的 project.properties 文件。
推荐使用Android 4.0 以上版本的SDK： 

target=android-14
## **一、工程目录结构** ##
根目录 
>├ source    
>├ LICENCE.txt  
>├ README.md  

目录简要解释 
根目录 
>├ source --源代码   
>├ LICENCE.txt --开源协议  
>├ README.md --项目帮助及项目信息  

## **二、源代码目录结构** ##
source 
>├ src    
>├ libs  
>├ res  
>├ AndroidManifest.xml  
>├ proguard-project.txt  
>└ project.properties  

**1、src目录**  
src目录用于存放工程的包及java源码文件。

下面是src目录的子目录：

> src  

>├ cn.eoe.app --存放程序全局性类的包 
>├ cn.eoe.app.adapter --存放适配器的实现类的包  
>├ cn.eoe.app.adapter.base --存放适配器基类的包 
>├ cn.eoe.app.biz --存放ＤＡＯ类的包 
>├ cn.eoe.app.config －－存放常量，配置和api接口等类的包 
>├ cn.eoe.app.db --关于sqlite操作相关的类的包 
>├ cn.eoe.app.db.biz --详细的增删改查类的包，暂时仅有一个类 
>├ cn.eoe.app.entity --实体类包 
>├ cn.eoe.app.entity.base --实体类基类包 
>├ cn.eoe.app.https --网络访问相关类的包 
>├ cn.eoe.app.indicator --导航相关的类包 
>├ cn.eoe.app.slidingmenu --滑动菜单相关类包 
>├ cn.eoe.app.ui --界面相关的包，activity的类 
>├ cn.eoe.app.ui.base --activity相关的基类包 
>├ cn.eoe.app.utils --工具类包 
>├ cn.eoe.app.view --Fragment相关类的包 
>├ cn.eoe.app.widget --自定义view组件包 
>
>├ com.google.zxing.camera --第三方定义，控制摄像头包 
>├ com.google.zxing.decoding -- 二维码图像解码包 
>├ com.google.zxing.view -- 自定义View，控制拍摄取景框和动画等 

 
**2、libs目录**  
libs目录用于存放项目引用的第三方jar包。

libs目录里的jar包文件：

libs
>├  android-support-v4.jar --v4兼容包 
>├ jackson-all-1.9.2.jar --解析json的包 
>├ umeng_sdk.jar --友盟的sdk 
>├ zxing-1.6.jar --二维码处理的包 

**3、res目录**  
res目录存放工程用到的图片、布局、样式等资源文件。 
res目录的子目录： 

res  
>├ anim  
>├ color  
>├ drawable  
>├ drawable-hdpi  
>├ drawable-ldpi  
>├ drawable-mdpi  
>├ drawable-xhdpi  
>├ interpolator 
>├ layout  
>├ menu  
>├ raw  
>├ values  
>└ values-zh  

**4、AndroidManifest.xml** 
AndroidManifest.xml用于设置应用程序的版本、主题、用户权限及注册Activity等组件及其他配置。

## **三、程序功能流程** ##
**1、APP启动流程**

AndroidManifest.xml注册的启动Activity是"cn.eoe.app.ui.SplashActivity"，然后进入到主界面，对应的

Activity是“cn.eoe.app.ui.MainActivity”


**2.程序功能** 
 (1)社区精选 
 (2)新闻资讯 
 (3)学习教程 
 (4)社区博客 


 

# **参与贡献** #
android-app项目设置2-3名管理者，目前的管理者是
- cuijie(ghlimbrother)
- com360
- Iceskysl

每个人都可以fork一份代码，在自己的分支上修改，完成相关的功能后可以给 `eoecn/android-app` 发起一个pull request,管理者收到pull request后会评估合并提交的功能和代码

ps. 
详细的协作步骤请参考Iceskysl写的[基于Github参与eoe的开源项目指南](http://u.720life.cn/g/99671cb86df3fb727b007d53dcbd9e31e25688e963c2bb4fa8a4a8fd415381d26d22b75770f46f953ba3fb5676dc8b85)文章



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed027b596ff296df84a89bc57a35d540987e7a7519b55652a873c4d326026c4b7b6c10f741d024bfdbaa9c9ac572bb2a0)