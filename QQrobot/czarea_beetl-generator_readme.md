### 1.简介
beel-generator是一个代码生成工具，根据数据库表，生成基本的CRUD代码，提升开发效率。
**依赖技术有：**
beetl2.0（模版引擎） + jfinal2.1（用到其中DB插件工具） + JDK1.7

### 2.使用流程
![image](http://www.wailian.work/images/2018/04/09/0c6c106dea300935.png)

### 3.模版配置
配置文件在src/main/resource/conf目录下，db.properties配置数据库等，template.properties配置模版路径，数据库表等
```
#选择模板路径
template.selected=
#all或者不填，为生成全部；多个表已逗号分隔
template.tables=
#表前缀
template.table.remove.prefixes=t_
#配置单表的搜索列，多个列逗号分割，大小写不敏感
template.table.OPERATION_TEAM.searchColumn=NAME

#生成路径
template.output.path=/output/
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e6de5ff95b0cf2eab26fa89d18f1ef45ba27703645d6da004602033c182a155576fd223d4d90db8ec2826fa450b898923)