1. 本项目欢迎上传图案二维数组到 **[issues](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea63c67f747cd83280f829f789a96733b01ee381b771e0733a9ee2afea8cdc78fc6959c86a30ecceb5a5b6f52f0c82bcb)** 以供大家使用
1. 本项目欢迎上传图案二维数组到 **[issues](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea63c67f747cd83280f829f789a96733b01ee381b771e0733a9ee2afea8cdc78fc6959c86a30ecceb5a5b6f52f0c82bcb)** 以供大家使用
1. 本项目欢迎上传图案二维数组到 **[issues](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea63c67f747cd83280f829f789a96733b01ee381b771e0733a9ee2afea8cdc78fc6959c86a30ecceb5a5b6f52f0c82bcb)** 以供大家使用
1. 格式: 标题图片+二维数组

### 前言

    码云不仅仅是代码管理平台，码云也是国内最快的git平台，速度最快，服务最好，没有之一。
    在枯燥的代码管理平台，如何玩出花来，这个就是本项目的乐趣，好玩又好看！
    本项目能给你的码云账号添加一缕颜色，装x，又多彩！
    感谢墨大佬的支持!!!!

###### 二维数组制作地址: [http://47.99.218.99:8080/led/](http://u.720life.cn/g/e4ac1f60e2da7031e6a653e0be4002eaa9793eafe5551cd6422ec9e5b89241c4)

### 项目介绍


该项目使用java语言开发springboot框架开发，注释全，代码少，3个类即可运行！


### 项目组织架构

```
├─cn
│  └─fc
│     └─fb
│     │  BootApplication.java springboot 启动无用
│     │  
│     └─test
│          GitUtil.java git提交方法
│          Init.java  运行方法
│          WindowsSetSystemTime.java 设置系统时间方法
│                      
└─resources
```

### 使用方法

- 1.修改 **GitUtil.java** 方法里面的参数

>
    //定义本地git下来的项目地址
    public static final String LOCALPATH = "D:/Users/Administrator/git/led/";
    //.git文件路径 读取.git文件夹
    public static final String LOCALGITFILE = LOCALPATH + ".git";
    //远程仓库地址
    public static final String REMOTEREPOURI = "https://gitee.com/fc-code/led.git";
    //gitee邮箱
    public static final String USER = "1111111111@qq.com";
    //gitee密码
    public static final String PASSWORD = "111111111";


> LOCALPATH、LOCALGITFILE 、REMOTEREPOURI 、USER 、PASSWORD 


- 2.修改 **Init.java** 方法里面的参数

###### 参数一

 
    //码云LED开始时间
    DateTime start_date= DateUtil.parseDate("2018-12-03");
    String start_time= "21:00:00";
###### 参数二

 
    //led 为画板制作的二维数组
    int [] [] Led= {};




- 3.运行 **Init.java** 方法里面的main方法


### 运行环境

- JDK8.0


### 项目截图

 
- 效果码云账号地址：[https://gitee.com/fc-code/](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4316ec3eb0d54677846e8b82948bb19c)
- 项目运行效果截图


![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/015121_a3c2adc5_123301.gif "无标题.gif")



- led画板制作工具截图  画板制作地址: http://47.99.218.99:8080/led/

![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/015813_526e3179_123301.gif "无标题.gif")


### 开发者联系
- QQ：87766867 
- QQ群：881799237 
     进群备注跑马灯













### 图文并茂版本
1. 下载跑马灯项目导入开发工具【不做介绍，不会百度】
1. 新建一个新的仓库
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/151959_3ed915d0_123301.png "屏幕截图.png")
1. 在线创建仓库
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/152213_0b439a06_123301.png "屏幕截图.png")
1. git下载创建项目放入d盘【不是单纯的下载，是下载后的项目跟码云仓库项目绑定】
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/152744_50471cc4_123301.png "屏幕截图.png")
1. 修改 **GitUtil.java** 方法里面的参数
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/153224_cdba14be_123301.png "屏幕截图.png")
1. 查看码云贡献榜，自己要刷的起点时间
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/153314_38e1a39d_123301.png "屏幕截图.png")
1. 修改 **Init.java** 方法里面的参数
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/153353_da65d7e0_123301.png "屏幕截图.png")
1. 制作跑马灯图案【去在线制作网站制作图案】 [http://47.99.218.99:8080/led/](http://u.720life.cn/g/e4ac1f60e2da7031e6a653e0be4002eaa9793eafe5551cd6422ec9e5b89241c4)
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/153705_b111947b_123301.png "屏幕截图.png")
1. 设置ssl为false【自己码云仓库下载的项目地址】
> git config http.sslVerify "false" 


![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/153844_8d2d6563_123301.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/153912_7b24656a_123301.png "屏幕截图.png")

10. 运行Init.java
![输入图片说明](https://images.gitee.com/uploads/images/2019/1202/154010_3fa95fa2_123301.png "屏幕截图.png")


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1b4a7174e64fee0d320e446aa938d0f193797b6bfa528389fe4690a865eaa2bc8146e14c8aabe25bf53de45057c050c1bcdc1519f540b5e403256f014dcca450)