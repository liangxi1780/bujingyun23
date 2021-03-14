TurboDex: Fast load dex in memory
--------

[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-TurboDex-green.svg?style=true)](https://android-arsenal.com/details/1/3456)

[中文](CHINESE.md "中文")

It is generally known that load an **unoptimized Dex file** at runtime
in Android (especially in **ART mode**) would take a **long time**.
When your App is using **MultiDex or PluginFramework**,
You will find that this problem is hard to bear.

TurboDex was born to solve this problem, Like to **opens the god mode** for AndroidVM,
after using TurboDex, no matter how much Dex file your need to load,
it will be finished in **a very short time**.

# Quick Start Guide

## Building TurboDex
TurboDex has given you a **pre-compiled** version in **/Prebuilt**,
if you need to custom the TurboDex, you need to install **Android-NDK**.

```
✘ lody@MacBook-Pro ~/TurboDex/TurboDex/jni> ndk-build                  
SharedLibrary  : libturbo-dex.so
Install        : libturbo-dex.so => libs/armeabi/libturbo-dex.so
SharedLibrary  : libturbo-dex.so
Install        : libturbo-dex.so => libs/x86/libturbo-dex.so
```



## Config

#### Maven

```xml
 
   com.github.asLody 
   turbodex 
   1.1.0 
   pom 
 
```

#### Gradle

```groovy
compile 'com.github.asLody:turbodex:1.1.0'
```



## Usage
To use TurboDex, first add **library** to your project,
Then write the following code in your **Application**:

```java

@Override
protected void attachBaseContext(Context base) {
  TurboDex.enableTurboDex();
  super.attachBaseContext(base);
}


```

After your **enable** the TurboDex, No matter where you load the Dex, it will return quickly.
Example:
```
new DexClassLoader(...):

DexFile.loadDex(...);
```

## Others analysis and comment
http://note.youdao.com/share/?id=28e62692d218a1f1faef98e4e7724f22&type=note#/

然而，不知道这篇笔记的作者为什么会认为Hook模块是我实现的，
我并没有给Substrate那部分的模块自己命名，而是采用了原名：MSHook，
而且，
所有的Cydia源码我也保留了头部的协议申明，你知道源码的出处，却没有意识到这一点？

## Remark
QQ Group: **535498571**



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e31e15641f9852e20e16a61710fd0d1a83e638cdb8b8e332c6a53fbdc7e878c34d59cb5b42bfa56f86a0049b530a0e551)