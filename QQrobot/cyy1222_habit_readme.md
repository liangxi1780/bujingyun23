# habit

#### 介绍
长期做外包,一直想找个时间整理下一款简单实用的后台管理系统,奈何一直没找到合适的,就花了点时间自己东看看,西凑凑整了一套. 
基于JFinal的后台管理系统，采用了简洁强大的JFinal作为web框架,数据库用MYSQL,前端使用Vue+Element,支持移动端 
做了一些简单的改造,让开发人员专注于业务开发. 
 **默认载入配置文件根目录中的所有配置文件 ** 
 **控制器不需要一个一个去路由里面加,配置下控制器包名,自动映射 ** 
 **数据模型,Sql模板,添加对应的配置包名,扫描映射 ** 
 **权限菜单只要一些简单的注解,自动生成数据 ** 
 **代码生成Model,Service,Controller,sql模板,js,vue模板,解放双手,少做一些通用性的工作(待完善) ** 
- up-habit 项目基础
- up-app 业务功能模块
- up-ui vue+element管理前端
#### 体验地址
- [http://habit.up-pro.cn](http://u.720life.cn/g/7dd3bc6d2baa14ab7251c0c60698ab6072b6012c90b1cff96da926dd6f9bc82f)
- 账号密码:admin/111111
#### V1.0.0版本功能
~~~~
|-系统设置
| |-机构管理:配置系统组织机构，树结构展现支持数据权限
| |-岗位管理:配置系统用户所属担任职务。
| |-角色管理:角色菜单权限分配、设置角色按机构进行数据范围权限划分
| |-用户管理:用户是系统操作者
| |-菜单管理:配置系统菜单，操作权限，按钮权限标识等。
| |-参数管理:对系统动态配置常用参数。
| |-字典管理:系统字典的使用维护
|-系统监控
| |-服务监控:监视当前系统CPU、内存、磁盘、堆栈等相关信息。
| |-数据监控:监视当前系统数据库连接池状态,使用Druid
| |-定时任务:添加,修改,删除,启停定时任务
| |-日子查看
|   |-任务日志:任务执行日志
|   |-系统日志:系统正常操作的日志
|-系统工具
| |-代码生成:利用Enjoy模板生成简单的业务逻辑代码

~~~~

#### 使用配置
基础配置

```
#应用名
app.name=UP-APP
#开发模式
app.dev=true
#是否显示Sql
app.showSql=true
#模块包名,用于自动扫描Controller加入路由
#api控制器所在包名,多个包名用逗号隔开
app.ctrl.api=com.up.app.controller.api
#admin控制器所在包名,多个包名用逗号隔开
app.ctrl.admin=com.up.app.controller.admin
#web控制器所在包名,多个包名用逗号隔开
app.ctrl.web=com.up.app.controller.web
#不要加入的控制器,可以是包名,也可以是具体的类路径名,多个用逗号隔开
app.ctrl.without=
```

日志:集成Logback,自己又做了一层改造,简化了配置内容,
Log log=Log.getLog("{name}")

```
#日志文件存放路径
log.folder=log/
#日志文件分等级存储
log.level.file=false
#系统日志根等级
log.root.level=info
#日志默认等级
log.default.level=debug
#对应日志等级,不设置默认log.default.level等级,其中{name}是Jfinal中Log.getLog("{name}")
log.{name}.level=debug
```
数据库配置:数据模型扫描映射,sql模板扫描

```
#数据源,多个用逗号隔开,默认配置main,更多配置请查看源码
db.array=main
#对应数据源配置
#连接地址
db.main.url=localhost:3306/habit
db.main.user=root
db.main.password=
#数据模型映射,多个包名逗号隔开,省去jfinal生成的_Mapping.Kit
db.main.map=com.up.app.model,com.up.habit.expand.gen.model
#JFinal Enjoy sql摸板路径配置,多个逗号隔开
db.main.sql=com.up.app.service
```
缓存配置:默认不配置使用Ehcache

```
#缓存类型,ehcache,redis
cache.type=ehcache
#ehcache配置文件路径,自定义配置ehcache.xml
cache.ehcache.configFileName=
#redis 配置
cache.name=
cache.host=    
cache.port=    
cache.timeout=    
cache.password=    
cache.database= 
```
### 项目结构
#### 感谢

1.  JFinal:[http://git.oschina.net/jfinal/jfinal](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844dd5b4c01c069ce20ef9cb3339fc644d79911ef780e2d0af250de17dae01f49f8a)
2.  ruoyi:[https://gitee.com/y_project/RuoYi-Vue](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4efbf9a2018792702bfb8d2f94b55c6d7a2c36c7bc4d3e3beccaae130c5d21a5)
2.  vue-element-admin:[https://github.com/PanJiaChen/vue-element-admin](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304603c6efa7d0c1ce77680f5b6f938bd6cef861f7dd6d31dc89ca07ef0b5d2b912f)

#### 示例图
![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122320_54ea114f_342753.png "1.png")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122343_027f2276_342753.png "2.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122355_93caff04_342753.png "3.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122403_7c230acd_342753.png "4.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122411_6f91c4e9_342753.png "5.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122418_983fc349_342753.png "6.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122425_57f65800_342753.png "7.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122432_8b7f939c_342753.png "8.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122439_cb58ac81_342753.png "9.png")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122448_e7e88156_342753.png "10.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122457_8e5e70bf_342753.png "11.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122505_8e753008_342753.png "12.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122512_ed5cc656_342753.png "13.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122524_c5523f62_342753.png "14.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122536_5de8956e_342753.png "15.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122544_956942f2_342753.png "16.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122551_526f7f32_342753.png "17.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122559_cab50b39_342753.png "18.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122606_86092c24_342753.png "19.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122614_da9b55bc_342753.png "20.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122623_7851256e_342753.png "21.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122630_232f3bec_342753.png "22.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122639_44fd9937_342753.png "23.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122645_0b940203_342753.png "24.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122659_509bdf82_342753.png "25.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122708_dff449ed_342753.png "26.png")![输入图片说明](https://images.gitee.com/uploads/images/2020/0126/122717_45b353ca_342753.png "27.png")







 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e04ff7c0ace8adefcc86cbea165254bc925eedee7caeff9c17a09e652281a93d59c3abcfc01233286c40eb63fd428c3f7)