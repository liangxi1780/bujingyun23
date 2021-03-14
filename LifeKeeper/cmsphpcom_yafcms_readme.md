# yafcms  
最近学习yaf框架，写一个简单的cms系统。

* 重新设计yafcms，采用layuicms后台界面，动静分离，接口url路径与gincms尽量保持一致
* 与gincms使用同一个数据库，可以同时维护数据内容。
* 与gincms的界面一致。接口路径稍有变化。
* gincms 地址 https://blog.csdn.net/huoyongliang/article/details/90544168

>[yaf](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466225fbc5bd5dba62141ebc92dc7fb505)是鸟哥用C语言编写的一个PHP框架，yaf文档地址：[http://yaf.laruence.com/manual/]http://yaf.laruence.com/manual/

yafcms是一个基于Yaf框架的小型内容管理系统。前端使用了基于LayUI的LayUICMS，后端使用了ThinkORM等许多开源类库，是学习php，入门Yaf的好例子，希望对大家有所帮助。

如果有什么改进意见可以到这里提问：[点这里提问](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5925adfa3c608d8cb690d7421b88ec6f88f0f85f2b37e7d3b2ad24240ba7def5)

同时我也会把一些常见问题整理成帮助文档，放到这里：[帮助文档](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded130e51b814513fb53f91bc60323142e53ff037499d2091a1ab459f83d25f2e4d)

# 站点部署
> 数据库文件是sql.zip  
> 数据库配置文件是conf/application.ini  
> 站点根目录是public  

# 账号密码
admin  
123456

# 配置
首先，你得安装yaf,文档里有，[http://php.net/manual/zh/yaf.installation.php](http://u.720life.cn/g/d72b6b65beb51348ff2c110f8fad4b12368f82ccb9cff97a1725f4bb2b44f6d4efb5f74d4152994ddf488f093c096032) 。
安装完之后，编辑php.ini文件，配置yaf:
```sh
extension=yaf.so
yaf.use_namespace=1 ;开启命名空间
yaf.use_spl_autoload=1 ;开启自动加载
```
# [yafcms](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5925adfa3c608d8cb690d7421b88ec6fdc8822a9db8090d750487ba46eeafe96)主要添加了:   
* [Think ORM](http://u.720life.cn/g/2ef919c988b0e4d820d8befd5d089d778c91a28eb9821c330ddb47bb9beee6c6ff31c765aeae26eca60848936bb409ddc892ce01278eb168572e0055e1f3b3f5)  
* [Lay UI](http://u.720life.cn/g/330802d232849288787f1cd346adeee341ba5458233285bf444ffecff43d7f06)  
* [Layuicms](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2409a82d5bd2a83cade8d109634cd1f5891815172f67de3974efdbca397ca8e3)  
* 一些常用函数  

先编辑conf/application.ini文件
```sh
[common]
application.modules = "Index"
application.directory = APP_PATH  "/application"
application.view.ext = "html"

;user
user.default_filter = 'trim,htmlspecialchars,strip_tags'

[product : common]

[develop : common]

;socketlog
socketlog.enable = true
socketlog.host = 'slog.thinkphp.cn'
socketlog.optimize = true
socketlog.show_included_files = true
socketlog.error_handler = true
socketlog.force_client_ids = ''
socketlog.allow_client_ids = 'slog_3079b2'

;database
;数据库驱动类型
database.config.type='pdo'
;服务器地址
database.config.host='127.0.0.1'
;数据库名
database.config.name='yaf_member'
;用户名
database.config.user='root'
;密码
database.config.pwd='123456'
;端口
database.config.port= '3306'
;启用字段缓存
database.config.fields_cache=false
;数据库编码默认采用utf8
database.config.charset='utf8'
;数据库部署方式:0 集中式(单一服务器),1 分布式(主从服务器)
database.config.deploy_type=0
;数据库读写是否分离 主从式有效
database.config.rw_separate=false
;读写分离后 主服务器数量
database.config.master_num=1
;指定从服务器序号
database.config.slave_no=''
database.config.dsn=''
database.config.params='' 
database.config.bind_param=false  
database.config.like_fields=''
;是否输出sql语句
database.config.debug=false
```
database为MySql数据库的配置,socketlog为socketlog的配置




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e37226372f254dce6d409e9e4223f4c08319b39c02dbf75a2e7c98969ed5c4f44f2ca3143909044f617244db403187c9f)