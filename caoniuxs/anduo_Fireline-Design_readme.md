#Fireline Design
背景介绍：作者从事 JAVA SWT桌面应用开发多年，深感JAVA 开发的 GUI代码的繁锁与重复 。于是想改进JAVA图行界面设计器 windowbuilder pro 在上面加入类似visaul studio design 中数据集的功能。注：该设计器目前只应用于SWT非swing
查看演示文档 请访问 http://my.oschina.net/TommyZgw/blog/296894

工程目录说明：
com.zgw.fireline.base 数据集控件源码 
com.zgw.fireline.bin 说明文档、与打包好的fireline +winbuilder 插件。 
com.zgw.fireline.demo 演示项目源码 
com.zgw.fireline.design fireline设计器源码 

安装fireline 设计器：
1 下载Eclipse3.6 (winbuilder 是基于3.6 的,但用其它版应该也没有问题，我用过在3.7也可以使用)
2 下载 com.zgw.fireline.bin 然后将“JAVA（SWT）仿visual studio GUI设计器.rar”解压至 eclipse 安装根目录即完成安装。也可 将 "WBPro_v0.9.0_UpdateSite_for_Eclipse3.6" 、"fireline_for_Eclipse3.6" 拷贝至根目录，在将links 拷贝至根目录

演示Demo说明：
1 下载并导入com.zgw.fireline.demo 工程
2 JDK必须使用 1.6以上版本
3 demo是一个 ‘产品管理’ 的程序，使用的数据库为 sqlite。直接运行 CpglView.java Main就可运行
4 CpglView.java 产品管理界面
5 CpglEdit.java 产品编辑界面
6 SqliteJdbcImpl 数据库实现，同时也是设计器的数据解析器（IDataBaseProvide 注：该类的修改必须重启Eclipse 才能作用于设计器）
6 关于设计器使用 请参考  http://my.oschina.net/TommyZgw/blog/296894


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8a8c3cfe226e287b6602ec890597ba73e558831a1a9d7b2ef02cf66f8580104e0ac040527677a95a12d0072d8dc67860)