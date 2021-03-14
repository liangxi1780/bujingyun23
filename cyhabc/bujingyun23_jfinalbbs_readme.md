### 友情提醒: 使用jfinalbbs的代码搭建自己的社区网站,不能删除页面底部的 powered by [JFinalbbs](http://u.720life.cn/g/e123d6aadc5fc3213d8137460a9eed5f3b28f6ac3bdfb52160ab0c3415af400c) ,如果嫌位置不好看,可以在页面其他显眼的地方加上提供者:[JFinalbbs](http://u.720life.cn/g/e123d6aadc5fc3213d8137460a9eed5f3b28f6ac3bdfb52160ab0c3415af400c), 谢谢配合

# 如何开始

### 服务器环境部署

- clone代码,maven编译打成war包, 或者直接[下载war包](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461372279bb3bb0c6dcc03b70ecdd76747908973afd29af6872fa093a7e4916cf6)
- 将`doc/最新版SQL.sql`脚本在mysql数据库里运行，创建jfinalbbs数据库
- [下载tomcat](http://u.720life.cn/g/27381b9b9aecbc3251722641d01ac5ed6b60a2f4f59bdeb7be0dc0ead4e20011),解压
- 将war包放到`tomcat/webapp`下,启动tomcat(`./bin/startup.sh`)
- 修改`tomcat/webapp/jfinalbbs/WEB-INF/classes/config.properties`文件的配置(就一个数据库的jdbc连接信息)
- 重启tomcat
- 打开浏览器,输入`http://localhost:8080/jfinalbbs`回车
- 后台访问路径`http://localhost:8080/jfinalbbs/admin/index`

### 开发环境部署

- 使用git将master分支的代码down下来
- 使用maven编译
- 运行`JFinalbbsConfig.java`类里的main方法
- 浏览器访问`http://localhost:8080/`

# 碰到问题怎么办?

1. 加QQ群 419343003 ,阅读群公告后可以提问题
2. 在Github上提 Issues
3. 提问题的时候请将问题重现步骤描述清楚,对于截个图什么也不说,发一句话就了事的,我会看心情回答(你懂的!)

# 贡献代码

目前jfinalbbs就一个`master`分支,就朋也一个人在开发维护,如果想分享自己拓展的功能等,可以给朋也的`master`分支推送`pull request`

# 2016年3月24日 V2.2更新内容

1. 后台增加shiro权限控制（使用了jfinal-ext）
2. 后台标签可以增加/编辑
3. 前台登录另起一个页面
4. 编辑器升级,可以直接拷贝word文档粘贴
5. controller, table 增加了自动扫描注入（使用了jfinal-ext）
6. 删除baseUrl从后台设置, 改用`me.add(new ContextPathHandler("baseUrl"));`方式

## 数据库更新

- 增加表: jfbbs_role, jfbbs_user_role, jfbbs_permission, jfbbs_role_permission, jfbbs_admin_log
- 修改了: jfbbs_admin_user增加字段: salt, in_time
- 修改了: jfbbs_topic删除字段: original_url, reposted, 增加字段: isdelete
- **具体对照最新数据库脚本 `doc/最新版SQL.sql`**

## 截图欣赏

![](http://7xj5k8.com1.z0.glb.clouddn.com/QQ20160324-0.png)

**更新体验[传送门](http://u.720life.cn/g/e123d6aadc5fc3213d8137460a9eed5f3b28f6ac3bdfb52160ab0c3415af400c)**

其他版本更新日志参见 `doc/更新日志.md`

![](http://jfinalbbs.com/static/upload/imgs/381938b1861da719.jpeg)

以上


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb25e0a6bd757664afe4c0ec687f3f94339473a6688df730fc46ff80bd471667b1341597f9427d2afb38a65e73aa07d3b)