# 1 study-part4-springboot介绍

study-part4-springboot是《全栈工程师修炼之路》的Part4部分。本教程是书籍+源代码+视频（未来录制）
本教程是本人原创教程，90%以上示例代码都经过本人亲自所敲，引用他人示例的本人会标明引入来源。
原创不容易，请支持。如有雷同，请多多包涵！

# 2 源码包括：
0. Part1中用到的ajax示例-后台交互部分；
1. SpringMVC常用的注解；
2. SpringBoot整合MyBatis的XML使用；
3. SpringBoot整合MyBatis的注解使用；
4. SpringBoot整合MyBatis-Plus使用；
5. SpringBoot整合JPA使用；
6. SpringBoot整合MongDB；（更新中）
7. SpringBoot整合ES；（更新中）
8. SpringBoot更多整合；
9. SpringBoot实际项目案 例；

# 3 数据库相关
***注意MySQL5和MySQL8链接的区别：***
```
 1. MySQL5 的链接：jdbc:mysql://localhost:3306/db?allowMultiQueries=true
 2. MySQL8 的链接：jdbc:mysql://localhost:3306/db?serverTimezone=UTC&allowMultiQueries=true
 ```

# 4 基本步骤：
1. 请先创建数据库（在db文件夹下，数据库名称和项目名称一致）；
2. 据库不对应的请自行调整；
3. 找到test下的相关测试类，进行测试；
4. 建议找到select查询测试方法，运行看看；
5. 之后一次通过test类中的所有方法执行：新增、修改、删除、查询、分页等；

# 5 作者简介 莫小明
 
  ![image.png](https://upload-images.jianshu.io/upload_images/18601763-68f09e5e7bcd4262.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**悄悄的扫一下微信，就可以获得PDF电子书，B站：[https://space.bilibili.com/432367773](http://u.720life.cn/g/53d965c89cfaa89e69480af221ad5eb1dca87804eed5f80cd76c27e68f2f95b6ba2ef4740b958e1fc78d053de7cd6c64)**

* 2006至2008年 就职于北京东方国信，技术方向：Java、数据挖掘、算法和分析、Oracle、Linux。
* 2009至2015年 就职于斯欧股份（IBM顶级实施商），任职：华南区SOA架构师、项目总监。技术方向：EJB、Java、SOA（如：WebSphere Portal、BPM、ESB、MQ、Cognos BI、SSO等）。
* 2015至2018年 在深圳创业，担任CTO。技术方向：微服务、GO、SpringCloud、Docker虚拟化、高性能搜索引擎ES、高性能缓存Redis。主要研发分布式电商以及大数据方向产品。在创业2年内公司获得数千万融资。
* 2018年至今 回重庆二次创业，担任CTO，技术方向：Java、PHP、VUE、WX、微服务、SpringCloud、Dubbo等分布式架构，主持研发“低代码平台”。

**参与和主导过的部分项目（其他项目因商业化不方便提供）：**
* 国联通第二、第三期经营分析系统；
* 长安铃木整车零部件业务流程管控系统；
* 神华集团内蒙古准能能源生产监控系统；
* 广汽乘用车主数据管理平台；
* 佛山政府某区公有资产管理和监控平台；
* 湖南株洲三三一军工厂主数据管理平台
* 深圳市毅德控股集团商业地产商业管理；
* 北京某央企担保业务和全国各省市农业担保业务管理平台；
* 自主研发低代码平台；

# 6 书籍本章部分截图

![image.png](https://i0.hdslb.com/bfs/album/80474d725670fa50ff7e6c5e35df3fbdbc0ad86a.png)
![image.png](https://i0.hdslb.com/bfs/album/ad57969e121d016c7fc72a1ea915a9624212ca1a.png)
![image.png](https://i0.hdslb.com/bfs/album/59c99a992dce2f87781235580905baf794a324fb.png)
![image.png](https://i0.hdslb.com/bfs/album/3c3797b3dca5a0184dc8ec9a0f6c6c1a38a3e97f.png)
![image.png](https://i0.hdslb.com/bfs/album/d80cf544a85a613a8bc3bef49660640c8b028dcf.png)
![image.png](https://i0.hdslb.com/bfs/album/3f9ac075591885ff8f1c7020ca496a1adfb9b79c.png)
![image.png](https://i0.hdslb.com/bfs/album/09a0f3d95b59680c37340437d06ddebe673e7544.png)
# 7 示例部分截图
![image.png](https://upload-images.jianshu.io/upload_images/18601763-5710a84a13934fdd.jpg?imageMogr2/auto-orient/strip|imageView2/2/format/webp)
![image.png](https://upload-images.jianshu.io/upload_images/18601763-a2cfde3df2c5cd56.jpg?imageMogr2/auto-orient/strip|imageView2/2/format/webp)
![image.png](https://upload-images.jianshu.io/upload_images/18601763-cd63deeaefff7420.jpg?imageMogr2/auto-orient/strip|imageView2/2/format/webp)
![image.png](https://upload-images.jianshu.io/upload_images/18601763-c030aa12bba12c94.jpg?imageMogr2/auto-orient/strip|imageView2/2/format/webp)
![image.png](https://upload-images.jianshu.io/upload_images/18601763-58f9303579dd99af.jpg?imageMogr2/auto-orient/strip|imageView2/2/format/webp)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee2e3283e971c3985d3cd76fc16b22dd55aa83147d2183c1d1f5ecac009930d4acaa0e4dedfa181bb0f603efa038367ec260321cd583112b688488dc4237f727b)