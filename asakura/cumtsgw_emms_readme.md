##企业物资管理系统
###简介

企业单位通常需要管理大量的设备，建立物资管理系统可以有效地节约人力物力资源，并提高管理效率。一个企业物资管理系统应具有以下功能：

- 
-     1.实现物资的购入、登记、报废等管理；
-     2.可将各类物资分配到企业各个科室以便使用；
-     3.可按照物资类别，名称，价格、科室等查询、统计；
-     4.可生成相应的统计报表；
-     5.个人申报功能；其他说明、限制：所管理的物资分两大类：固定资产（如家具、电器）、耗材（文具等）；每一件固定资产有唯一的资产编号；物资管理员可以完成以上1、2、3、4功能，而普通员工只可查询本人、本科室相关的情况；

###技术结构
    主要框架 : PHP7 + laravel5.4 +　mysql5.5.36 + composer1.3.2(依赖管理)
    前端 : jquery + bootstrap + jstree（树形结构） + echart（图表） + layer（弹出层）
    其他：  阿里大于短信等

###完成概况 
 项目演示地址   http://www.zhouyou.website/

 **项目主页** 


![输入图片说明](https://git.oschina.net/uploads/images/2017/0430/150209_bee4f761_1030765.gif "在这里输入图片标题")

 **购买审批**  
-    1 待审批通知
-    2 历史记录
-    3 导出到 excel
-    4 打印当前表单

![输入图片说明](https://git.oschina.net/uploads/images/2017/0430/150249_bd6f2d02_1030765.png "在这里输入图片标题")


**搜索功能** 
- 根据名称，类别，价格和部门搜索物资信息

![](https://git.oschina.net/uploads/images/2017/0430/150346_721b67a7_1030765.png "搜索物资信息")


 **树形结构管理** 
- 以符合公司组织结构的树形结构管理物资。
- 可在树形目录上点击右键增删改查和拖拽移动节点，符合现实中的人事调动和物资分配。
- 每个部门可以有部门管理员管理所在分支，职责划分明确。
- 用 jquery 实现懒加载分支信息，减小服务器负载压力。

![输入图片说明](https://git.oschina.net/uploads/images/2017/0430/150546_a378f1f5_1030765.png "在这里输入图片标题")

 **统计** 
- 为系统记录提供图形化统计

![输入图片说明](https://git.oschina.net/uploads/images/2017/0430/150622_1f209bae_1030765.png "预约Top10统计")

其他：

- 公司树权限 ： 部门管理员，只能看到自己所在部门的物资记录。
            普通员工删除的记录，部门管理员可见；部门管理员删除的记录，公司树的顶级管理员可见。
- 系统权限 ：　软件即服务的理念（SaaS），系统管理员可以停止和恢复对一家公司的服务。（待完善）
- 提供站内消息和短信消息两种通知
- 为租借提供可选的外送服务
- 提供预约功能，当物资可用时，有消息通知
- 提供维修功能等

###目录结构

- 典型的laravel项目
- 需要的 .env 中添加阿里大于的短信验证的配置

###项目部署

- 1、拉代码$ git clone http://git.oschina.net/uchiyou/emms
- 2、安装依赖$ composer install --optimize-autoloader --no-dev
   $ composer dump-autoload --optimize
- 3、编译前端文件$ gulp --production
- 4、清理$ php artisan clear-compiled
    $ php artisan optimize
- 5、php -S localhost:8080(url)

 **部署到linux上可能遇到的问题：**

- 步骤2 出现 out of memory 类似问题。

    １　系统内存不够，关闭一些程序。 composer install 很吃内存。

    composer的其他问题参考 https://getcomposer.org/doc/articles/troubleshooting.md


- 访问的时候如果出现 ```
Please provide a valid cache path.
``` 的异常提示。解决方法：

    1、确保storage目录下有如app，framework，views三个目录。

    2、确保storage/framework目录下也有cache，sessions，views三个目录。缺少以上目录就手动创建，然后赋予写的权限。

    `chmod 777 -R storage/logs`
    `chmod 777 -R bootstrap/cache` 

    否则会发生`TokenMismatchException in VerifyCsrfToken.php line 68:异常

###开源协议
        本着学习和共享的精神，项目自身采用 MIT协议。
###关于作者
    作者为能力有限,有需求改进或程序有不规范之处，欢迎指出。

    想联系作者或兴趣爱好者，欢迎加群 636619354 交流。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec0710275ae67f9a63ab5c1cd2f46d46c3e075b687055325cba5208be579185948258f8b113775b4fa51e09ddda27e09e)