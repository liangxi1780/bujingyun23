# 介绍
`watchdog-framework`基于SpringBoot+Shiro+Mybatis+Mybatis-Plus+HikariCP+Redis+Vue+iView等开发的轻量级管理系统快速开发脚手架，拥有角色、用户、资源管理、权限数据同步更新等功能，并此项目会进行持续更新升级，欢迎使用，若对您有帮助请点击上方的star :beers: 。
# 在线演示

[https://wdog-web.licoy.cn](http://u.720life.cn/g/9de3b32407661916dacb66cc2b00e971092eb1deac7fcba1c325459566e78fd3)

- 用户名：test
- 密码：test123456

# 部分界面展示
## 登录
![登录](dist/login.png)
## 用户管理
![用户管理](dist/user.png)
## 用户管理
![用户管理](dist/user.png)
## 用户添加
![用户添加](dist/add-user.png) 
## 角色管理
![角色管理](dist/role.png) 
## 角色添加
![角色添加](dist/add-role.png) 
## 资源管理
![用户添加](dist/resource.png) 
## 资源添加
![资源管理](dist/add-resource.png)    
## 更多请查看上方演示
# 技术选型
## 后端技术
技术 | 类型 | 版本 | 官网
----|------|----|----
Spring Boot | 容器 | 1.5.12.RELEASE | [http://start.spring.io/](http://u.720life.cn/g/3ef5f783c3cb0203538d979061cf7ec4c25d574a38da83f9f7bf622184b33846)
Mybatis-Starter | ORM框架 | 1.3.1 |  [http://www.mybatis.org](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a21cb345a9d06d59f28a6ab87b313549327)
Mybatis-Plus | ORM框架 | 1.3.1 |  [http://mp.baomidou.com/](http://u.720life.cn/g/cc2472c166ad93a8385c9f9684a56a6b40ba6d7dfa2fdb6f28fa2e9922b0547f)
Maven | 项目构建管理 | 4.0.0 |  [http://maven.apache.org](http://u.720life.cn/g/bc840264f6cc23df0a8935b6f2922fec747e8988e9d6774b642901b9662b323f)
Apache Shiro | 安全框架 | 1.3.2 |  [http://shiro.apache.org](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a21a07057a36d6ca5ea426a94333449b8ee4a9090aa94e48705a0a12124d68034da)
Lombok | 工具 | 1.16.20 |  [https://www.projectlombok.org/](http://u.720life.cn/g/89ca35ff92b73e2217d93dd6fd99f47f7cf8051a079683dcf0e19a72eaedd769)
HikariCP | 数据库连接池 | 2.7.8 |  [http://brettwooldridge.github.io/HikariCP/](http://u.720life.cn/g/ddfe35a69d72a8aff9a956675ee22da19f831c303ae494da5ef3946a27edb266b28d92c3411ff69bf76515073e2f2f1b)
Shiro-Redis | shiro缓存工具 | 2.8.24 | [https://github.com/alexxiyang/shiro-redis](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463849f92d4054e4dd6135067215a8a3ae488c247f697c5783b832e529c948b040)
Springfox-Swagger2 | api文档工具 | 2.7.0 | [https://github.com/springfox/springfox](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463d0d19aa0e59203735aab4a297ddb2bd3139c45e6885041a2ba910000a52ac55)
jedis | redis管理 | 2.9.0 | [https://github.com/xetorthio/jedis](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046542adf33a02b50d9ea34e04f3739d517527400c8830e803b51c2dc910a76a188)
jwt | 身份认证 | 3.2.0 | [https://jwt.io/](http://u.720life.cn/g/29b44050880331fd3d2682a984e1a32d)
## 前端技术
技术 | 类型 | 版本 | 官网
----|------|----|----
Vue | 前端渐进式框架 | 2.5.13 | [https://cn.vuejs.org/](http://u.720life.cn/g/1eea7f654038e3466b5f7afd82540e029cf1cf4f4ebcade1fd3faec47dce2808)
Vue-Router | 前端路由 | 3.0.1 | [https://router.vuejs.org/](http://u.720life.cn/g/7bedfe02707a57b283aa65bf169b40685a2bcc51af184101de4b71f45db846fa)
Vuex | 前端状态管理 | 3.0.1 | [https://vuex.vuejs.org/](http://u.720life.cn/g/acea3f53396a46112876052cae0a3648a88a7ed218d2be0ffa10fc982c11ad04)
Axios | HTTP库 | 0.18.0 | [https://github.com/axios/axios](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304638015ac6a54b1cadf0934b8a0d5637d0)
iView | UI框架 | 2.8.0 | [https://www.iviewui.com/](http://u.720life.cn/g/042b48c1b518af8039860c9df004b13c906475620f394df891651fa508140e86)
dayjs | JS时间操作库 | 1.5.14 | [https://github.com/xx45/dayjs](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464af892698274715b7d4f8ed06464c20c)
String-Format | 字符串格式化 | 1.0.0 | [https://github.com/davidchambers/string-format](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466554f074424e23fe86ca17b6eabec2ce7aec36d72b2e91e3d1ebe189214168e0)
Vue-table-with-tree-grid | iview-树表格 | 0.2.4 | [https://github.com/MisterTaki/vue-table-with-tree-grid](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046710e96c3af190a53bd217b4f4b8a0c339a13fca61cdc7ef798d88044d4516fd02d8fcb5b3909ac18d6366498f39b831e)
js-md5 | js-md5库 | 0.7.3 | [https://github.com/emn178/js-md5](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462cb8c97a6fa8900c505d4fa8405eab2d)

# 使用方法
## 软件需求
    JDK1.8+
    MySQL5.6+
    Maven4.0+
## 服务端
- 使用前提：安装lombok插件
   
   - IDEA安装方法：[https://blog.csdn.net/zhglance/article/details/54931430](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded6628d3a08d62caeec5be7c34fb004ca2d4ea7f67631d716f1f9532414661441d3d65ec833391a9bf13b0447cddfc15c9)
   - eclipse安装方法：[https://blog.csdn.net/dorothy1224/article/details/79280591/](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79deddc1f73c2b8582d9b9d920a2c4a587f15ffbe666c8510ef12702675c9cc29bac3c6f52117cdc9647c4d5503f68d77a0d7)
- 克隆到本地
```git
git clone git@github.com:watchdog-framework/watchdog-framework.git
```
- 导入SQL

    将项目根目录下的`wdog.sql`导入至数据库信息
    > admin默认密码为：123456
- 修改数据库信息
```yml
# application.yml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/wdog?useUnicode=yes&characterEncoding=UTF8
    password: root
    username: root
    driver-class-name: com.mysql.jdbc.Driver
```
- 启动
    
    运行`WatchDogApplication.java`，默认端口为1000
    
 ## 客户端

- [点击此处进入“watchdog-framework-web”项目部署说明](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460856dbfaf4559107b8716c2b2ed71bc48613ea2953b8ea8aae58df2a9c3d122256305b6d622c0dc4c7a43f89e36d02a7)

# 常见问题
- [点此查看解决办法](QUESTION.md)

# 讨论

 - QQ群：30261540  &nbsp; [点我加入QQ群讨论](http://u.720life.cn/g/e4cdc8a5afa7a074f5195772284c0c5f8e5b843143288222f8a8ec57b75dca80a6aab167a4aa9c05cf0838cee46c56befb8d18b9c4f775d933885348b02fb41f3e776474068559702c54c804cab83d761507bb974521832639b978e95a295be50d3497b42c6bbea1a257ffa45036c7c9)

- 作者博客：[https://www.licoy.cn](http://u.720life.cn/g/708a38f55b2d3b31fba93992acb3e3520cca5ced95b79ca3abad362d5c444df6)

# 项目地址

- Github：[https://github.com/watchdog-framework/watchdog-framework](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460856dbfaf4559107b8716c2b2ed71bc48613ea2953b8ea8aae58df2a9c3d12229a52f25b99661215e8705cdf352bf940)

- 码云：[https://gitee.com/licoy/watchdog-framework](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e84bf9feaa4d42d3d40398b46e88cc463f00e6e26c4b6f0f5f0a9af7e93aadf5c)

# TODO

- [ ] 支持容器化
- [ ] 字典
- [x] 日志记录
- [ ] More...

# 业务扩展

个人接单，有需求的小伙伴可以直接联系我，业务类型请参考：[https://www.licoy.cn/business.html](http://u.720life.cn/g/708a38f55b2d3b31fba93992acb3e352aab8db70d9750505127f56f4ba2ce1c5f6464b97933e3e0a0833d24e6233b413)

# 开源协议
MIT
    



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea5a16e82227689789dbcdbc5f535b6bf39ff1e0678132e43329f6b90e83375c7c1195481afc1a22a04be2985914cb5544083b9269460e346d94078633f5333d6)