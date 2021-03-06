# friday

#### 介绍
基于Spring Boot2.X的后台权限管理系统，适合于学习Spring Boot开发、项目毕业设计以及研发团队快速搭建项目，提供纯净的权限管理功能，可作为开发项目的脚手架，作为基础项目。

#### 软件技术
1. Spring Boot 2.1.4
2. Spring Security 5.1.5
3. Mybatis 3.5.1
4. Logback 1.2.3
5. Druid 1.1.10
6. Swagger 2.9.2
7. Lombok 1.18.6
8. X-admin 2.2
9. Thymeleaf 3.0.11
10. Layui 2.5.3
11. MySQL 5.6
12. Docker(用于提供MySQL服务) 

#### 内置功能
1. 用户管理：用户查询、添加用户、修改用户、用户角色设置、删除用户；
2. 角色管理：角色查询、添加角色、修改角色、角色菜单权限配置、删除角色；
3. 菜单管理：菜单查询、添加菜单、修改菜单、删除菜单；
4. 登录、登出：基于Spring Security的认证和授权；
5. Druid数据源监控功能；
6. Swagger接口文档功能；
7. 修改密码；
8. 代码自动生成：根据数据表以及自定义模板自动生成html、controller、service、serviceImpl、dao、mapper.xml文件；

#### 安装教程

1. 克隆源代码并使用Intelij IDEA导入项目代码；
2. Intelij IDEA中安装Lombok插件，参考：https://jingyan.baidu.com/article/0a52e3f4e53ca1bf63ed725c.html
3. 将'/resources'目录下的'friday.sql'导入MySQL数据库；
4. 修改'/resources'目录下的'application.yml'文件中的数据源配置，改为你自己的MySQL环境:

```
url: jdbc:mysql://localhost:3306/sxb-base?useUnicode=true&characterEncoding=utf-8&allowMultiQueries=true&useSSL=false&serverTimezone=UTC

username: root

password: my-secret-pw
```

5. 启动项目，访问"http://localhost:8080",输入admin/admin即可登陆成功。

#### 项目学习

1. 本项目配有成套开发视频供参考 [https://ke.qq.com/course/447325?flowToken=1015532](http://u.720life.cn/g/acade89ba1aa2fc5ea46106ad5a9218f646f0ab7abf753ad6b7639fb5444f690b91a6f9b4ef24e88c7bc603a9309587baf07a6787857b2e4e24802aa62948923)


6. 参考资料软件包
复制这段内容后打开百度网盘手机App，操作更方便哦
链接：https://pan.baidu.com/s/1a76sbeQ8u4OISC9X37EjFg 提取码：31Kx


#### 如有帮助，请随手点击右上角的star，非常感谢。




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e92fa68c82e81cc1f2bb8995744932047155667c41310aebe69d95c5065613b3c4488416ef86bff5d699b1f9e1d46b47d)