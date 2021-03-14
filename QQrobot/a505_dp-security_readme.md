# dp-LTE
基于SSM框架的轻量级开发框架，已经完成基于角色的操作权限管理，对前后端进行封装，可快速实现CRUD的开发。项目采用Maven多模块构建，方便按需求进行模块化扩展。
### 传送门
- dp-LTE：[https://gitee.com/dp_group/dp-security/](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0590d9ce48e96a32b4415700aa83be71896b2b9b63c8626e8afa47634635fd92)
- dp-PRO：[https://gitee.com/dp_group/dp-pro](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eddd49d2184fb5ca4867bfafd7110a22a0ea9bcc83b0fb974654bbeba57f006a7)
- dp-GEN：[https://gitee.com/dp_group/dp-generator](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed9ea5b109b5b12dab9eac9c92d09371fa469ee82b439485f1864733c4873dbd9)
- dp-BOOT：[https://gitee.com/dp_group/dp-boot](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8cb46e598d0dd38745f7ad957dffb332950b32c1cf2fa0d608aab83cad1043b2)
- 项目文档（包含常见问题解答）：[http://dp-dev.mydoc.io/](http://u.720life.cn/g/b2f108c7a1e3d6e2bd054cf582505685eb40109f14c1d2cc8fcedeb46150f9ab)
（dp-PRO支持动态数据源切换、分布式session、多tab页标签菜单、代码生成器【生成代码也适用于dp-LTE】、自定义日志） 
### 项目拓展
- [基于系统参数管理实现动态select控件](http://u.720life.cn/g/a88615b97db01a1ba3d626afe31cb1736ecc4bc73836e4d2d01d26fb7233d418250ef1c15953d77e10b118b883f7d0bc)
- [基于ajaxfileupload.js实现文件上传](http://u.720life.cn/g/a88615b97db01a1ba3d626afe31cb1736ecc4bc73836e4d2d01d26fb7233d418be5a320a0b6d8ade090bec6ddc8eca32)

### 项目介绍
- 一个轻量级的Java快速开发框架，能快速开发项目并交付（规划后期不定时发布更新）
- 友好的代码结构及注释，便于阅读及二次开发，命名规范和工程分层规约参考阿里巴巴JAVA开发规范
- 前后端开发封装，快速实现CRUD开发
- 支持通过velocity模板生成部分代码，可直接生成到项目路径，无须二次部署（见文档）
- 基于角色的权限管理，细分到按钮权限（dp-PRO支持数据权限）
- 基于Maven模块化开发，可快速扩展个性化业务模块
- 封装常用开发组件，目前已集成select2、switchery及富文本组件
### 技术方案
- 核心框架：Spring
- WEB框架：SpringMVC
- ORM框架：Mybatis
- 缓存框架：Ehcache
- 安全框架：Shiro
- 模板框架：thymeleaf（支持freemarker、jsp等其他自定义视图）
- 主页框架：adminLTE(Bootstrap)
- JS框架：vue.js
- 表格插件：bootstrap-table(扩展分页跳转)
- 树形表格：tree-grid(基于bootstrap扩展)
- 树形插件：ztree
- 弹窗组件：layer
- 日期组件：laydate
- 下拉选择组件：select2
- 开关组件：switchery
- 富文本组件：wangEditor
- 表单校验：validator
- 后端校验：fluent-validator
- 接口管理：swagger-ui
### 项目结构
- dp-security：父级（聚合）模块
- dp-common：公共通用模块
- dp-shiro：权限模块（操作权限）
- dp-orm：数据持久模块
- dp-quartz：定时任务模块
- dp-web：前端界面
- dp-base：基础模块，目前包含行政区域、通用字典和系统日志功能模块
### 交流反馈
- 项目文档：[http://dp-dev.mydoc.io/](http://u.720life.cn/g/b2f108c7a1e3d6e2bd054cf582505685eb40109f14c1d2cc8fcedeb46150f9ab)，二次开发手册参见3.4节
- 交流QQ群：553461392
- 如果对项目感兴趣，请Watch、Star项目，后期会不定时发布更新
### 命名规范（参考阿里巴巴Java开发手册）
-  获取单个对象的方法用 get 做前缀
-  获取多个对象的方法用 list 做前缀
-  获取统计值的方法用 count 做前缀
-  插入的方法用 save(推荐) 或 insert 做前缀
-  删除的方法用 remove(推荐) 或 delete 做前缀
-  修改的方法用 update 做前缀
### 应用分层（参考阿里巴巴Java开发手册）
![image](http://oss.chenlintech.com/common/0.png)
### 项目演示
- 演示地址：[http://dp.chenlintech.com](http://u.720life.cn/g/7d03172ba0f4c2010f2a1c33c0ede0163a1d330bb6bd3ab7a22bf998db645798e6e4cdb3dac7b66ee2f5913b980d076e)
- 账号密码：admin / 1
### 运行效果
![image](http://oss.chenlintech.com/lte/1.png)
![image](http://oss.chenlintech.com/lte/2.png)
![image](http://oss.chenlintech.com/lte/3.png)
![image](http://oss.chenlintech.com/lte/4.png)
![image](http://oss.chenlintech.com/lte/5.png)
![image](http://oss.chenlintech.com/lte/select2.png)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5004432eb016d2449d339dacc60b6be0553e7bb7499e4cafe90d0dfc8b428bf1c5c99879b7674fadd2de299c44ebf58c)