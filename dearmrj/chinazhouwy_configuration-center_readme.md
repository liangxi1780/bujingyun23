###  **一个简单的zookeeper配置中心**  :smiley: 

### 项目结构如下：

![项目结构](https://gitee.com/uploads/images/2018/0530/150857_a13b92d9_724638.png "项目结构")

configuration-core模块是配置中心服务端核心
configuration-admin是配置中心管理页面

 **使用时只需要install configuration-center 获取configuration-core.jar** 

其他项目引入configuration-core.jar 

在resources路径下添加config.propertis 文件 输入服务器项目等信息

![输入图片说明](https://gitee.com/uploads/images/2018/0530/151958_04b76b77_724638.png "QQ截图20180530151420.png")

其他配置也可以选择性添加

然后在applicationContext.xml中添加 加载文件类

![输入图片说明](https://gitee.com/uploads/images/2018/0530/151924_1dcb3b89_724638.png "QQ截图20180530151821.png")

 **若是第一次使用，启动后，会提示没有配置项，此时需要到管理页面添加配置。** 

打开configuration-admin 修改resources文件下 config.properties zookeeper服务器信息

![输入图片说明](https://gitee.com/uploads/images/2018/0530/152418_ae26815c_724638.png "QQ截图20180530152345.png")

运行Application 启动项目,打开页面http://localhost:9090 登录 用户名admin 密码123456（目前用户名密码固定）

![输入图片说明](https://gitee.com/uploads/images/2018/0530/152742_2c92bc9b_724638.png "QQ截图20180530152726.png")

选择左侧项目

![输入图片说明](https://gitee.com/uploads/images/2018/0530/152946_5031cbf9_724638.png "QQ截图20180530152926.png")

可以导入添加配置项.

 :smile: 界面比较简单，并且没有使用数据库

 **该项目正在开发中，目前还不支持main函数启动项目 读取配置中心** 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed2f5cf361d8fd7706080233a88f756c9fcf496970428335855a1ff47f7936d3e0ba12d88a673699ed2927e9356a327e4ee29ec9b680fa15e85b26cc25ceaed69)