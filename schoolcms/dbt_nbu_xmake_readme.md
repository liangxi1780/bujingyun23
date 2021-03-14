 
   
     
     

   xmake 

   
     
       
     
     
       
     
     
       
     
     
       
     
   
   
     
       
     
     
       
     
     
       
     
     
       
     
     
       
     
     
       
     
   

   A cross-platform build utility based on Lua 
 

## Introduction ([中文](/README_zh.md))

xmake is a cross-platform build utility based on lua. 

The project focuses on making development and building easier and provides many features (e.g package, install, plugin, macro, action, option, task ...), 
so that any developer can quickly pick it up and enjoy a productivity boost when developing and building projects.

 

If you want to know more, please refer to:

* [Documents](http://u.720life.cn/g/009933c6d1d8db7dc76014c7712b610f3e9c36db087d1f7be6d68f559e7acc92)
* [HomePage](http://u.720life.cn/g/009933c6d1d8db7dc76014c7712b610f)
* [Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686d020c7eedf15e0fde31b8d1df57a875c1c3c733825798e96ec7cd6d9a7465b)
* [Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0b414e602eddce4a8f0ce918acbd93f0)

## Installation

#### via curl

```bash
bash  

## Package dependences

 

An official xmake package repository: [xmake-repo](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686d020c7eedf15e0fde31b8d1df57a87da4e3e28af8762a6cad4a8e867153c11)

## Build project

```bash
$ xmake
```

## Run target

```bash
$ xmake run console
```

## Debug target

```bash
$ xmake run -d console
```

## Configure platform

```bash
$ xmake f -p [windows|linux|macosx|android|iphoneos ..] -a [x86|arm64 ..] -m [debug|release]
$ xmake
```

## Menu configuration

```bash
$ xmake f --menu
```

 

## Package management

### Download and build

 

### Processing architecture

 

## Supported platforms

* Windows (x86, x64)
* macOS (i386, x86_64)
* Linux (i386, x86_64, cross-toolchains ...)
* Android (armv5te, armv6, armv7-a, armv8-a, arm64-v8a)
* iOS (armv7, armv7s, arm64, i386, x86_64)
* WatchOS (armv7k, i386)
* MinGW (i386, x86_64)

## Supported Languages

* C
* C++
* Objective-C and Objective-C++
* Swift
* Assembly
* Golang
* Rust
* Dlang
* Cuda

## Supported Projects

* Static Library
* Shared Library
* Console
* Cuda Program
* Qt Application
* WDK Driver (umdf/kmdf/wdm)
* WinSDK Application
* MFC Application

## Builtin Plugins

#### Generate IDE project file plugin（makefile, vs2002 - vs2019 .. ）

```bash
$ xmake project -k vs2017 -m "debug,release"
$ xmake project -k cmakelists
$ xmake project -k compile_commands
```

#### Macros script plugin

```bash
$ xmake m -b                        # start to record
$ xmake f -p iphoneos -m debug
$ xmake
$ xmake f -p android --ndk=~/files/android-ndk-r16b
$ xmake
$ xmake m -e                        # stop to record
$ xmake m .                         # playback commands
```

#### Run the custom lua script plugin

```bash
$ xmake l ./test.lua
$ xmake l -c "print('hello xmake!')"
$ xmake l lib.detect.find_tool gcc
```

#### Generate doxygen document plugin

```bash
$ xmake doxygen [srcdir]
```

## More Plugins

Please download and install from the plugins repository [xmake-plugins](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686d020c7eedf15e0fde31b8d1df57a873c806779a0dc15d15f3890c540ebeae3).

## IDE/Editor Integration

* [xmake-vscode](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686d020c7eedf15e0fde31b8d1df57a87449ea893941e7c36ee0a5c9283083f96)

 

* [xmake-sublime](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686d020c7eedf15e0fde31b8d1df57a87967f0dfd86a83f906aca1930c804c42e)

 

* [xmake-idea](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686d020c7eedf15e0fde31b8d1df57a87c2ce52594251ec40f54b6eee66e1e6d7)

 

* [xmake.vim](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463781662bec3c03b2c5e21808e18151b903c2645439847064570d90a2e36ac2b4) (third-party, thanks [@luzhlon](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466638af8d88a49145c422dcdb6c097ae7)

## More Examples

Debug and release modes:

```lua
add_rules("mode.debug", "mode.release")

target("console")
    set_kind("binary")
    add_files("src/*.c") 
    if is_mode("debug") then
        add_defines("DEBUG")
    end
```

Download and use packages in [xmake-repo](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686d020c7eedf15e0fde31b8d1df57a87da4e3e28af8762a6cad4a8e867153c11):

```lua
add_requires("libuv master", "ffmpeg", "zlib 1.20.*")
add_requires("tbox >1.6.1", {optional = true, debug = true})
target("test")
    set_kind("shared")
    add_files("src/*.c")
    add_packages("libuv", "ffmpeg", "tbox", "zlib")
```

Download and use packages in third-party package manager:

```lua
add_requires("brew::pcre2/libpcre2-8", {alias = "pcre2"})
add_requires("conan::OpenSSL/1.0.2n@conan/stable", {alias = "openssl"}) 
target("test")
    set_kind("shared")
    add_files("src/*.c")
    add_packages("pcre2", "openssl")
```

Find and use local packages:

```lua
target("test")
    set_kind("shared")
    add_files("src/*.c")
    on_load(function (target)
        target:add(find_packages("zlib", "openssl", "brew::pcre2/libpcre2-8", "conan::OpenSSL/1.0.2n@conan/stable"))
    end)
```

## Project Examples

Some projects using xmake:

* [tbox](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304657d8efa05c681e2a08f08f2bae66e5cd)
* [gbox](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466424aa5b40cf746504b4ea5c47c23c9d)
* [vm86](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a592dbb566eb4e33ab545a174182d754)
* [more](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d8dc405bc9b4a889f2719c1650ebcd358b3274c9840972f40ba0e7fd41a412b5)

## Example Video

 
 
 

## Contacts

* Email：[waruqi@gmail.com](mailto:waruqi@gmail.com)
* Homepage：[tboox.org](http://u.720life.cn/g/75a639d0ee98d7a448ed2dfa4621e70b6242cb21f61d3efae26fdcf3d3a8c999)
* Community：[/r/tboox on reddit](http://u.720life.cn/g/c0dd3a2651b78798f89b1013814805623f1a63a6d905c15df72e472aa578981e)
* ChatRoom：[Char on telegram](http://u.720life.cn/g/81b3001eda94fccf5f7753bb8378abc1fcf095c4ee51aaca4c117d3486d6058e), [Chat on gitter](http://u.720life.cn/g/11e95d0ed8d2826912e12fe1dc3f34213d053b7442ea437e8b47413e3457277d000d09d75a2b772c5816d6481f2d12ab86e9cc0202de789836269a74804e7434e4cbc98a75c1b924ec462db53c440da0c31d568070b9860bb1d51047347f379bad8b60e37e43c96c50a4aadddad62766)
* Source Code：[Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686d020c7eedf15e0fde31b8d1df57a875c1c3c733825798e96ec7cd6d9a7465b), [Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0b414e602eddce4a8f0ce918acbd93f0)
* QQ Group: 343118190(full), 662147501
* Wechat Public: tboox-os

## Thanks

This project exists thanks to all the people who have [contributed](CONTRIBUTING.md):
   

* [TitanSnow](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304615c5f86c5b7eef0ce7d2454c690258ad): provide the xmake [logo](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b3304ebdf790bf6982f623ede7607ecb1ef58862725eadf48b9b63d826ccea43) and install scripts
* [uael](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a0d60d8e8d634d32ab34950cd514cfb9): provide the semantic versioning library [sv](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466ec8fb9f18a335fc5c97a9ec8eb154fc)
* [OpportunityLiu](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304602d2744e654208976a4782debf67d5bad3a5dfe701e25f7aef038110bc44e617): improve cuda, tests and ci

## Backers

Thank you to all our backers! 🙏 [[Become a backer](http://u.720life.cn/g/df0d0b49c04f66c9033e4268d2ee0e12a64489b16ad012c774fb6abb45e45048d69679c7657d3a1306526bf1a245f4a7)]

   

## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](http://u.720life.cn/g/df0d0b49c04f66c9033e4268d2ee0e12a64489b16ad012c774fb6abb45e450489ef4078761c234702667a613fbbc90a7)]

   
   
   
   
   
   
   
   
   
   





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e81038e445af938a766588ab31f3d76ea077d7d6560a66676fb6a2e8017a336a8e3414ff87c4ee16769f984cd5bea60da)