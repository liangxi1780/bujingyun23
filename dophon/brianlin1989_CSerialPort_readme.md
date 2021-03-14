 CSerialPort 

 
   
   
   
   
 
 

 
语言： English 英语  /  中文 
 

一个使用C++实现的轻量级串口类库，可以轻松在windows和linux下进行串口读写

---
# Design Principles 设计原则

* 跨平台
* 简单易用
* 高效

# Todo List 待处理事项

## Strategic Goal 战略目标

- [x] 1.首先支持windows和linux平台
- [ ] 2.增加通用串口通信协议
- [ ] 3.支持热插拔
- [ ] 4.更高效的通知模块
- [ ] 5.支持其他语言，如C, C#, Python, Java, Golang等
- [x] 6.同步串口通信
- [ ] 7.全新的跨平台串口调试助手
- [ ] 8.增加一个类库的介绍和使用视频

## Short-term Goal 短期目标

- [x] 1.跨平台操作系统识别库
- [ ] 2.跨平台多线程类库
- [ ] 3.跨平台锁类库
- [ ] 4.跨平台高效定时器类库
- [ ] 5.性能测试报告


# Last Modify 最新版本

## Version: 4.0.2.200108
by itas109 on 2020-01-08

# Tested Machine 测试机器
* QT 5.6.2 MSVC2013u5 32bit - Win7 Ultimate 64bit CN - 2020-01-08
* QT 5.12.1 MSVC2017 64bit - Win7 Ultimate 64bit CN - 2020-01-08
* VS2013 update 5 - Win7 Ultimate 64bit CN - 2020-01-08
* VS2015 update 3 - Win7 Ultimate 64bit CN - 2020-01-08
* VS2015 update 3 - Win10 Enterprise 64bit CN - 2020-01-08
* QT 5.6.2 GCC 5.4.0 20160609 - Ubuntu 16.04 64bit En  - 2019-07-28
* VS2013 update 5 - Win7 Ultimate 64bit En - 2019-03-07
* QT 5.6.2 GCC 6.3.0 20170516 - DeepIn 15.11 64bit CN  - 2020-01-08

# directory List 目录列表

update : 2019-08-10

```
|-- CSerialPort # root
    |-- .gitattributes
    |-- .gitignore
    |-- LICENSE # LGPL3.0 license
    |-- README.md 
    |-- VERSION # version 版本号
    |-- Demo # example 示例目录
    |   |-- Comm # CSerialPort MFC Demo use source code win32直接调用源码MFC程序示例
    |   |   |-- Comm
    |   |   |-- Release # CSerialPort Release Application 可以直接运行的Release程序
    |   |       |-- Comm.exe
    |   |-- CommDLL # CSerialPort MFC Demo use Win32 Dll win32动态库MFC程序示例
    |   |   |-- Comm
    |   |-- CommQT # CSerialPort QT win/linux Demo QT win/linux 程序示例
    |   |-- CommNoGui # CSerialPort No Gui win/linux Demo win/linux无界面程序示例
    |   |-- CSerialPortDemoWin32Console # CSerialPort Demo for Win32 Console win32控制台程序示例
    |       |-- CSerialPortDemoWin32Console
    |-- doc # document 文档目录
    |   |-- common_problems.md # common problems 问答文档
    |   |-- CSerialPort_doc_cn.chm # Chinese documnet 简体中文说明书
    |   |-- CSerialPort_doc_en.chm # English documnet 英文说明书
    |   |-- error_guide.md # error guide 错误指南文档
    |   |-- How To Use.txt
    |   |-- suspending.txt
    |-- lib # lib 库目录
    |   |-- Linux # windows lib windows库目录
    |       |-- compile.sh # sh compile 命令编译
    |       |-- Makefile # Makefile compile Makefile编译
    |   |-- Windows # windows lib windows库目录
    |       |-- VC12 # windows lib for vs2013 windows vs2013库目录
    |           |-- libcserialport
    |               |-- libcserialport
    |-- pic # picture 图片
    |-- src # source 源代码
        |-- osplatformutil.h # os platform define 操作系统定义
        |-- SerialPort.cpp
        |-- SerialPort.h # Lightweight library of serial port, which can easy to read and write serical port on windows and linux with C++ 轻量级跨平台串口读写类库
        |-- SerialPortBase.cpp
        |-- SerialPortBase.h # CSerialPort Base class 串口基类 
        |-- SerialPortInfo.cpp
        |-- SerialPortInfo.h # CSerialPortInfo class 串口信息辅助类 
        |-- SerialPortInfoBase.cpp
        |-- SerialPortInfoBase.h # CSerialPortInfo Base class 串口信息辅助类基类 
        |-- SerialPortInfoUnixBase.cpp
        |-- SerialPortInfoUnixBase.h # CSerialPortInfo unix class unix串口信息辅助类基类 
        |-- SerialPortInfoWinBase.cpp
        |-- SerialPortInfoWinBase.h # CSerialPortInfo windows class windows串口信息辅助类基类 
        |-- SerialPortUnixBase.cpp
        |-- SerialPortUnixBase.h # CSerialPort unix Base class unix串口基类 
        |-- SerialPortWinBase.cpp
        |-- SerialPortWinBase.h # CSerialPort Windows Base class windows串口基类 
        |-- SerialPort_global.h # Global difine of CSerialPort 串口全局定义 
        |-- sigslot.h # signal and slot 信号与槽
```

