# Lancer
同步两个DB之间的schema,配置如下:     
sourceHost=127.0.0.1:3306     
sourceUser=root     
sourcePass=123123123     
sourceSchema=mystique_db     
sourceCharset=utf8     

targetHost=127.0.0.1:3306     
targetUser=root     
targetPass=123123123     
targetSchema=mystique_test     
targetCharset=utf8     

autoExecute=YES //此处表明自动同步     

原理:
通过捞取information_schema来比较source_schema和target_schema(可在不同实例)的表结构是否一致，     
如果target_schema没有则这张表则创建，     
如果target_schema表里面没有这个字段则alter add(保证顺序),     
如果表里面有这个字段、但属性不一样则alter change,     
另外还同步索引的元数据.     
可以指定进行自动执行，也可以指定打印出对应的执行语句,语句如下所例:     
alter table mystique_test.t_test_3 change id id bigint(20) NOT NULL AUTO_INCREMENT COMMENT ''      
alter table mystique_test.t_test_3 add index (`name`)     
alter table mystique_test.t_test_3 drop index name_id     
alter table mystique_test.t_test_3 add id_2 varchar(50) NULL DEFAULT '' COMMENT '' after name     



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7a4f56cb8186f93468e5acb018ac6f46e3ed41c98e130fad43437ea922ba1677bf7ef3c634cc97982f3ecaa8b9231e0a491df477cb7b4c472bc5d1de7a0e98e7)