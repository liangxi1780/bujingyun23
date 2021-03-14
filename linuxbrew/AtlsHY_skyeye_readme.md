# skyeye

#### 项目介绍 
win10风格的一套系统，前端采用layui作为前端框架，后端采用SpringBoot作为服务框架，采用自封装的xml对所有请求进行参数校验，以保证接口安全性。 
##### 启动方式
直接运行com.skyeye.SkyEyeApplication即可，启动完成后，访问http://localhost:8081即可。

#### 服务器部署注意事项
1.ActiveMQ链接地址、账号、密码的修改 
2.Redis集群的修改 
3.MySQL数据库链接地址、账号、密码的修改 
4.webSocket的IP地址修改 
5.图片资源路径存储的修改 

#### 本地开发环境搭建
- windows搭建nginx负载均衡（[下载](http://u.720life.cn/g/79c052993beda1b8b515943f814949523771de2562a8eb04a18037336070cd2024fab4a27b4301b6da266146de8110ab36de2c7729b676bfb92fed3288bd6503)）
- windows搭建activemq单机版（[下载](http://u.720life.cn/g/79c052993beda1b8b515943f814949523771de2562a8eb04a18037336070cd2024fab4a27b4301b6da266146de8110ab24e75c7ddb628be59cf5e3f611334e43)）
- windows搭建redis集群（[下载](http://u.720life.cn/g/79c052993beda1b8b515943f814949523771de2562a8eb04a18037336070cd2024fab4a27b4301b6da266146de8110abbf430d3c01a4f9530c7710343ec7e837)）

##### 注意事项
如果是eclipse导入发现pom文件报错。 
错误：org.apache.maven.archiver.MavenArchiver.getManifest 
解决办法：https://blog.csdn.net/doc_wei/article/details/84936514 

#### 目前功能

- 菜单管理、用户管理、角色管理、角色绑定菜单管理、用户多角色管理、系统ICON管理（目前只支持系统内部样式icon）、日志管理
- 代码生成器完成（只能适用于该框架的代码生成器，配置模板即可生成，然后下载压缩包解压复制到项目中即可）
- 微信小程序、H5手机自适应页面拖拽生成，可自定义配置小程序组件
- 用户可根据自己的爱好自定义设置界面样式
- Java应用的在线性能监控
- 行政区划（四级行政区划，数据量四万多条，界面只展示三级行政区划。获取行政区划的工具在 **com.skyeye.common.util.AreaUtil** ）
- 项目流程图规划
- 问卷调查模块（创建问卷、发布问卷、问卷统计等）
- 多桌面任务栏（[演示](http://u.720life.cn/g/0b2e9c050c16e17e2de17da38fe221e14e891e7f464d808a8bfeaa8b64b73a97377a3f1010a7574ac6b65415e4dff2a0)）
- 聊天功能([演示](http://u.720life.cn/g/0b2e9c050c16e17e2de17da38fe221e14e891e7f464d808a8bfeaa8b64b73a9759711cb96abfcd62c5d9347a3aeaee5a)
- 我的日程([演示](http://u.720life.cn/g/0b2e9c050c16e17e2de17da38fe221e14e891e7f464d808a8bfeaa8b64b73a979b922f0efd62426c7344ba98c9314173)
- 自定义快捷方式，自由组合菜单分组
- 多系统集成：可以将多个系统进行应用集成，无需多次登陆，无需记录多个网址
- 应用商店：集成外部系统，进行同步更新
- 开发文档：方便开发者进行开发的学习文档

#### 目前系统

- 文件系统：支持大文件分块上传，支持office、txt、tpl、html、js、css、png、jpg、gif、mp4、zip、rar等多种文件格式的在线预览，在线编辑，在线解压，压缩包内容在线查看，在线压缩等功能。
- 笔记系统：类似有道云的笔记记录系统，可同步更新、分享。
- 门户系统：包含门户展示系统和门户后台维护系统（可进行定制开发）
- 消息系统：负责整个系统的消息、通知等内容

#### 技术扩展
- webSocket技术扩展
    ![输入图片说明](https://images.gitee.com/uploads/images/2019/0205/224843_d8055e22_1541735.png "1.png")

#### 版本介绍
功能|商用版|免费版
---|---|---
问卷调查样式设计|有|否
聊天功能（下图展示部分功能）|有|否
我的日程|有|否
我的笔记|有|否
自定义快捷方式|有|否
多系统集成|有|否
应用商店|有|否
开发文档|有|否

#### 系统
功能|商用版|免费版
---|---|---
门户系统(包含门户展示系统和门户后台维护系统)|有|否
消息系统|有|否
文件系统|有|否
笔记系统|有|否

#### 技术选型
##### 后端技术:
技术|名称|官网
---|---|---
SpringBoot|核心框架|http://spring.io/projects/spring-boot
MyBatis|ORM框架|http://www.mybatis.org/mybatis-3/zh/index.html
Druid|数据库连接池|https://github.com/alibaba/druid
Maven|项目构建管理|http://maven.apache.org/
redis|key-value存储系统|https://redis.io/
webSocket|浏览器与服务器全双工(full-duplex)通信|http://www.runoob.com/html/html5-websocket.html
Activiti|工作流引擎|https://www.activiti.org/
spring mvc|视图框架|http://spring.io/
quartz 2.2.2|定时任务|http://www.quartz-scheduler.org/
ActiveMQ|消息队列|http://activemq.apache.org/replicated-leveldb-store.html

##### 前端技术：
技术|名称|官网
---|---|---
jQuery|函式库|http://jquery.com/
zTree|树插件|http://www.treejs.cn/v3/
layui|模块化前端UI|https://www.layui.com/
winui|win10风格UI|https://gitee.com/doc_wei01_admin/skyeye
codemirror|codemirror代码编辑器|https://codemirror.net/
handlebars|js模板引擎|http://www.ghostchina.com/introducing-the-handlebars-js-templating-engine/
webSocket|浏览器与服务器全双工(full-duplex)通信|http://www.runoob.com/html/html5-websocket.html
G6|流程图开发|https://antv.alipay.com/zh-cn/index.html
FullCalendar|日历插件|https://blog.csdn.net/qw_xingzhe/article/details/44920943

#### 代码描述
##### 前后台接口映射
```
 
	 
 
```
##### 后台代码编写规范

###### 控制层
```
@RequestMapping("后台接口")
@ResponseBody
public void 方法名(InputObject inputObject, OutputObject outputObject) throws Exception{
	服务层接口对象.方法名(inputObject, outputObject);
}
```

###### 服务层
```
@Override
public void 方法名(InputObject inputObject, OutputObject outputObject) throws Exception {
	Map  map = inputObject.getParams();//接收参数
	Map  user = inputObject.getLogParams();//获取当前登录用户信息
	/**
	 * 业务逻辑
	 */
	outputObject.setBean(bean);//返回单个实体Bean
	outputObject.setBeans(beans);//返回集合
	outputObject.settotal(total);//返回数量
	outputObject.setreturnMessage("信息");//返回前端的错误信息
	outputObject.setreturnMessage("信息", 错误码);//返回前端的错误信息，同时抛出异常（不常用）
}
```



#### 效果图
- 1.界面效果图（支持右键操作，多任务栏桌面） 
![输入图片说明](https://s2.ax1x.com/2019/04/16/Avo0c8.png "1.png")
- 2.角色管理（权限分配，多角色用户） 
![输入图片说明](https://s2.ax1x.com/2019/04/16/AvoHE9.png "1.png")
- 3.小程序拖拽 
![小程序拖拽](https://images.gitee.com/uploads/images/2018/1107/104734_d9304e60_1541735.png "2.png")
- 4.代码生成器（自定义模板） 
![代码生成器](https://images.gitee.com/uploads/images/2018/1107/104903_f244dfde_1541735.png "3.png")
- 5.文件管理 
![输入图片说明](https://images.gitee.com/uploads/images/2019/0601/165637_3862802b_1541735.png "1.png")
- 6.Redis数据实时监控 
![输入图片说明](https://images.gitee.com/uploads/images/2018/1118/191634_497ea929_1541735.png "微信图片_20181118191516.png")
- 7.动态表单（动态表单限制条件配置，动态表单Form表单内容项配置，动态表单数据展示模板配置） 
![输入图片说明](https://images.gitee.com/uploads/images/2018/1118/193301_72d0bb49_1541735.png "微信截图_20181118193254.png")
- 8.用户基础设置（主题设置，背景图片设置，任务栏设置）
![输入图片说明](https://s2.ax1x.com/2019/04/16/Av7lee.png "微信截图_20181120154643.png")
- 9.系统日志管理
![输入图片说明](https://images.gitee.com/uploads/images/2018/1121/105120_65de9434_1541735.png "1.png")
- 10.Java应用的在线服务器性能监控
![输入图片说明](https://images.gitee.com/uploads/images/2018/1121/173442_c1c842b4_1541735.png "1.png")
- 11.公司上下级管理（公司管理、部门管理、职位管理）
![输入图片说明](https://images.gitee.com/uploads/images/2019/0122/113516_b0600e8f_1541735.png "1.png")
- 12.思维导图（项目流程图制作）
![输入图片说明](https://images.gitee.com/uploads/images/2018/1207/123501_3248346e_1541735.png "微信截图_20181207123447.png")
- 13.问卷调查（设计问卷、问卷收集、问卷发布、答卷等）
![输入图片说明](https://images.gitee.com/uploads/images/2019/0113/114947_1c7fa387_1541735.png "微信截图_20190113114922.png")
- 14.聊天功能（在线客户端列表，上线/下线通知，消息通知，群聊管理） 
![输入图片说明](https://images.gitee.com/uploads/images/2019/0202/130711_7ed57951_1541735.png "3.png")
- 15.我的日程
![输入图片说明](https://images.gitee.com/uploads/images/2019/0310/095241_72a7847b_1541735.png "微信截图_20190310094407.png")

#### 环境搭建
##### 开发工具:

- MySql: 数据库 
- Tomcat: 应用服务器 
- SVN|Git: 版本管理 
- Nginx: 反向代理服务器 
- Varnish: HTTP加速器 
- IntelliJ IDEA|Eclipse: 开发IDE 
- Navicat for MySQL: 数据库客户端 
- Redis Manager：redis视图工具 

#### 资源下载

- JDK8 https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html 
- Maven http://maven.apache.org/download.cgi 
- Redis https://redis.io/download 
- Nginx http://nginx.org/en/download.html 

#### 在线文档

- [JDK8中文文档](http://u.720life.cn/g/6e932f51d22186016c0fc3e7daee3c145d5523d10e93ad3c079802b8f8f22d56526467428bdeb88c5305a49b28acec08) 
- [Spring4.x文档](http://u.720life.cn/g/3d3c1eebe7d1a3ce4b19ffb3e57807e89fa619207522cc50e254f65d86af1be0b306863a011de5ef8e4a8b3c5c17ee5d) 
- [Mybatis3官网](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a215e4d93221eb26b660bea25686b89be63142caf406b6e1c14d3ab51db921e10ca) 
- [Nginx中文文档](http://u.720life.cn/g/0b74b15bb9de87b5a2fb1d39225b742f9755696133ba7493060bcd72b849d00c70ea5132d4eda0624001e88d63d0a989754ed6dd7d93878effc7028703b52239) 
- [Git官网中文文档](http://u.720life.cn/g/0699e533b96232c5e210af6ab5668134f26d4ce8eb73c737efb58c5e94ea6f74) 
#### 作者微信公众号：
![输入图片说明](https://images.gitee.com/uploads/images/2018/1207/083137_48330589_1541735.jpeg "qrcode_for_gh_e7f97ff1beda_258.jpg")

#### QQ群：
![输入图片说明](https://images.gitee.com/uploads/images/2018/1205/145236_4fce6966_1541735.jpeg "微信图片_20181205145217.jpg")




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eabf84c9247da0e89a63840606360483223823650e91030fa498b53f0a2de167f273b9f8ced0cd19e0ae9abb0b17fdc1f)