# Error Guide 错误指南文档

[错误指南文档](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467320ae5ea7e199cba9f738140f7036a20352e1ddf28ead4f39627501cf5e221e0294e740673dd64eab1ac9d19c1ec1454e603df565bdeb2bdb9ba9e25c3f0267)

# Frequently Asked Questions 常见问题回答

[常见问题回答](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467320ae5ea7e199cba9f738140f7036a20352e1ddf28ead4f39627501cf5e221ec00fb5d737b4c5215ed9530ed35c8bf7)


# Result 结果

## linux：

## Gui 界面

示例路径: CSerialPort/Demo/CommQT

![image](https://github.com/itas109/CSerialPort/raw/master/pic/linux.jpg)

## No Gui 无界面

示例路径 1: CSerialPort/Demo/CommNoGui

![image](https://github.com/itas109/CSerialPort/raw/master/pic/linux_no_gui.jpg)

示例2如下所示 :

![image](https://github.com/itas109/CSerialPort/raw/master/pic/linux_no_gui_2.jpg)

* 示例代码

```
//sp.cpp

#include  
#include "SerialPort.h"

int main()
{
        itas109::CSerialPort sp;
        std::cout << "Version : " << sp.getVersion() << std::endl;
	sp.init("/dev/ttyS0");
	sp.open();
	std::cout << " open status : " << sp.isOpened() << std::endl;
	
	return 0;
}
```

* compile 编译

```
Linux源码编译
g++ sp.cpp SerialPort.cpp SerialPortBase.cpp SerialPortUnixBase.cpp -lpthread -o sp
./sp

Linux 动态库编译
g++ SerialPort.cpp SerialPortBase.cpp SerialPortUnixBase.cpp -fPIC -lpthread -shared -o libsp.so
g++ sp.cpp -o sp -L. -lsp
export LD_LIBRARY_PATH=./
./sp
```

## windows:

## Gui 界面

示例路径: CSerialPort/Demo/CommQT

![image](https://github.com/itas109/CSerialPort/raw/master/pic/win.jpg)

## No Gui 无界面

示例路径 1: CSerialPort/Demo/CSerialPortDemoWin32Console

示例路径 2: CSerialPort/Demo/CommNoGui
![image](https://github.com/itas109/CSerialPort/raw/master/pic/win_no_gui.jpg)

# Contacting 联系方式

* Email : itas109@qq.com

* QQ群 : [129518033](http://u.720life.cn/g/88d3be70c797d2a69a24ab56221f9e0339fd68ed2b2e8afb401b350bf89ee621cb3a5d50c0d0949a4b5a5d40cec53cc575a9cc7cbc4a3e7a7201c369242fe38914e5ebfb790a18a192307b1e039aea44f966a25c7f86f587604ca37597373fdca724ec9e7e2c6e6975b6f43dfb61be00)

# Links 链接

* [CSDN博客](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4ee37fa372494b831676c2fe053759503)
* [Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467320ae5ea7e199cba9f738140f7036a2679a258094471844ac763fc0e0efe4f2)
* [Gitee码云](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e40c8462a719416da8f5fcc0fbd3f6eab300d5550cc81142cfe46e96c6e3f44c4)

# Donate 捐助

---
# Other branches 其他分支

Remon Spekreijse的串口类库对于本类库有着深远的影响，十分感谢Remon Spekreijse
http://www.codeguru.com/cpp/i-n/network/serialcommunications/article.php/c2483/A-communication-class-for-serial-port.htm

仅支持windows版本分支 : 
https://github.com/itas109/CSerialPort/tree/CSerialPort_win_3.0.3

---

# License 开源协议

自 V3.0.0.171216 版本后采用[GNU Lesser General Public License v3.0](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467320ae5ea7e199cba9f738140f7036a2f61152670f79def8d80fa4273ec893a09bf88afda9b178850c2cd77c1e3031d4)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5f533de3e60e4c477a677e54d63894bf545e8657af1827e59ad5b9620d3a28bd9d95dfd40f6f6a4bebba96184827aaa5)