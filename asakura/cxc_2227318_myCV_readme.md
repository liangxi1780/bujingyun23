# myCV 中文简历 LaTeX模板

主要参考：

- [billryan/resume](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466395c20f1ef44fa5877b251b88548e19c5a27df13e9dbf5b338ebc73f9007d03)
- [WonderCV 学生求职模板](http://u.720life.cn/g/332796aa4a603de88a6fbbdd6629a775dd077524527fd2ef6dc87ba1238f3ae869d0b687a08b2761666327a4a571b48a)

在[billryan的 一个简洁优雅的XeLaTeX简历模板](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466395c20f1ef44fa5877b251b88548e19c5a27df13e9dbf5b338ebc73f9007d03)基础上修改而来，删掉了大部分宏，只保留section定义，从而去掉cls文件，整合到一个tex文件内，严格来讲并不能算是一个模板，但是简历通常只有一两页，反而有时候在一个tex文件修改起来更方便。


简历外观主要参考[WonderCV 学生求职模板](http://u.720life.cn/g/332796aa4a603de88a6fbbdd6629a775dd077524527fd2ef6dc87ba1238f3ae869d0b687a08b2761666327a4a571b48a)，结合[billryan模板]https://github.com/billryan/resume Awesome Icons](http://u.720life.cn/g/8d9a295ace2e7390132a40554ec03408a74af59646b7e95e7b10272cae5ce4388db19b626dea1ace8839d9c0d8c97b39)。按照[知乎上关于简历字体的问答]https://www.zhihu.com/question/21451635


## 无照片 myCV.tex

源文件 myCV.tex

使用xelatex编译

```
xelatex myCV.tex
```

或者利用makefile

```
make myCV
```

截图如下

![无照片截图](shot-myCV.png)


## 有照片 myCV-Photo.tex

源文件 myCV-Photo.tex，利用tikz来插入照片，同时也加入了学校Logo和脚注信息栏，简历正文文字内容与无照片一模一样，只是额外增加三个tikz node，如果想去掉可以屏蔽掉相应语句。由于使用tikz来放置图片，需要多次运行xelatex编译

```
xelatex myCV-Photo.tex
xelatex myCV-Photo.tex
xelatex myCV-Photo.tex
```

或者利用makefile

```
make myCV-Photo
```

截图如下：

![有照片截图](shot-myCV-Photo.png)

# License
与[billryan/resume](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466395c20f1ef44fa5877b251b88548e19c5a27df13e9dbf5b338ebc73f9007d03)一样吧，

[The MIT License (MIT)](http://u.720life.cn/g/ba059582536a397f7c573b87c8bea647045b0ef049248233b6f76e909e70200fe7048b25e29c8bab79aeff32ea74556a)。




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eab7099772aedd16672b064a8f0d2c657ec70fb7d8d9a34e59d4c8b595af7767b0888d1f83bc513fa16f63fcfd8f265fb)