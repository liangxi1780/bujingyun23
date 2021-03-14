# Lee-Blog
大三上学期的javaweb实践项目
## 上手指南
以下指南将帮助你在本地机器上安装和运行该项目，进行开发和测试。
### 安装要求
1. java 1.8即以上
2. mysql 5.5即以上
3. tomcat 8.0即以上
4. idea即以上
### 安装步骤
1. 将该项目下载至本地任意位置
2. 打开mysql管理工具，创建数据库，具体代码如下
    ```
    create database blog;
   use blog;
    ```
   然后运行根目录下的`blog.sql`文件，接着在user表中加入一条数据
3. 修改`src/dao/DBConnect.java`第14行，15行，改为自己数据库的用户名、密码
4. 运行`src/test/DBConnectTest.java`，如果没有报错就是连上数据库了
5. 然后就可以在idea上运行项目了
## 使用到的组件
1. 前台UI CleanBlog
2. 后台UI 模板之家上下载的
3. markdown编辑器  [editor.md](http://u.720life.cn/g/62ba2c0ec0b5419421d1cb88bcfe78aeb0931761a711b76e738928f0b0cbc685)
## 效果预览
详见`img/preview.mp4`
## 版权说明
该项目签署了Apache 授权许可，详情请参阅LICENSE.md


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e16b725d846cea06fd22fd9ffe3c6480f6d6ba9eabef8bb4bf1d1c65a2415a9054b668f85492a1a6fef6f0e6516d72335)