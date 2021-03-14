###  您可以考虑给作者来个小小的打赏以资鼓励，您的肯定将是我最大的动力


 **Description** 

JuCheap V2.0响应式后台管理系统模板,MVC5+EF6+Bootstrap3搭建了一个通用的后台管理系统的模板，里面使用到的技术包括：MVC,EF,T4模板批量生成,Jquery,jqGrid,Bootstrap,DDD,AutoMapper等

 **Instructions** 

1.框架使用的EF Code First模式，在运行的时候，程序自动帮你初始化数据库、数据表和初始数据.  
2.配置Web.Config文件里面的数据库连接字符串，就可以直接运行项目.  
3.默认数据库类型是MySql，如需要使用MsSql，请按照web.config 文件中的注释修改. 
4.初始数据放在，JuCheap.Data项目的/Config/Configuration.cs文件里面. 

 **Attentions** 

~~记得将Web.config文件里Form认证里面的domain改成自己的，要不会登录不了~~

 ~~&lt;forms name="AuthenToken" loginUrl="~/Adm/User/Login" timeout="2880" domain="www.jucheap.com" /&gt;~~ 

 身份认证已由forms认证改成了asp.net identity身份认证,对于登陆认证不再需要做额外的配置。 

 **Demo view**

![jucheap](http://git.oschina.net/uploads/images/2016/1109/115238_f6e40415_422345.png "jucheap")

![jucheap](http://git.oschina.net/uploads/images/2016/1109/115304_99754093_422345.png "jucheap")

![jucheap](http://git.oschina.net/uploads/images/2016/1109/122732_191c2c6c_422345.png "jucheap")

![jucheap](http://git.oschina.net/uploads/images/2016/1109/122746_7a14746f_422345.png "jucheap")

![jucheap](http://git.oschina.net/uploads/images/2016/1109/122754_cbf08341_422345.png "jucheap")

![jucheap](http://git.oschina.net/uploads/images/2016/1109/122802_622365f2_422345.png "jucheap")

 **net core 版本**   
最新源代码：https://gitee.com/jucheap/JuCheap.Core  
预览地址：http://core.jucheap.com  


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e81e86b4f8fb5c0a2b092425e5fdfaeddb77f4cbe2d979f3c1acdd4b3da88d7539b8250a029c8df4ca614dfb7ecbbda75)