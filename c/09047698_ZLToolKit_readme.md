# 一个基于C++11简单易用的轻量级网络编程框架
平台|编译状态
----|-------
Linux | [![Build Status](https://travis-ci.org/xiongziliang/ZLToolKit.svg?branch=master)](https://travis-ci.org/xiongziliang/ZLToolKit)
macOS | [![Build Status](https://travis-ci.org/xiongziliang/ZLToolKt-build_for_mac.svg?branch=master)](https://travis-ci.org/xiongziliang/ZLToolKt-build_for_mac)
iOS | [![Build Status](https://travis-ci.org/xiongziliang/ZLToolKt-build_for_ios.svg?branch=master)](https://travis-ci.org/xiongziliang/ZLToolKt-build_for_ios)
Android | [![Build Status](https://travis-ci.org/xiongziliang/ZLToolKt-build_for_android.svg?branch=master)](https://travis-ci.org/xiongziliang/ZLToolKt-build_for_android)
Windows | 已经完成移植

## 项目初衷
多年的编程经历让我接触过多种网络开源库，譬如libevent、libev、libuv、boost.asio等等。这些开源框架有些是用C语言开发的，里面包含了各种难以阅读层层嵌套佶屈聱牙的宏，学习起来非常费力；有些使用起来又不甚方便，代码被切割成碎片零零碎碎；有些虽然使用简单，但是却非常宏大，牵涉各种代码，配置复杂，很难交叉编译。由于作者既从事过linux服务器编程又有jni、ios的编程经历，所以一直以来在寻求既能在服务器端高效运行又能在嵌入式平台方便开发的方法，但是一直没有找到比较合适的方案；于是作者大约在一年前开始整理多年的工作成果积累，抽取经过时间检验证明稳定有效的代码并且参考其他成熟的框架形成了这个项目。后面在我使用该项目（初期版本）用于实际开发，一路林林总总遇到了很多问题，但是在后面几个月不间断的调试、测试、修正、优化等过程中项目代码逐渐沉淀稳定，经过长时高强度的测试之后我把代码提交到github形成了这个项目。

## 特性
- 网络库
  - tcp/udp客户端，接口简单易用并且是线程安全的，用户不必关心具体的socket api操作。
  - tcp服务器，使用非常简单，只要实现具体的tcp会话（TcpSession类）逻辑,使用模板的方式可以快速的构建高性能的服务器。
  - 对套接字多种操作的封装。
- 线程库
  - 使用线程实现的简单易用的定时器。
  - 读写锁。
  - 信号量的封装（ios下用条件变量实现）。
  - 自旋锁。
  - 线程组。
  - 简单易用的线程池，可以异步或同步执行任务，支持functional 和 lambad表达式。
- 工具库
  - 文件操作。
  - std::cout风格的日志库，支持颜色高亮、代码定位、异步打印。
  - INI配置文件的读写。
  - 监听者模式的消息广播器。
  - 基于智能指针的循环池，不需要显式手动释放。
  - 环形缓冲，支持主动读取和读取事件两种模式。
  - mysql链接池，使用占位符（？）方式生成sql语句，支持同步异步操作。
  - 简单易用的ssl加解密黑盒，支持多线程。
  - 其他一些有用的工具。
  - 命令行解析工具，可以很便捷的实现可配置应用程序
 
## 后续任务
- 提供更多的示例代码

## 编译(Linux)
- 我的编译环境
  - Ubuntu16.04 64 bit + gcc5.4(最低gcc4.7)
  - cmake 3.5.1
- 编译

  ```
  cd ZLToolKit
  ./build_for_linux.sh
  ```  
  
## 编译(macOS)
- 我的编译环境
  - macOS Sierra(10.12.1) + xcode8.3.1
  - Homebrew 1.1.3
  - cmake 3.8.0
- 编译
  
  ```
  cd ZLToolKit
  ./build_for_mac.sh
  ```
	 
## 编译(iOS)
- 编译环境:`请参考macOS的编译指导。`
- 编译
  
  ```
  cd ZLToolKit
  ./build_for_ios.sh
  ```
- 你也可以生成Xcode工程再编译：

  ```
  cd ZLToolKit
  mkdir -p build
  cd build
  # 生成Xcode工程，工程文件在build目录下
  cmake .. -DCMAKE_TOOLCHAIN_FILE=../cmake/iOS.cmake -DIOS_PLATFORM=SIMULATOR64 -G "Xcode"
  ```
## 编译(Android)
- 我的编译环境
  - macOS Sierra(10.12.1) + xcode8.3.1
  - Homebrew 1.1.3
  - cmake 3.8.0
  - [android-ndk-r14b](http://u.720life.cn/g/12b78f2738a1a1323c5b851b57f1c1148d9a9915620f61ab46129f5dfcee9ec9611bd48c550842c4f77d23a863332831b31febb29f7a013ed1144b600aeee15e9d268a9cb5b1c58405a3ff3679cb5ed7) 
- 编译

  ```
  cd ZLToolKit
  export ANDROID_NDK_ROOT=/path/to/ndk
  ./build_for_android.sh
  ```
## 编译(Windows)
- 我的编译环境
  - windows 10
  - visual studio 2017
  - [openssl](http://u.720life.cn/g/da0d6a2297e13be9dc831481b49bcedfdaeafb926043bc60d218e345e715a594642190b6b4bc80a2118cc1d7ea016b67e9f4b7faab8046d177cbcb1090ea7b6c) 
  - [mysqlclient](http://u.720life.cn/g/95e6cdfc419b9fe3e81ac644ae2e762d34429c000291673411318cb980922ba3076e96c701ed42f7bc080b9dd815a413) 
  - [cmake-gui](http://u.720life.cn/g/a75d52cde9c3226230e6270162b9978ed0bf780d4ffad3f67a26803ee7d842dfc20354741a97b69b6feacb59b931e441b47601f082643d822ff6e95a60a214d9) 
  
- 编译
```
   1 使用cmake-gui打开工程并生成vs工程文件.
   2 找到工程文件(ZLToolKit.sln),双击用vs2017打开.
   3 选择编译Release 版本.
   4 依次编译 ZLToolKit_static、ZLToolKit_shared、ALL_BUILD、INSTALL.
   5 找到目标文件并运行测试用例.
   6 找到安装的头文件及库文件(在源码所在分区根目录).
```

## QA
 - 该库性能怎么样？

基于ZLToolKit，我实现了一个流媒体服务器[ZLMediaKit]https://github.com/xiongziliang/ZLMediaKit);作者已经对其进行了性能测试，可以查看[benchmark.md]https://github.com/xiongziliang/ZLMediaKit/blob/master/benchmark.md)了解详情。

 - 该库稳定性怎么样？

该库经过作者严格的valgrind测试，长时间大负荷的测试；作者也使用该库进行了多个线上项目的开发。实践证明该库稳定性很好；可以无看门狗脚本的方式连续运行几个月。


## 联系方式
- 邮箱： 
- QQ群：542509000





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)