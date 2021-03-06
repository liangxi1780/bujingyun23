
# QQt Foundation Class  

==============================================  

1. 支持绘制图表
    - QQtChart (compatiable with QChart and QCustomPlot)  
2. 支持检测USB设备热插拔  
3. 自定义了一部分特殊需要的控件，用来解决Qt的嵌入式bug。
    - 包括完全使用图片的checkbox（switchbutton）
    - QQtTabWidget，解决QtTab不能竖排横显文字的问题
    - QQt进度条，解决Qt进度条在Dialog中导致系统死机的问题
1. 添加精美控件
    - 包括复杂的圆盘进度条, SpeedMeter    
    - 包括有多种效果的Widget、Dialog
    - 二维码生成器、识别器，校验码生成器
    - 九宫格技术展示图片
    - Html解析器
    - 以及未列出的等20余种自定义widget。
4. 有线和无线网络自动连接管理类  
6. 解决Qt4.8.7在嵌入式屏幕上QGraphics系统不正常绘画的问题 
7. QQt输入法
    - 重写了UI，适配多种屏幕
8. Qt对象工厂，允许注册、生成、查找和删除所有来自QObject以及QWidget的类。
9. 嵌入式视频播放器，模拟端口实时预览器
0. QQt打印机，支持打印pdf
2. QQtWord，支持doc文档编写，输出pdf格式。
4. QQtTreeView，添加Qt4内部没有TreeView
    - 包括QQtXmlTreeModel、QQtJsonTreeModel、QQtFileSystemTreeModel、QQtSqlTreeModel
5. 支持工程的版本变更
    - 添加config.h.in支持
6. QQt通讯套件。
     - 通讯口类   
        - QQtSerialPort 兼容QSerialPort and QextSerialPort
        - [QQtSocketTcpClient](src/network/qqtsockettcpclient.h)、QQtSocketTcpServer、QQtSocketUdpClient、QQtSocketUdpServer
        - QQtBluetoothSocket +QQtBluetoothManager
        - QQtWebAccessManager，支持http、ftp等主流协议，高并发传输。
        - QQtWebSocket接口
     - 协议虚类（接口类） [QQtProtocol](src/network/qqtprotocol.h) QQtWebSocketProtocol
     - 报文虚类（接口类） [QQtMessage](src/network/qqtmessage.h)
5. 支持webservice
7. 添加应用中常用的form
8. 支持多页TableWidget
9. 添加 [QQtApplication](src/frame/qqtapplication.h)，支持入门级、通用级、专用级嵌入式App所必须的初始化内容
5. 支持Qt5.9.2   
0. 跨平台支持macOS、iOS、Android、Windows、Linux、MIPS、ARM等。  
1. 添加svg support widgets  
     - 比如 QQtSvgProgressbar
     - QQtSvgCheckBox
2. 添加 [QQtDictionary](src/core/qqtdictionary.h)   
     - 解决C Plus Plus中没有字典类别的尴尬。    
3. 添加Multi Link技术  
     - Multi Link technology，既多链接工程管理技术。
     - 基于qmake，用户可以轻易的添加自定义library。



# 摘要介绍下  

==============================================  
*LibQQt包括基础组成、精美组成*
- 基础组成，可以完成专业App所需要的业务功能和图形功能。
- 精美组成，包括高级业务功能和超级图形功能。（都在src/exquisite文件夹里）  

*如果用户希望精简LibQQt，qqt_header.pri里面有很多模块开关，开开关关能修剪。*  
*不建议使用cmake，建议使用qmake。*

# 使用方法  

==============================================   
在Windows平台上，  
*把LibQQt/extra/touch.exe 复制到C:\Windows*   
*把LibQQt/extra/md5.exe 复制到C:\Windows*   

[走，去看看入门用法](usage.md)  
[学习一下，设置工程目录](project.md)  

# 截图

==============================================  
[看入门用例截图](screenshot.md)

# 维基百科

==============================================  
[跳到转维基](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9aaa444e2f1036875cecfbadb1596e334a23cff87d2bb5922eba8702b500df7e "Wiki Home")


# 联系我  

==============================================  
邮箱: tianduanrui@163.com  
QQ: 2657635903  
发现了个问题: [new issue link](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb2b0aa9d7261b36afd426cb46da8070cad22ade872f471e098dc12478ca10a1e886d8232afe6c93c83e67846e4afc748fabf7d1faf1b3dc3bcb8e1162ba35f1c38d51069c617848331b028ba4c46d94f)  

# 依赖学习知识   

==============================================  

[预习Git 入门](usage-git.md)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfe127d85de6fd5591b9cc11308d08cccae0ab98e72f3e893b99d26fddb6361a5832e8e9154e533970a9b8a14462dbbb)