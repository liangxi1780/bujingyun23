XDOC Office Server
==========================================

简介
----------------------------------------------
一个JavaEE服务，将Office文档转换为PDF，格式兼容性好。
![docx](https://raw.githubusercontent.com/myeeboy/xoffice/master/web/image/docx.png)
![pdf](https://raw.githubusercontent.com/myeeboy/xoffice/master/web/image/pdf.png)

安装部署
----------------------------------------------
1. 安装微软Office 2010或以上版本
2. 安装JDK 1.6或以上版本
3. 将release/jacob下的适合的dll文件复制到JDK的bin目录下。
   32位操作系统选：jacob-1.18-x86.dll，64位选：jacob-1.18-x64.dll。
4. 安装Tomcat 6或以上版本
5. 将release/war/xoffice.war复制到tomcat的webapps目录下，重启服务

调用
----------------------------------------------
http://locahost/xoffice/xoffice?_xformat=*文档格式*&_file=*文档地址*

文档格式：doc、docx、xls、xlsx、ppt、pptx

文档地址：http、ftp协议地址，需要用UTF-8编码

例：http://locahost/xoffice/xoffice?_xformat=docx&_file=http%3A%2F%2Flocahost%2Fxoffice%2Fdemo.docx

开源协议
----------------------------------------------
**MIT**

技术支持
----------------------------------------------
http://www.xdocin.com



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e678ddc3fd2b983defad1f4916033c2f23172e7479312639e1e28f8d0ca9d5dcf66e8554b502867a4272acf3ec60e8ecb)