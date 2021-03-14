# EventDemo
Spring的事件为Bean和Bean之间的消息通信提供了支持。
当一个Bean处理完一个任务之后，希望另外一个Bean能知道并做相应的处理，这时就需要让另一个Bean监听当前Bean的所发的  
**事件**  
这个事件可以理解为桌面应用程序的**点击事件**、**双击事件**  

其它就是常见的观察者模式：  
1.ApplicationContext是Subject和Context  
2.ApplicationListener是Observer  
3.Subject和Observer通过**ApplicationEvent**或其**子类**来进行匹配，只有匹配的Observer才会被调用  
4.ApplicationListener只要注册到ApplicationContext即可  



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e89c83480f3a3fa349b8fcc88cc94991d12b057dbcec23d864582d9ff3879ce4909113b7f456861e7ee469d86e2c12189)