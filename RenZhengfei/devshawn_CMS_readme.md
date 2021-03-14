## 欢迎使用 “师说CMS”

> 使用Java语言开发的CMS（使用Apache2协议，可免费用于商业用途） 
QQ群：7343505    

## 部署环境前提
* eclipse
* jdk7
* git
* maven
* tomcat
* mysql

## 部署开发环境
1. 下载 [Eclipse IDE for Java EE Developers](http://u.720life.cn/g/99033988eb308493fb3efbee06dc9584c4a47b381cbaa7c42ed042d31c99f538)
2. 打开eclpse,导入师说CMS
3. File -> Import -> Git -> Projects from Git -> Clone URI
4. 然后在URI输入：https://git.oschina.net/shishuo/CMS.git
5. 等待eclipse自动下载jar包
6. 创建/sql/install.sql数据库
7. 部署中可能还会碰到很多问题，请加入QQ群：7343505

## 部署到线上（生产）
1. 复制 /src/main/resources/shishuocms.properties 到 /
2. 修改 shishuocms.properties 里的数据库链接、用户名和密码为生产环境的值
3. mvn package
4. 生成/dist文件夹，此文件夹为生产环境的编译目录

## 师说CMS的功能

### 首页头条
* 滚动大图上传
* 可设置链接、标题

### 目录
* 无层级限制
* 目录拥有自己的内容
* 可设置此目录的所有文章的封面
* 可设置是否需要审核

### 文章
* 文章管理，整合百度UEditor，
* 自动缩小和裁剪文章封面图片
* 可定义文章发布时间
* 可设置文章摘要

### 管理员
* 设置超级管理员
* 增加管理员
* 分配管理员拥有的目录权限
* 修改密码

### 其他
* 使用标签，方便前端模板开发
* 使用注解，方便二次开发


## 捐赠
如果您喜欢“师说CMS”，认为“师说CMS”确实给您带来方便和帮助，那么欢迎您捐赠。这笔钱会用在“师说CMS”的服务器费用上。非常感谢，您的捐赠，是我们前进的动力。我们将定期公开捐赠和支出。 
     

## 演示地址
[http://shishuocms.aliapp.com/](http://u.720life.cn/g/90c55ae1df6ec37f94832148ad45066fd152b2a2b5020f0c81807cceed34c741)

## 技术关键词
* jQuery
* Bootstrap
* Java
* Maven
* Spring
* Spring MVC
* MyBatis
* MySQL
* FreeMarker
* Lucene

## 需求

 - 文章列表模块
 - 图片展示模块
 - 文件下载模块
 - 电子商务模块
 - 用户注册登录模块
 - 后台管理模块

## 开发

[长沙市师说网络科技有限公司][1]

## 版权

    Copyright 2013 Changsha Shishuo Network Technology Co., Ltd.
    All rights reserved.
    长沙市师说网络科技有限公司
    版权所有
    http://www.shishuo.com
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
    http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


  [1]: http://www.shishuo.com




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec8b659ef121f3a62c168b24e870030446dceb77f62fbe7895dc13dbdcd1fd160ae8f6c6fce5a2275589234a4270df29a)