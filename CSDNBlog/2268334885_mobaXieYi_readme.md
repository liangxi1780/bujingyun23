#protobufferUnity

1:src 目录是 protobuffer csharp port 修改后的代码， 用于ios 上面使用
2:Google.ProtocolBuffersLite.dll 是编译的ios 上可用的 dll
3:build.bat  是编译生成 协议dll 的脚本
4:cs 目录下面是 根据protos 目录 中协议 生成的cs 协议代码
    cs 目录的 AssemblyInfo.cs
    UpdateSln.py
    protoDll.csproj
    new.csproj
    是一个 cs 工程，执行 UpdateSln.py 之后 编译 new.csproj 可以生成协议的dll 文件， 需要mono 环境的支持，只在 mac上面测试过

5:windows 使用 protoc_win.exe mac使用brew install 安装的官方 protoc  pb 2.5.0版本



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed2ed4674b1b98decef41e8bd2e056e3020f321a58327f73c47362c5304515c9f3f9ac10a446820e553eae376bcc4378f)