# lua-click

一个用于快速创建命令行程序的Lua模块。该项目从python库[click](http://u.720life.cn/g/14bf35e3dea6f35fc907085b98609be38146dc45b5684aa11b4fff3dac5003af)借鉴了不少灵感，项目名也沿用了"click"这一缩写（Command Line Interface Creation Kit）。

## Dependencies

唯一的依赖就是：

* lua >= 5.1

该模块已在`lua-5.1.5`, `lua-5.2.4`, `lua-5.3.5`下验证通过。


## Quick start

一个简单的`HelloWorld`程序：

```
-- HelloWorld.lua

local function main(cmd, options, arguments)
    print(string.format("Hi, %s!", arguments["name"]))
    if options["speaker"]~=nil then
        print(string.format("%40s", "-- from " .. options["speaker"]))
    end
end

local cli = require("click")

local mainCommand = cli.FunctionCommand {
    desc = "Say hi to somebody.",
    options = {
        {"-s, --speaker", help="Specify the name of speaker."},
    },
    arguments = {
        {name="name", help="Your name."},
    },
    entry_func = main,
}

if cli.__name__()=="__main__" then
    cli.main(mainCommand, nil, arg)
end
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b72c092edd4e667bd926345def85763babae518e3fa87fafa092045812c283a763a26d3e80e4aadc289783fde9de7ab)