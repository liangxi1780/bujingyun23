 
 
 


![](https://img.shields.io/badge/build-passing-brightgreen)

**TecLab - M朋友圈**

---

微信小程序仿朋友圈样式开发。

[**1.项目介绍**](http://u.720life.cn/g/3e44a884c1d792dd0ec1ac531ed36da951bc166e5548e7579863e8413e9e9b5b4a74969c5046b5cc9fd5c43b68f810490e847940ed0d7fe291d6230ee00b0803)

[**2.项目如何部署**](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e70d3e1978915b757fb63081498d87eb0291b41036550b79639366e7484e0104662bf6e6b376f9ccfa9835a7a0f4ac0f68900937afbb8a4aae31880df2e6e8771c3394357208d242a744c71bbebedf1ba)





**M朋友圈 - 引用**

---

1.云函数 clouddb 、filter 、transfunc 部署并云端安装依赖

~~~
右键 - 上传并部署（云端安装依赖）
~~~

2.style文件夹下的样式引入全局样式中 （**引用colorUI**）且 app.wxss 中的样式也要保留，可以封装到一个wxss文件中再引用。

~~~css
@import "style/main.wxss";
@import "style/icon.wxss";
~~~

3.保留 _self 、utils 文件夹和其中内容 

4.进入云开发控制台，新建3 数据表，并设置其权限为 **所有用户可读，仅创建者可读写**

~~~
circles_list
remarks_list
thumbs_list
~~~




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4e2f88dbc3a5000b923dd1275912b348b300449e35c7c625195d32066603c6a47d5733630794f720ae828346bf218026)