## GTALabel

### 项目介绍
从国泰安 (GTA) 数据库提供的字段说明书直接提取变量标签和「数字-文字对应表」。

### 语法格式 (尚未写帮助文件)

```stata
syntax anything(id="txt file" name=filesource)  ///
     [, DO Fulllabel Lower Save(string asis) REPLACE Compress ///
        LABelvalue BOTH NODisplay]
```


#### 使用说明

```stata
which GTALabel 

global ff "GTAvar[DES][txt].txt"  //需要转换的文档

*- Test -labelvalue- , -both-  
GTALabel "$path/$ff"
GTALabel "$path/$ff", labelvalue 
GTALabel "$path/$ff", labelvalue both  // Error
GTALabel "$path/$ff", both

*- Test -lower- , -fulllabel-
GTALabel "$path/$ff", lower
GTALabel "$path/$ff", lower full

*- Test -compress- , -replace-
GTALabel "$path/$ff"
GTALabel "$path/$ff", compress

*- Test -save()- , -replace-
GTALabel "$path/$ff", save(aa.do)
GTALabel "$path/$ff", save(aa.do)
GTALabel "$path/$ff", save(aa.do) replace
GTALabel "$path/$ff", save(aa.do) replace labelvalue
GTALabel "$path/$ff", save(aa.do) replace both 
GTALabel "$path/$ff", save(aa.do) replace both nodisplay


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e771a616695ea4ee90fb716ba3f0b111cb72ff8be4cc5e849b7ba0112cd27a6c55411d4fd395d22bfae2a28564ea4236f)