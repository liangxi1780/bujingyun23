# libjson

libjson 是一款简单、高性能的 C 语言 json 库，以 LGPL 协议发布。

libjson 支持以 SAX 模式进行解析，也支持以 DOM 模式解析。

libjson 以非常节制的方式使用内存。以 SAX 模式进行解析时，libjson 不动态分配任何内存。以 DOM 模式进行解析和序列化时，libjson 仅为每个节点分配 20 字节（32 位系统）或 32 字节（64 位系统）内存（字符串本身占用的空间除外）。

libjson 本身是线程安全的。但是如果使用 SAX 模式进行解析，需要自行保证传入的回调函数线程安全。

libjson 目前使用递归方式生成与解析 json 文本，所以如果 json 对象的嵌套层数过深，可能会导致堆栈溢出。

## 数据类型与精度限制

libjson 对字符串存在长度限制，对数值存在精度限制。

在任何系统下，libjson 在解析时使用 double 类型变量存储浮点数，使用 long long int 类型变量存储整数。如果被解析的 json 字符串超过了这个限制，解析获得的数值将不正确，但 libjson 目前并不会因此而返回任何错误。

### 32 位系统
name 长度不能超过 255 个字节（8 位），value 字符串长度不能超过 65535 个字节（16 位）。如果被解析的 json 字符串超过了这个限制，则会发生高位截断。但 libjson 目前并不会因此而返回任何错误。

例如，如果某一个 name 的长度为 300，那么 300 会被截断为 44。

### 64 位系统
name 长度不能超过 262143 个字节（18 位），value 字符串长度不能超过 274877906943 个字节（38 位）。如果被解析的 json 字符串超过了这个限制，则会发生高位截断。但 libjson 目前并不会因此而返回任何错误。

## 编译

```
make -f nbproject/Makefile-Release.mk QMAKE= SUBPROJECTS= .build-conf
```

## 测试

```
make -f nbproject/Makefile-Release.mk SUBPROJECTS= .build-tests-conf
```

### 解析测试

```
./build/Release/GNU-Linux-x86/tests/TestFiles/f1 ./tests/test.json 1 p
```

### 性能测试

```
time ./build/Release/GNU-Linux-x86/tests/TestFiles/f1 ./tests/test.json 1000000 n
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eaf64497d59eb2adbf8473fe2eef265a0440b9b267fa29bed2b07665f31eb97667a78be8e92361267117b86c167cd6bf3)