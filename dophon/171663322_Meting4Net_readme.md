 
 
 
 Meting4Net 

> :cake: 一个强大的音乐API框架

[![repo size](https://img.shields.io/github/repo-size/yiyungent/Meting4Net.svg?style=flat)]()
[![LICENSE](https://img.shields.io/github/license/yiyungent/Meting4Net.svg?style=flat)](https://mit-license.org/)
[![nuget](https://img.shields.io/nuget/v/Meting4Net.svg?style=flat)](https://www.nuget.org/packages/Meting4Net/)
[![downloads](https://img.shields.io/nuget/dt/Meting4Net.svg?style=flat)](https://www.nuget.org/packages/Meting4Net/)


[English](README_en.md)

## 介绍

Meting4Net:  Meting  for .Net, thanks to  Meting .   

一个强大的音乐API框架促进你的开发
 + **优雅** - 简单易用, 对于所有平台均可一个标准格式.
 + **丰富** - 支持多个音乐平台, 包括 腾讯QQ音乐, 网易云音乐, 虾米音乐, 酷狗, 百度等.
 + **免费** - MIT协议 发布
 
## 进度

- [x] 网易云音乐 Meting Open API 移植完成 v0.1.0
- [x] 腾讯QQ音乐 Meting Open API 移植完成 v0.2.0
- [x] 酷狗音乐 Meting Open API 移植完成 v1.0.0

## 持续集成

| 环境 | 平台 | 状态 |
| :------: | :------: | :------: |
| Ubuntu-16.04 | .net core 2.0.0 | [![Build Status](https://dev.azure.com/Meting4Net/Meting4Net/_apis/build/status/yiyungent.Meting4Net?branchName=master)](https://dev.azure.com/Meting4Net/Meting4Net/_build/latest?definitionId=1&branchName=master) |
| Linux | mono 5.18.0.240 | [![Build Status](https://travis-ci.com/yiyungent/Meting4Net.svg?branch=master)](https://travis-ci.com/yiyungent/Meting4Net) |

## 需要

只需要满足下方其中一条.

- .NET Framework (>= 4.5) 且 Newtonsoft.Json (>= 12.0.1) 被安装.
- .NET Standard (>= 2.0) 且 Microsoft.CSharp (>= 4.5.0), Newtonsoft.Json (>= 12.0.1) 被安装.

## 安装

推荐使用 [NuGet](http://u.720life.cn/g/fc22af1986001aaffae545db699770d8eb394e3a04eef4059670cd53b2cb082e3dab350b0b72ca499751361187dfc71e), 在你项目的根目录 执行下方的命令, 如果你使用 Visual Studio, 这时依次点击 **Tools** -> **NuGet Package Manager** -> **Package Manager Console** , 确保 "Default project" 是你想要安装的项目, 输入下方的命令进行安装.

```bash
PM> Install-Package Meting4Net
```

## 快速开始

```csharp
using Meting4Net.Core;
   ...
// 初始化 网易云音乐API
Meting api = new Meting(ServerProvider.Netease);
// 获得 json 数据
string jsonStr = api.FormatMethod(true).Search("Soldier", new Meting4Net.Core.Models.Standard.Options
{
    page = 1,
    limit = 50
});

return Content(jsonStr, "application/json");
//[{"id":"35847388","name":"Hello","artist":["Adele"],"album":"Hello","pic_id":"1407374890649284","url_id":"35847388","lyric_id":"35847388","source":"netease"},{"id":"33211676","name":"Hello","artist":["OMFG"],"album":"Hello",...
```

## 环境

- 运行环境: .NET Framework (>= 4.5) or .NET Standard (>= 2.0)    
- 开发环境: Visual Studio Community 2017

## 相关项目

 - [Meting](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678949a1447c7dc67ce057ac609f6fd7212707ff626e895c4d6fe3d13d0e1ee33)
 
 ## 鸣谢
 - 本项目由  Meting  移植而来，感谢原作者 metowolf 的贡献
 - 网易云音乐API加密模块参考  Music163Api ，感谢作者 IllyaTheHath 的贡献


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ebc7d6baf124acae48e9278b89981579eafc96e78a9e07bf3ececc6b554ef030e0d16a38ff53b5e04f4e56426290cb183)