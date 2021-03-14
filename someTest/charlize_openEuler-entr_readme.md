# entr RPM package on openEuler

[entr](http://u.720life.cn/g/9885e75152161bdc8d995db6f59b6fbb4cbc5f6eb6d5c61d063ce638c430dfb7) is a file watcher,
which run specified commands when target files change.

# Build Package

To build a RPM package, create packaging scaffold with `rpmdev-setuptree`
if it doesn't exist.
Then copy entr-4.5.tar.gz ([upstream URL](http://u.720life.cn/g/9885e75152161bdc8d995db6f59b6fbbf18ae683ac8fc08760a149e43d00b17903cf6b08cafd7d3d215a7ed9b63738fe1c10a85b24aa67a6c5f25dc8e1a387ab)
to ~/rpmbuild/SOURCES, entr.spec to ~/rpmbuild/SPECS, and run:
```
rpmlint entr.spec
rpmbuild -bs entr.spec
rpmbuild -bb entr.spec
```

Verified on openEuler 20.03 (LTS), Jun 4, 2020.




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1b9b5762558d9a5dbd4dd586cb587dea29064997999ea5f986dbdd685ac1e7ed46d649974169ca7cb0283f25aac43d70)