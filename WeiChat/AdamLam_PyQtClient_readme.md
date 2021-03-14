# PyQtClient

PyQt Examples Client For https://github.com/PyQt5/PyQt

It requires both Python35-32 and PyQt 5.10 and QtWebKit.

需要Python35 32位 PyQt5.10 QtWebKit

## Installing （安装）

1.install requirements 安装依赖
```
pip install requests
pip install pygit2==0.27.2
pip install PyQt5==5.10.1
pip install PyQtWebKit==5.10.1
pip install PyQt3D==5.10.1
pip install PyQtChart==5.10.1
pip install PyQtDataVisualization==5.10.1
pip install PyQtPurchasing==5.10.1
```

if pip install PyQtWebKit==5.10.1 failed then do 2 and 3

如果 pip 安装PyQtWebKit失败, 可能是PyQt或者Python版本不对, 那么就需要自己编译了, 按照下面2和3

2.install QtWebKit [option]  安装QtWebKit [可选]

download [QtWebKit](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462fc09dc3d15acc5cfc430b0ef17277cea322053691c9a383692f51e17ff946ec) and extract to PYTHONPATH/Lib/site-packages/PyQt5/Qt

下载 [QtWebKit](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462fc09dc3d15acc5cfc430b0ef17277cea322053691c9a383692f51e17ff946ec) 并解压到 PYTHONPATH/Lib/site-packages/PyQt5/Qt

3.install QtWebKit pyd  复制编译好的QtWebKit

copy .Data/site-packages to PYTHONPATH/Lib/site-packages

## Notice

If the first boot is slow  第一次运行很慢（因为在clone例子源码）

    1. git clone https://github.com/PyQt5/PyQt.git
    2. move PyQt to PyQtClient\Resources\Data\Projects
    3. start PyQtClient

## ScreenShot

![PyQtClient](ScreenShot/PyQtClient.gif)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e66919745d335e109a9a102bde77d2c5eaa6d5683e315eaab62715378fd1f5b2b0f008f9a6b755bcb0514d13f52ca29d3)