# uniapp-chatRoom

### uniapp新版本
https://github.com/dcloudio/hello-uniapp

表情符号：
https://copy.emojiall.com/zh-hans/#go_smileys_emotion

IOS表情：
https://emojipedia.org/apple/ios-13.3/


基于PHP开发的仿pc端网页微信的即时通讯开源系统
https://www.chtml.cn/product/show/10967

https://github.com/duckchat/gaga


```
重要！如果当作网站启动的话，必须部署在站点根目录

第一步：安装 Docker（如有可跳过）

Ubuntu

代码实例
sudo apt update
sudo apt install docker.io
Centos

代码实例
sudo yum update
sudo yum install docker.x86_64
sudo systemctl start  docker.service
第二步：启动服务器

1 下载源码

下载源码，并在终端（命令行程序）cd 到 duckchat.sh 所在目录。
git clone https://github.com/duckchat/gaga.git

2. 启动程序

启动服务器
sudo sh duckchat.sh

停止服务器
sudo sh duckchat.sh stop

启动服务器时支持以下参数 sudo sh duckchat.sh -h

代码实例
-http=[port]
    指定http服务端口号，默认为 80-zaly=[port]
    指定zaly服务器的监听地址与端口，默认为 “:2021”-ws=[port]
    指定websocket服务器的监听地址与端口，默认为：”:2031”
3. 访问服务器

当 sudo sh duckchat.sh 执行成功后，便可以通过浏览器、客户端等方式链接到你的私有 IM 站点。

此方案启动的 Mysql 信息如下：

内容	值
地址	127.0.0.1
端口	3306
数据库	duckchat
用户名	root
密码	duckchat@akaxin

```

#### 介绍
基于 '回梦無痕' 作者的 《聊天模板》 添加的表情轮播组件

###### 继上个版本之后，集成到了这个聊天模板上,虽然效率还存在卡顿现象，但是经过简单测试,把代码中的console.log() 和 uni.showToast()方法全部注释掉以后,执行效率有所提高

#### 软件架构
### 效果图1
![](doc/img/1.jpg)

### 效果图2
![](doc/img/2.jpg)

@tap 在子页面无效,经过确认是开发工具的bug,
HBuilderX 2.4.1+ 已修复
2019-11-18 12:18

https://ask.dcloud.net.cn/question/82199


uni-app只支持vue单文件组件（.vue 组件）。其他的诸如：动态组件，自定义 render，和  字符串模版等，在非H5端不支持。

详细的非H5端不支持列表：

Slot（scoped 暂时还没做支持）
动态组件
异步组件
inline-template
X-Templates
keep-alive
transition （可使用 animation 或 CSS 动画替代）
老的非自定义组件编译模式不支持在组件引用时，在组件上定义 click 等原生事件、v-show（可用 v-if 代替）和 class style 等样式属性(例：    样式是不会生效的)。建议更新为自定义组件模式
老的非自定义组件编译模式组件里使用 slot 嵌套的其他组件时不支持 v-for。建议更新为自定义组件模式

优化技巧：

app-vue和小程序的数据更新，分页面级和组件级
对于复杂页面，更新某个区域的数据时，需要把这个区域做成组件，这样更新数据时就只更新这个组件，否则会整个页面的数据更新，造成点击延迟卡顿。 这就是自定义组件编译模式的特点。

避免使用大图
页面中若大量使用大图资源，会造成页面切换的卡顿，导致系统内存升高，甚至白屏崩溃。
尤其是不要把多张大图缩小后显示在一个屏幕内，比如上传图片前选了数张几M体积的照片，然后缩小在一个屏幕中展示多张几M的大图，非常容易白屏崩溃。
多使用css动画，而不是通过js的定时器操作界面做动画
如果是canvas里做跟手操作，建议使用web-view组件。web-view里的页面没有逻辑层和视图层分离的概念，自然也不会有通信折损。
#### 安装教程

1.  xxxx
2.  xxxx
3.  xxxx

#### 使用说明

1.  xxxx
2.  xxxx
3.  xxxx


### 仿微信在对话框文字中插入Emoji表情包

https://segmentfault.com/a/1190000015989051


### 自定义表情键盘及输入框的实现

https://www.jianshu.com/p/378639e2dc93


### 仿qq表情输入框

https://www.cnblogs.com/jzdwajue/p/6781023.html



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e220039724e9e5f984ed9e8f3c3c4d44a4219e78c449747efebd6bf0dcbcef8327d750f3b2c3a901430b23e16131f3fe96abae7c3918bf1c6f05f2cac85bfc9fc)