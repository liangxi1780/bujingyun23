## OSDA - The Open Serial Debug Assistant

 
       
       
       
 

![OSDA](Docs/source/_images/osda.png)

## 架构

软件支持 WPF [Microsoft .NET Framework 4.6.1](http://u.720life.cn/g/198c5e64072a1965c346756d06ffda87ebae84a9bae759b6d250296ecb1539da6e6aa1e5488dd3ea0a735e9c700557f094d736e2e0470369280bc84e4192140c) 和 WPF [Microsoft .NET Core 3.0.0]( https://dotnet.microsoft.com/download/dotnet-core/3.0 ) 两种框架，使用 MVVM 模型开发。

![Framework](Docs/source/_images/framework.png)

## 功能

- [x] 基础功能（打开、关闭、接收、发送、清接收区、清发送区和清空计数）
- [x] 十六进制（HEX）接收，十六进制（HEX）发送
- [x] 自动发送
- [x] 保存接收数据（可自定义保存位置）
- [x] 发送文件
- [x] 编码方式（ASCII，UTF-8，UTF-16，UTF-32）
- [x] 流控制（握手协议、控制协议）
- [x] 暂停接收
- [x] 发送新行（三种换行符）
- [x] 信号控制（RTS，STR）
- [x] 信号检测（DCD，CTS，DSR）
- [x] 在线更新
- [x] 精简视图（只保留接收区和发送区）
- [ ] 全球化和本地化

####  串口属性

* 串行端口传输前后的默认编码方式为 UTF-8 
* 串行端口输入缓冲区大小配置为 2MB
* 串行端口输出缓冲区大小配置为 1MB
* 串行端口默认流控制为 None（无控制流）
* 串行端口信号控制 Rts 和 Dtr 默认均未启用

## 安装

#### 先决条件

1. 仅支持 `Windows7 Service Pack 1(SP1)` 及以上版本（不支持 `Windows XP`）。`Windows7` 未安装 `SP1` 请  [点击此处](http://u.720life.cn/g/3f6bc38e6938b6711866a3ba7ee64d80176db063e9ea1e0b9be246bed2c417b06a25504ca5c8d6356b5d6a41c3a0852971cbd7c462d1aa869312f7fbd72d87e3c864e9b9477a5865f053b31a2d9853238b02053cb8aafe1905c54a2ca5588128) 根据网站页面描述下载安装（Microsoft官方网站）。

2. 已安装 `Microsoft .NET Framework 4.6.1` 。未安装请 [点击此处](http://u.720life.cn/g/198c5e64072a1965c346756d06ffda87ebae84a9bae759b6d250296ecb1539da6e6aa1e5488dd3ea0a735e9c700557f094d736e2e0470369280bc84e4192140c) 根据网站描述下载安装（Microsoft官方网站）。

#### For Windows

下载最新的 [OSDA 安装程序](http://u.720life.cn/g/bb190da35179160bd6ff0821e36e10cbb3dd5aa91979e9662346c5ed8ca9d01b164bf9d85f8e0eaca807d5ddf4c1d968)。可以选择从 `Gitee` 或 `Github` 站点下载。

## 编译

#### For Windows

- [ ] VS2015
- [x] VS2017（仅支持 .Framework 框架）
- [x] VS2019（支持 .Framework 和 .Core 两种框架）

```bash
$ git clone https://gitee.com/leven9/OSDA.git
$ cd OSDA/msvc
```
* 对于 VS2017 ，双击 `OSDA2017.Framework.sln` 
* 对于 VS2019 ` .Framework` 框架，双击 `OSDA2019.Framework.sln` 
* 对于 VS2019 `.Core` 框架，双击 `OSDA2019.Core.sln`

## 贡献

请参阅项目的贡献者指南（贡献者指南可以在 [GitHub](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cbdeeb5098ecc4d617fd138b3b9e8689666c82afcfae50782f0d961698bc3fab4d4ad4340b99f42c5631f944a7b3d09b) 或 [Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0031bbf78be7bd491c922f3b0aeeef4dfd0a749c6350cd43cf6145410fe97e38d5727757de9a2f90ec30d418d93a52a0) 中找到）。

## License

软件采用 MIT License 授权（授权许可证可以在 [Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464932d0cd96a3a0fc2955248fcc1db7ac) 或 [Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e780f70453f50e993aaa446009d8e60b6) 中找到）。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5753d25175f69f93d89d6b4fc94d4d9ef255a68fe88e05001d545dce53a6054939842b39c06e0d8ae5961d99fe39ec6c)