> 目录

> 1.[功能介绍](#1-功能介绍)

> 2.[使用方法](#2-使用方法)

> 3.[API文档](#3-api-document)

> 3.1[－－－－－分组操作－－－－－](#3-1-分组操作)
 
> 3.1.1[获取分组信息](#3-1-1-getgroup)

> 3.1.2[根据名称查找分组标识](#3-1-2-getgroupidsbyname)

> 3.1.3[添加分组](#3-1-3-addgroup)

> 3.1.4[删除分组](#3-1-4-removegroup)

> 3.2[－－－－－库操作－－－－－](#3-2-库操作)

> 3.2.1[添加系统框架](#3-2-1-addsysframework)

> 3.2.2[添加框架](#3-2-2-addframework)

> 3.2.3[添加系统动态库](#3-2-3-addsysdylib)

> 3.2.4[添加动态库](#3-2-4-adddylib)

> 3.2.5[添加静态库](#3-2-5-addstaticlib)

> 3.3[－－－－－资源操作－－－－－](#3-3-资源操作)

> 3.3.1[添加资源包](#3-3-1-addbundle)

> 3.3.2[添加本地化资源](#3-3-2-addlocalizedfile)

> 3.4[－－－－－编译设置相关－－－－－](#3-4-编译设置相关)

> 3.4.1[获取编译设置信息](#3-4-1-getbuildsettings)

> 3.4.2[添加框架搜索路径](#3-4-2-addframeworksearchpath)

> 3.4.3[添加库搜索路径](#3-4-2-addlibrarysearchpath)

> 3.4.4[添加链接器标识](#3-4-5-addotherlinkerflag)

> 3.5[其他操作](#3-5-其他操作)

> 3.5.1[保存修改](#3-5-1-save)


# 1. 功能介绍
PBXProjectHelper是一个基于Python开发的，目的用于解析和操作PBXProject（XCode项目的配置文件）的工具类库。其提供了非常简单的方法来让开发者对XCode项目进行文件、类库以及项目设置的修改。从而达到自动化维护和管理的目的。

# 2. 使用方法
1. 导入PBXProjectHelper到你的Python脚本中。如：
```
import PBXProjectHelper
```

2. 初始化PBXProjectHelper工具类，并传入pbxproj文件的路径
```
helper = PBXProjectHelper ("/Users/fenghj/Documents/work/Demo/Demo.xcodeproj/project.pbxproj")
```

3. 调用PBXProjectHelper类提供的方法来操作PBXProj文件。如添加一个Group到XCode项目：
```
helper.addGroup ("Demo")
```

# 3. API Document

## 3.1 分组操作

### 3.1.1 getGroup

- 描述

根据分组标识来获取分组信息，取得的分组信息以Dict对象返回，其组织结构如下：

```
{
    isa = PBXGroup;
    children = (
        D04218DD1BA6CBB90031707C /* AppDelegate.h */,
        D04218DE1BA6CBB90031707C /* AppDelegate.m */,
        D04218E01BA6CBB90031707C /* ViewController.h */,
        D04218E11BA6CBB90031707C /* ViewController.m */,
        D04218E31BA6CBB90031707C /* Main.storyboard */,
        D04218E61BA6CBB90031707C /* Assets.xcassets */,
        D04218E81BA6CBB90031707C /* LaunchScreen.storyboard */,
        D04218EB1BA6CBB90031707C /* Info.plist */,
        D04218DA1BA6CBB90031707C /* Supporting Files */,
    );
    path = Demo;
    sourceTree = " ";
}
```

- 声明

```
def getGroup (self, gid)
```    

- 参数

**gid** - 分组标识

- 返回

分组信息的Dict对象。

- 示例

```
group = helper.getGroup("D04218E61BA6CBB90031707C")
print group
```


### 3.1.2 getGroupIDsByName 

- 描述

查询项目中指定名称的分组标识，因为一个项目中可能有多个同名的分组，因此该方法会以list形式返回多个分组标识。

- 声明

```
def getGroupIDsByName (self, name)
```    

- 参数

**name** - 分组名称

- 返回

与指定名称匹配的分组标识的List对象。

- 示例

```
groupIdList = helper.getGroupIDsByName("Demo")
```

### 3.1.3 addGroup

- 描述

添加分组，在项目的某个分组下新建分组。

- 声明

```
def addGroup (self, name, parentGroupId = None, isVarGroup = False)
```

- 参数

**name** - 分组名称

**parentGroupId** - 父级分组ID，默认为None，表示添加到项目的根分组中

**isVarGroup** - 是否为VariantGroup。True表示添加的分组类型为VariantGroup，否则为Group。默认为False

- 返回

被添加的分组标识

- 示例

```
groupId = helper.addGroup("Demo")
```

### 3.1.4 removeGroup

- 描述

删除一个分组，该方法请慎用，误删某些分组可能会导致项目无法运行。

- 声明

```
def removeGroup (self, gid)
```

- 参数

**gid** - 分组标识

- 返回

无

- 示例

```
helper.removeGroup("D04218E61BA6CBB90031707C")
```

## 3.2 库操作

### 3.2.1 addSysFramework

- 描述

添加系统框架，将系统内置框架(*.framework)添加到项目中。

- 声明

```
def addSysFramework (self, framework)
```

- 参数

**framework** - 框架名称，如：UIKit.framework

- 返回

无

- 示例

```
helper.addSysFramework("UIKit.framework")
```

### 3.2.2 addFramework

- 描述

添加框架，将框架(*.framework)添加到项目中。

- 声明

```
def addFramework (self, framework, groupId = None) 
```

- 参数

**framework** - 框架路径

**groupId** - 分组标识，默认为None，表示添加到Frameworks分组中

- 返回

无

- 示例

```
helper.addFramework("~/work/projects/Demo/Demo.framework")
```

### 3.2.3 addSysDylib

- 描述

添加系统动态库，将系统内置的动态库(*.dylib或者*.tbd)添加到项目中。

- 声明

```
def addSysDylib (self, dylib)
```

- 参数

**dylib** - 动态库名称，如：libz.dylib


- 返回

无

- 示例

```
helper.addSysDylib("libz.dylib")
```

### 3.2.4 addDylib

- 描述

添加动态库，将动态库(*.dylib或者*.tbd)添加到项目中。

- 声明

```
def addDylib (self, dylib, groupId = None)
```

- 参数

**dylib** - 动态库路径

**groupId** - 分组标识，默认为None，表示添加到Frameworks分组中

- 返回

无

- 示例

```
helper.addDylib("~/work/projects/Demo/Demo.dylib")
```

### 3.2.5 addStaticLib

- 描述

添加静态库，将指定的静态库(*.a)添加到项目中。

- 声明

```
def addStaticLib (self, staticLib, groupId = None)
```

- 参数

**staticLib** - 静态库路径

**groupId** - 分组标识，默认为None，表示添加到Frameworks分组中

- 返回

无

- 示例

```
helper.addStaticLib("~/work/projects/Demo/Demo.a")
```

## 3.3 资源操作

### 3.3.1 addBundle

- 描述

添加资源包，将指定的Bundle文件(*.bundle)加入到项目中.

- 声明

```
def addBundle (self, bundle, groupId = None)
```

- 参数

**bundle** - 资源包路径

**groupId** - 分组标识，默认为None，表示添加项目根分组中

- 返回

无

- 示例

```
helper.addBundle("~/work/projects/Demo/Demo.bundle")
```

### 3.3.2 addLocalizedFile

- 描述

将本地化文件（*.strings）添加到项目中

- 声明

```
def addLocalizedFile (self, lang, path, groupId = None)
```

- 参数

**lang** - 本地化语言标识，如：en、zh-Hant

**path** - 文件路径

**groupId** - 分组标识，默认为None，表示添加项目根分组中

- 返回

无

- 示例

```
helper.addLocalizedFile("en", "~/work/projects/Demo/Demo.strings")
```

## 3.4 编译设置相关

### 3.4.1 getBuildSettings

- 描述

获取项目或者指定Target的编译设置信息。并以Dict对象返回，其组织结构如下：

```
buildSettings = {
    ASSETCATALOG_COMPILER_APPICON_NAME = AppIcon;
    INFOPLIST_FILE = DemoIDFA/Info.plist;
    LD_RUNPATH_SEARCH_PATHS = "$(inherited) @executable_path/Frameworks";
    PRODUCT_BUNDLE_IDENTIFIER = cn.vimfung.DemoIDFA;
    PRODUCT_NAME = "$(TARGET_NAME)";
};
```

- 声明

```
def getBuildSettings (self, target = None, scheme = "Debug") 
```

- 参数

**target** - 项目编译目标，默认为None，即表示获取项目的根编译设置

**scheme** - 编译方案，如：Debug、Release，默认为Debug

- 返回

编译设置信息的Dict对象

- 示例

```
buildsettings = helper.getBuildSettings("Demo", "Release")
print buildsettings
```

### 3.4.2 addFrameworkSearchPath

- 描述

添加一个框架搜索路径（framework search path）到编译设置中。

- 声明

```
def addFrameworkSearchPath (self, path, target = None, scheme = "Debug") 
```

- 参数

**path** - 搜索路径

**target** - 项目编译目标，默认为None，即表示获取项目的根编译设置

**scheme** - 编译方案，如：Debug、Release，默认为Debug

- 返回

无

- 示例

```
helper.addFrameworkSearchPath("~/work/frameworks", "Demo", "Release")
```

### 3.4.2 addLibrarySearchPath

- 描述

添加一个库搜索路径（library search path）到编译设置中。

- 声明

```
def addLibrarySearchPath (self, path, target = None, scheme = "Debug") 
```

- 参数

**path** - 搜索路径

**target** - 项目编译目标，默认为None，即表示获取项目的根编译设置

**scheme** - 编译方案，如：Debug、Release，默认为Debug

- 返回

无

- 示例

```
helper.addLibrarySearchPath("~/work/libs", "Demo", "Release")
```

### 3.4.5 addOtherLinkerFlag

- 描述

添加一个链接器标识（linker flag）到编译设置中。

- 声明

```
def addOtherLinkerFlag (self, flag, target = None, scheme = "Debug") 
```

- 参数

**flag** - 标识，如: -ObjC, -all_load等

**target** - 项目编译目标，默认为None，即表示获取项目的根编译设置

**scheme** - 编译方案，如：Debug、Release，默认为Debug

- 返回

无

- 示例

```
helper.addOtherLinkerFlag("-ObjC", "Demo", "Release")
```

## 3.5 其他操作

### 3.5.1 save

- 描述

保存所做的修改

- 声明

```
def save (self) 
```

- 参数

无

- 返回

无

- 示例

```
helper.save ()
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4a554fa4290f9feda8b17000f49a4f17347c8b9f036ec1c3bcbbe72026db4fcd4bef26e5ac3bc0c62091fad14d297a667b8d407a10a356039fd2688ee061d1ef)