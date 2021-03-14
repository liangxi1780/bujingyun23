****

* KopSoftTool 条形码二维码标签编辑打印软件,C#串口通信SerialPort
* 官网 http://kopsoft.cn/
* github源码 https://github.com/williamyang1984/KopSoftTool
* gitee源码 https://gitee.com/william_yang/KopSoftTool

****

## 软件架构

Microsoft .NET Framework 4.5

ZXing.Net

## 条形码二维码标签编辑打印软件

C#打印
1.建立PrintDocument对象
2.设置PrintPage打印事件
3.调用Print方法进行打印

BarcodeWriter用于生成图片格式的条码类，通过Write函数进行输出
BarcodeFormat枚举类型，条形码/二维码
QrCodeEncodingOptions二维码设置选项，继承于EncodingOptions，主要设置宽，高，编码方式等
MultiFormatWriter复合格式条码写码器，通过encode方法得到BitMatrix
BitMatrix表示按位表示的二维矩阵数组，元素的值用true和false表示二进制中的1和0

支持文本、图片、条形码、二维码、直线等对象自由拖拽、删除，纸张尺寸边距设计等，
并可保存为XML模板，可直接打印到打印机，数据源支持XML、EXCEL、数据库等

##操作步骤
* 1.纸张设置：选择纸张尺寸或自定义纸张尺寸
* 2.条形码；二维码；图片；文本；直线；设置好属性后 插入到编辑界面
* 3.各对象支持拖拽操作，按Delete可删除当前选中的对象
* 4.编辑好准备打印的内容后到“打印”TAB页，“保存配置”会将当前内容保存为XML文件
* 5.保存配置后可以“打印预览”，也可以直接“打印”
* 6.“读取配置”用于直接读取之前设计好的模板打印样式，文件保存在程序根目录中，默认模板为KopSoft.KopSoftPrint.PrintConfig.xml


## C#串口通信SerialPort
串口按电气标准及协议来划分，包括RS-232-C、RS-422、RS485
RXD 接收数据 Receive Data
TXD 发送数据 Transmit Data
SGND 信号接地 Signal Ground


## SCADA监控与数据采集
西门子PLC OPC
C#通过OPC Server自定义接口实现客户端数据读写
在客户端开发时，要使用OpcServer对象来实现客户端与Opc服务器之间的连接。一个OpcServer对象下有多个OpcGroup，一个OpcGroup下有多个OpcItem，
在自定义接口下的Client开发，是以Group为单位的操作，数据读写都是通过OpcGroup进行的。
引用OpcRcw.Comn.dll OpcRcw.Da.dll



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e65bd33215c0c2eef6950f30497b0b3a7b58d9265db4398a91061e533081192d4e57d1302b0933a713d07519c674681dc)