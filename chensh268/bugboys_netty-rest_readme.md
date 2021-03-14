# netty-rest

#### 项目介绍
基于netty实现防spring mvc 的@RestController功能http请求
无需外部servlet容器,基于Spring+netty实现rest风格的http请求并实现Spring的@RestController功能。
netty自身提供了对http的支持,通过FullHttpRequest对象可以获取请求的url,和http请求方式,但是并没有处理url应该怎么处理请求.所以基本思路是:

1. 自定义注解:@Rest,@ReqMapping,@ReqParam , @Rest用于标记某个类是控制器,@ReqMapping用于标记方法哪个url对应该方法,@ReqParam用于标记方法参数,对应于哪个http请求参数

2.编写PackageScanUtils工具类用于扫描指定包下的class为类

3 通过反射获取带有@Rest注解的类并实例化,获取@Rest和@RuqMapping的value值,拼接成url,通过ConcurrentHashMap 以键值对的形式,记录url和对应方法Method的关系,当客户端请求时,通过url从Map中获取执行的Method和对应的Object,通过反射执行对应的方法

4 将反射调用方法得到的结果通FullHttpResponse返回,返回前先判断结果类如果是字符串直接通过ChannelHandlerContext.write输出,其他类型则通过json返回



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7cbece18be8fdbb58b7128e3752121f26c3d1762c68b5fec4cedc72f75fcb5ea0404c77fb1c1679b2a4c01b9788390af)