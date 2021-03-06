lemur-generation
----------------------
思考业务,代码它写
----------------------
	
	Gen是我构思了挺久的一个代码生成项目,之前零零散散也写了不少代码生成,
	但是很多都不太理想不能够满足通用性和特殊定制性的需求,
	每次生成出来还要改一部分的代码,很难做到0修改,而这个就是为了做到让大家0修改上线的一个小系统,
	帮减少大家的开发时间,专注于业务开发.而不是写这些单纯的CURD.功能强大的代码生成器,
	点一下就可以完成我们想要的,定制容易,二次开发简单,可远程可以本地
	一个通用版本的代码生成器,不单单局限于自己用,可以分享,可以浏览别人的代码
	好的代码是可以共享,好的代码也是促进开发的

**QQ群**

	官网： http://www.afterturn.cn/
	邮箱： qrb.jueyue@gmail.com
	QQ群:  364192721
	

**使用指南**

**[http://www.afterturn.cn/doc/lemur-gen.html](http://u.720life.cn/g/2969fa06f3cbbfc5f06770e1e3d7c7a58c908ea7093911dc137a64f0bd34788c3b676d04e46cbb8197a6954426dfe5f0)**

**线上环境,支持直接使用,不需本地安装,注册即可使用**

**[http://gen.afterturn.cn](http://u.720life.cn/g/ca6e96d66bc647a935f2ef17805dc3cadb59b83ba3bb7383c247f4d5e9e838b5)**


功能
---------
|功能|子功能|进度|开始时间|版本支持|
|----|----|----|----|----|
|数据库管理| |80%|2017-9-01|1.0|
| | CURD|100%|2017-9-01|1.0|
| | 密码加密| | | |
|表管理| |60%| | |
| |CURD| 100%| | |
| |数据库生成表| 100%| | |
| |SQL生成表| 30%| | |
| |JSON生成表| | | |
| |XML生成表| | | |
|模板管理| |80%|2017-9-01|1.0|
| | CURD|100%|2017-9-01|1.0|
| |语法高亮|100%|2017-9-01|1.0|
| |分享| | | |
|模板组管理| |100%|2017-9-01|1.0|
| | CURD|100%|2017-9-01|1.0|
|参数管理| |100%|2017-9-01|1.0|
| | CURD|100%|2017-9-01|1.0|
|代码生成| |30%|2017-9-01|1.0|
| | Mysql|100%|2017-9-01|1.0|
| | Oracle| | | |
| | SqlServer| | | |
| | PostgreSQL| | | |




启动方法
-----------
    1. 下载代码
    2. 导入gen.sql的SQL
    3.运行 GenApplication
    4.访问 localhost
    5.登录 admin/111111

***使用方法***

    1.在数据库管理,新建数据库连接
    2.模板分组建立自己的模板分组
    3.参数管理建立自己的参数
    4.建立自己的模板
    5.代码生成,选择想要生成的表

版本
---------------------------------------------------------------------------------
 - 1.1.0
    - 表管理 
    - 数据库导入
    - SQL导入
    - 代码生成
 - 1.0.1
    - 基础版本
    - 数据库管理
    - 数据库生成 

界面演示
----------------------------------------------------------------------------------
**数据库生成**
![代码生成界面](https://git.oschina.net/uploads/images/2017/0913/214120_a097692e_69288.png "gencode.png")
**DB导入**
![输入图片说明](https://static.oschina.net/uploads/img/201710/27180007_3cHi.png "在这里输入图片标题")
![输入图片说明](https://static.oschina.net/uploads/img/201710/27173859_57Vh.png "在这里输入图片标题")

**配置编辑**

![编辑界面](https://static.oschina.net/uploads/img/201710/27180151_XbfW.png "编辑界面")

**字段编辑**

![字段编辑](https://static.oschina.net/uploads/img/201710/27180302_Y23y.png "字段编辑")
**SQL导入**


![输入图片说明](https://static.oschina.net/uploads/img/201710/27174109_UeHH.png "在这里输入图片标题")

** 配置表生成代码 **

![输入图片说明](https://static.oschina.net/uploads/img/201710/27174217_sRvy.png "在这里输入图片标题")
![组](https://git.oschina.net/uploads/images/2017/0913/215434_b40e7468_69288.png "group.png")
![db](https://git.oschina.net/uploads/images/2017/0913/215453_fb373cfc_69288.png "db.png")
![tt](https://git.oschina.net/uploads/images/2017/0913/215501_81a29e95_69288.png "params.png")
![ttt](https://git.oschina.net/uploads/images/2017/0913/215537_c0e2a3b6_69288.png "template.png")


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e15c30b288945781745aff8c163ad671f8635408be95f8ffaab44e06bfca7e921f51826e86b919182b9ab3ef1e73e3dffec574d622668f7b804becceda54d9a91)