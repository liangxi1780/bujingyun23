# ssmbootstrap_table demo

## 技术栈/technology stack
* spring+springmvc+mybatis
* poi3
* 自定义标签开发
* bootstrap3/bootstrap-fileinput/jquery.fileupload
* bootstrap-table1.9
* druid
* fastjson
* weui
* log4jdbc/log4jdbc-remix/log4jdbc-log4j2(show sql)
* hibernate-validator
* [spring-jsonp-support](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467001aebc4efcd2ddd94fa7db50acf23f5c10533409f0d8cb18405a3f83453fb0)
* SUI mobile
* lombok
* ehcache
* metrics
* springfox
* spring-websocket
* zxing
* jwebunit
* mockito
* itextpdf

> ## github:[https://github.com/netbuffer/ssmbootstrap_table](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304624da1d7a10df02d5eb637b23b6d9d1bff2972cc35cd31c7437addcd7130dd02f)
> ## git@osc:[https://git.oschina.net/gradle/ssmbootstrap_table](http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36bf104bd342df6d4f3c957f19ad200c7d4df25c7bd7f9e1dd17cfcee32ddf0bbd17c6216bb844423321477b42580eea438)

## How to run
The project constructed by `maven`, please execute under the `src/main/java` `SQL script` to your `MySQL` database operation, and then modify the database configuration information `jdbc.properties` under the path `src/main/resource` configuration file in the project directory, enter, execute `mvn tomcat7:run` to run

## 运行
项目采用`maven`构建，运行前请先执行`src/main/java`下的`sql`脚本到你的`mysql`数据库中，然后修改`src/main/resource`下的`jdbc.properties`配置文件中的数据库配置信息，进入项目目录，执行`mvn tomcat7:run`来运行

git->clone;eclipse->File->Import->Existing Maven projects，导入到eclipse后，等maven依赖下载完，右键项目，run as->maven build->tomcat7:run

#![demo](src/main/webapp/image/demo.gif)

#![数据列表页面](src/main/webapp/image/sys2.png)

metrics | @Timed
---|---
![metrics-servlet](src/main/webapp/image/metrics.png) | ![metrics-servlet](src/main/webapp/image/@Timed.png)


#![springfox](src/main/webapp/image/swagger.png)


> `sssbootstrap_table(spring+springmvc+spring data jpa)` github:[https://github.com/netbuffer/sssbootstrap_table](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046babe0a3a80054ea5519d3383c63fbb864e7bcffd8b840bfd358968debbb3ae33)`/`git@osc:[https://git.oschina.net/netbuffer/sssbootstrap_table]https://git.oschina.net/netbuffer/sssbootstrap_table    

> `sshbootstrap_table(spring+struts2+hibernate)` github:[https://github.com/netbuffer/sshbootstrap-table](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467be0d19a2a85a3d25a2933ee07ee3debf7c962ed8f6a90775b940bbf30f52cb0)`/`git@osc:[https://git.oschina.net/netbuffer/sshbootstrap-table]https://git.oschina.net/netbuffer/sshbootstrap-table    

> `spring-boot-bootstrap_table(springboot)` github:[https://github.com/netbuffer/spring-boot-bootstrap_table](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465a0ef54179032185e9c8b5709bb7791b971ec8a36297c5d5f32ce291c74f267a28c8905bb81a7ba81192dd54a4076282)`/`git@osc:[https://git.oschina.net/netbuffer/spring-boot-bootstrap_table]https://git.oschina.net/netbuffer/spring-boot-bootstrap_table   

> `jfinal-bootstrap-table(jfinal)`github:[https://github.com/netbuffer/jfinal-bootstrap-table](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304645315e1dd43479895e2972c2bee5f45664d0a49b268878008a286f1febac584f9212c29c9a7d9813b5a18b315f0e2600)`/`git@osc:[http://git.oschina.net/gradle/jfinal-bootstrap-table]http://git.oschina.net/gradle/jfinal-bootstrap-table  

> `medoo_bootstrap_table(php5)`github:[https://github.com/netbuffer/medoo_bootstrap_table](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fbc6383660afc9a56ba185ae444c6ed74e3a3e736190dfbbb8d52547241f8915b3f7cdfd16665293b5c0d3f107acc1e7)`/`git@osc:[http://git.oschina.net/gradle/medoo_bootstrap_table]http://git.oschina.net/gradle/medoo_bootstrap_table

---
> 
>   * develop开发分支
>	* JdbcTemplate(test spring `jdbctemplate`/test `shiro`)
>	* springtask(test spring `task`/`quartz`)
>	* velocity(test `velocity` template)
>	* swagger (test `swagger` api doc)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e64ef55e4efb2bf8611cc61714d9a0b36fa445739657208ae6401837bd0315a6805ed8f23479e96399b69db44331a0d2459adceccde00e85948bce56bbb847d9e)