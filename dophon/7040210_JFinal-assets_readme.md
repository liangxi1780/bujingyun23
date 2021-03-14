## 说明
JFinal框架结合jsp、beetl、freemarker模版的js、css在线合并压缩插件！

结合CDN使用效果更佳哦

## 依赖
1. JFinal

2. yuicompressor

3. commons-io

## 使用
```
 
     net.dreamlu 
     JFinal-assets 
     1.0.0 
 
```

###Beetl中使用
###自定义标签
```
##自定义标签
TAG.assets = net.dreamlu.ui.beetl.AssetsTag
```
###js
```
 
      
 
```
###css
```
 
     
 
```

file: 需要压缩的js、css列表

assets.jjs示例：
```
#开头表注释
/js/jquery.min.js
/js/jquery-ui.min.js
/js/modernizr.min.js
/js/superfish.min.js
/js/application.js
```

###JSP中使用

首先、导入标签库
```
 
```

同理如beetl
```
 
	  
 
```
###freemarker中使用

首先、配置（可在JFinal的config中完成）
``` 
FreeMarkerRender.getConfiguration().setSharedVariable("assets", new AssetsDirective());
```

同理如beetl
```
 
	  
 
```

## 文章
[对css，js压缩之combo以及七牛cdn的思考:http://blog.dreamlu.net/blog/47](http://u.720life.cn/g/00df38750a0bb9d9cc98d2230bf8c7ae4569f69e2506f9b7d9cd085012093f31)

## 更新说明
>## 2015-12-30 v0.0.3
>1. 升级到JFinal2.1，JFinal低版本用户请使用`v0.0.3`

## 交流群
如梦技术：[`237587118`](http://u.720life.cn/g/88d3be70c797d2a69a24ab56221f9e0339fd68ed2b2e8afb401b350bf89ee621350895f23a887010bf0fceab6151068c95510f7848d51fb24af9d86d62fc5912dbb2c589d3eb07c6e4c64e6a59309bff3dfb7cf066ec6a2b50f3cbf60d7224e7ef49026677f619501372c29136359ef8)

## 捐助共勉
 
 
 

 
 

## License

( The MIT License )


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e90d7096ab2fa9c817fbea87321dce6e42cad37ccd0f935e78cf2f8be680da44eb7c49ee197f822f101d4c1af342e9760)