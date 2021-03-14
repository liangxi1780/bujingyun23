#dubbom-maven-plugin

用于对DubboM应用进行打包和开发调试插件

##插件配置
```xml
 
   
         net.dubboclub.maven 
         dubbom-maven-plugin 
         ${plugin_version} 
         
              配置打包输出目录 
              开发调试的dubbom的配置文件 
              spring的配置文件位置 
          
    
 
```
##修改你本地的mave的setting.xml
```
往setting.xml的  标签中添加
 net.dubboclub.maven 
```
##执行插件
###打包
`mvn install dubbom:pack`
###启动(当前项目必须是dubbom项目)
`mvn install dubbom:run`


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee372655bc5c5007b868532d08e520c4eedf5f6bbc0e25a8b681c350f3ced63978617c0d83fff0ff80d1b85588622ca6727e40b2690f8a17dda70f02505f98716)