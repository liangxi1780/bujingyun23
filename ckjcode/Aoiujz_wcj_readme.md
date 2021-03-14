wcj
---
[![](https://img.shields.io/github/issues/jaywcjlove/wcj.svg)](https://github.com/jaywcjlove/wcj/issues) [![](https://img.shields.io/github/forks/jaywcjlove/wcj.svg)](https://github.com/jaywcjlove/wcj/network) [![](https://img.shields.io/github/stars/jaywcjlove/wcj.svg)](https://github.com/jaywcjlove/wcj/stargazers) [![](https://img.shields.io/github/release/jaywcjlove/wcj.svg)](https://github.com/jaywcjlove/wcj/releases)

在使用 `Nodejs` 过程中，有很多包都支持全局安装，提供一个命令，然后在命令行我们就可以完成一些任务。有时候我们也需要开发这样的命令工具。`Node.js` 中发现弄个命令行工具特别轻松，我来学习如何使用 `node.js` 生成自己的command命令，在未来的项目中方便自己。  

- 先弄个小实例感受一下命令行的魅力
- 再用命令行实现输出自己的简历（我觉得这个可能很有趣）
- 常用的命令加入进来
  + ls 查看当前目录
  + ls -a 包括隐藏文件
  + 打开当前目录
- 就先这么计划着吧。

# 小实例

开始编写之前需要确认的一件事情是你已经安装了[Node.js](http://u.720life.cn/g/6dd25ec2eceebbb6348ad519a7343cbc690041c96fefc0320d9aace915151649)。你可以在命令行中运行 `which node` 来确认是否已经安装，或者运行 `node -v` 查看 node 的版本 。如果你已经安装了node，你可以看到类似于下面的输出结果，一般情况安装了node.js 顺带npm工具自动安装了。

```
$ which node
/usr/local/bin/node  

$ node -v
v0.10.36
```

## 创建目录

首先任意创建一个文件夹，初始化 `package.json` 文件，在该文件夹下创建bin目录：

```shell
$ mkdir wcj #创建一个文件夹
$ cd wcj && mkdir bin
$ npm init #初始化 `package.json` 文件
```

## 编写命令行

cd到 `bin` 目录下，新建一个 `wcj.js` 文件(名字自取)，编写如下代码，在js文件顶部加上 `#!/usr/bin/env node` 这段代码：

```js 
#!/usr/bin/env node  
var fs = require("fs"),
    path = process.cwd();

var run= function (obj) {
    if(obj[0] === '-v'){
        console.log('version is 1.0.0');
    }else if(obj[0] === '-h'){
        console.log('Useage:');
        console.log('  -v --version [show version]');
    }else{
        fs.readdir(path, function(err, files){
            if(err){
                return console.log(err);
            }
            for(var i = 0; i   ",
  "license": "MIT"
}
```

运行 `node bin/wcj.js` 会显示当前文件夹下的所以文件和文件夹名。这个玩意儿真的跑起来了。更多npm link的信息请[查看](http://u.720life.cn/g/8a79d8564074e2be842332888e4a773244e8414dc87c2b9e58a603dedda1b323)   

`package.json` 文件中 `bin` 里面的内容表示这个字段将 `wcj` 命令映射到了你的 `bin/wcj.js` 脚本。[bin参考](http://u.720life.cn/g/8a79d8564074e2be842332888e4a77324a9be8875228085cda46a40ce119b431f18be72a41b5ae9966f9ffc7f5f749ba) 

此工具采用 npm版本号采用的 [semver](http://u.720life.cn/g/73cc764475678a131c8c04bf7ecaf2f911baaade828a40560260c71e9ebe8760) 规则

```
"bin": { "wcj": "bin/wcj.js" }
```

[列子源码](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686e3d7a951d97bffd6c0f389bf91fbd4c3268299b913bee020bd96ce258de1b16a6543093bfd341992e975e1245ebd2d)

## 全局运行命令调试

> 确保你在 `package.json` 文件中添加了 `bin` 节点。然后打开命令了工具进入 `wcj` 目录 

如果在项目目录下运行没有问题，可以将当前目录模块安装到全局，也可以采用此方法来更新你的命令行工具

```
sudo npm install . -g
```

或者目录输入 `npm link` 会自动添加全局的 `symbolic link` ，然后就可以使用自己的命令了。

```shell 
$ wcj
#README.md
#bin
#package.json

$ cmd -v
# version is 1.0.0

$ cmd -h 
#Useage:
#  -v --version [show version]
```


## 错误

在运行 `sudo npm install . -g` 会有一堆警告可以忽视

如果你已经 `npm link` 搞了一遍你再 link 一遍，会报如下错误。即使你 `npm unlink` 也会报如下错误：

```
npm link
npm ERR! Darwin 14.3.0
npm ERR! argv "node" "/usr/local/bin/npm" "link"
npm ERR! node v0.10.36
npm ERR! npm  v2.7.1
npm ERR! path /usr/local/bin/wcj
npm ERR! code EEXIST

npm ERR! Refusing to delete: /usr/local/bin/wcj not in /Applications/XAMPP/xamppfiles/htdocs/git/github.com/myJS/wcj
File exists: /usr/local/bin/wcj
Move it away, and try again.
```

让你删除 `/usr/local/bin/wcj` 再 `npm link` ， 删除此目录运行 `rm -rf /usr/local/bin/wcj`

## 发布安装

### 发布到npm中
发布必须注册 [npm](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c963ac4e53f8a43f7c3d25154209847e9d0) 账号，还有 [github](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046edf2f9264e3b9b5f1c7e71411b34b37e) 账号，具体怎么玩儿问 谷歌大婶吧。在[JSLite.io](http://u.720life.cn/g/2aa53145cbec9fa581277eda417a9590) 中也有教程哦。

```
npm publish
```

### 安装
前提你发布到了[npm](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c963ac4e53f8a43f7c3d25154209847e9d0)中，你就可以运行下面的命令了。

```
sudo npm install -g wcj
```

例子下载：[v1.0.1](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686e3d7a951d97bffd6c0f389bf91fbd49c9598b5e205860a3c6fcf75981d0ef6ebdf9286d88f503d19941fb8949e3e21)

# Commander

依赖 `nodejs` 原生开发命令工具比较麻烦，[Commander.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304641a9458ec378561fe002b4aafaf5409c7e832617270508052782750b35f1ecb4) 可以帮助我们简化命令行开发。Commander 是一款重量轻，表现力和强大的命令行框架。提供了用户命令行输入和参数解析强大功能。Commander 源自一个同名的Ruby项目。[Commander.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304641a9458ec378561fe002b4aafaf5409c7e832617270508052782750b35f1ecb4) 是 [TJ](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046004e4417adb4aef5169add332a3c9f56) 写的一个帮助快速开发Nodejs命令行工具的package。[TJ](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046004e4417adb4aef5169add332a3c9f56)这货是Nodejs社区里非常知名的高产作者。方便的定义option包括option的描述和其回调函数    


## 特性
Commander的方便之处在于：  

自记录代码、自动生成帮助、合并短参数（“ABC”==“-A-B-C”）、默认选项、强制选项​​、命令解析、提示符

## API

`Option()`: 初始化自定义参数对象，设置“关键字”和“描述”  
`Command()`: 初始化命令行参数对象，直接获得命令行输入  
`Command#command()`: 定义一个命令名字  
`Command#action()`: 注册一个callback函数  
`Command#option()`: 定义参数，需要设置“关键字”和“描述”，关键字包括“简写”和“全写”两部分，以”,”,”|”,”空格”做分隔。  
`Command#parse()`: 解析命令行参数argv  
`Command#description()`: 设置description值  
`Command#usage()`: 设置usage值  

参考：[官方文档例子](http://u.720life.cn/g/f7796fc5eee3148e2180fd3127e1641b13880f175ca8c71fd408bacd99194e63)  

## 安装
安装commander

```
sudo npm install commander
```

## Option

内置选项Built-in option，Commander 会为程序提供给一个默认的 `-h` option。

```js
program
  .version('0.0.1')
  .option('-r, --resume', '简历');
program.parse(process.argv);
```

其中parse函数是处理定义的option和sub-command， 解析命令行参数并触发相应的回调(下文会说)。

```shell

./bin/wcj.js -h
## 输出下面内容
  Usage: wcj [options]

  Options:

    -h, --help     output usage information
    -V, --version  output the version number
    -r, --resume   简历
```

可以看到默认就有个 `-h` 参数，传入后会输出 `wcj` 命令的帮助信息。  

## Custom option

为 `wcj` 命令增加一个 `option`，展示说明是我的简历。

```
program
  .version('0.0.1')
  .option('-r| --resume', '简历');
program.parse(process.argv);

if (program.resume) {
    console.log('简历 - '
        + '这个是我的简历！'
    );
}
```


`option()` 接收[四个参数](http://u.720life.cn/g/f7796fc5eee3148e2180fd3127e1641b13880f175ca8c71fd408bacd99194e6390c15e0616f83d9eb91ef2ebbc168c5b4acc717d0af62ad312e5d871024bc946)

- 第一个参数中，`-r` 为`short option`，`--resume`为对应的`long option`, 二者的分割符是`|`或者`,`。在命令行里使用时，这两个是等价的。 区别是后者可以在程序里通过 `program.resume` 的方式取到该 `option` 的值，此处 `option` 的值为 `bool`，也可以为字符串。
- 第二个为 `option` 描述, 会在 `help` 信息里展示出来
- 第三个参数为回调函数
- 第四个参数为默认值

## Unknown option

当接收到未定义的option时，程序会自动抛出错误

```shell
./bin/wcj.js -h

## 输出下面内容
error: unknown option '--res'
```

Commander同时提供了api来取消这个自动报错机制， `.allowUnknownOption()`。 

```js
#!/usr/bin/env node
program
    .allowUnknownOption()
    .version('0.0.1')
    .option('-r, --resume', '简历');

program.parse(process.argv);
//省略一些细节...
```

## Option types

Command支持以下两种类型的option： `required` 、 `optional` 和 `bool`

### required 和 optional

在option的第一个参数里, 除了`short`，`long option`，还可以指定option类型，分隔符也是`|`和`,` 其中

- ` ` required参数，使用时后边必须跟参数值, 否则程序会报错
- `[db]` optional参数，后面可以选择是否跟参数值

```js
#!/usr/bin/env node  
var program = require('commander');
program
    .allowUnknownOption()
    .version('0.0.1')
    .option('-r, --resume', '简历')
    .option('-l, --language  ', '这个语言是我擅长的语言。')
    .parse(process.argv);

if (program.resume) {
    console.log('简历'
        + '-'
        + '这个是我的简历！'
    );
}

if (program.language) console.log('language: 我擅长的语言`' + program.language + '`');
if (program.database) console.log('db: 我擅长的语言`' + program.database + '`');

```

看下效果

```shell
./bin/wcj.js -l python
## 输出
language: 我擅长的语言`python`
db: 我擅长的语言`MySQL`

./bin/wcj.js -l
## 输出
  error: option '-l, --language  ' argument missing
```

### bool

选项值为布尔型, 像上面的`--date`, 默认是`false`，当使用此参数时，`program.date` 为`true`, 否则为`false`   

`bool`型`option`有个变种，当`long option`定义为`no-*`时默认值为`true`, 将

```js
var program = require('commander');
program
  .option('-d, --no-date', 'don‘t display current date')
  .parse(process.argv);

var dt = new Date();
if (program.date) {
    console.log(dt.getFullYear()
        + '-'
        + (dt.getMonth() + 1)
        + '-'
        + dt.getDate()
    );
}
```

不带-d 参数时, 参数的默认值为true

## Automated --help

Commander会根据配置的option，sub-command等信息，自动生成help信息。

### Custom help

可以通过监听--help事件来输出额外的帮助信息，如下面给fe命令添加了一些examples

```js
// must be before .parse() since node's emit() is immediate
program.on('--help', function () {
    console.log('  自定义的例子:')
    console.log('')
    console.log('    输出命令  wcj -d')
    console.log('    输出命令  wcj -l python')
    console.log('')
})

program.parse(process.argv);
```

效果如下：

```shell
./bin/wcj.js -h

  Usage: wcj [options]

  Options:

    -h, --help             output usage information
    -d, --no-date          display current time
    -l, --language    这个语言是我擅长的语言。
    -b, --database [db]    该数据库为我最擅长数据库

  自定义的例子:

    输出命令  wcj -d
    输出命令  wcj -l python
```

## 像git风格一样的命令

[列子源码](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304686e3d7a951d97bffd6c0f389bf91fbd4c3268299b913bee020bd96ce258de1b130d02f248ded9f4dfae323f05bb49f0e7ba4e6d1f6d1cc55c7b7ac7c52a174a2)

```js
#!/usr/bin/env node 
var program = require('commander');
var appInfo = require('./../package.json');

program
    .version(appInfo.version)
    .usage('这里是我私人玩耍的命令哦！[options]  ')

//像git风格一样的子命令
program
    //子命令
    .command('resume  ')
    //短命令 - 简写方式
    .alias('rs')
    //说明
    .description('这里是我的简历详情！')
    //resume的子命令
    .option("-n, --name  ", "输出我的名字")
    //注册一个callback函数
    .action(function(cmd, options){
        var nm = typeof options.name=='string'?options.name:""

        console.log('resume "%s" 使用 %s 模式', cmd, nm);
    }).on('--help', function() {
        //这里输出子命令的帮助
        console.log('  Examples:');
        console.log('    运行方法：');
        console.log('    $ ./bin/wcj.js resume ss -n aaaaa');
        console.log('    $ ./bin/wcj.js resume ss');
        console.log();
    });

program.parse(process.argv);
```

上面实例运行输出方式

```shell
$ ./bin/wcj.js resume ss -n aaaaa

#输出：
resume "ss" 使用 aaaaa 模式

$ ./bin/wcj.js resume ss
#输出：
resume "aa" 使用  模式
```

## 事件监听

命名多少个命令就监听多少命令，`--help` 为默认监听事件。

```shell
program.on('--help', function(argv,test){
    process.exit(1);
});
```

# 阅读参考

第一个小实例看了很多文章，记录一下，感觉非常简单的样子。

- [用node.js开发命令行工具](http://u.720life.cn/g/dc03aee31ab56931a51330b09409573f09070494068f412702bb11507134bdf7bf1e08114a35a0ef57a5b0260e2d93ba90e080da299c6e438115104f416b2ce1)
- [Command-line utilities with Node.js](http://u.720life.cn/g/47abc0d8fb629605c572593118d07f9d095bf3ee74ee6425cbc2a015675d08379b2ff7378397e49c103b49a17e71f48515d58f5e5e7b7155e5721c89c12f24a8)
- [使用Node.js创建命令行工具](http://u.720life.cn/g/f93303826988967b05797c533887df2a5472e731493f28456791d1b7b582b83803dd3f16a371b2fa208a7ba76859f45ec1834f8f06d9e950babe0bcdcda2b6ac)
- [commander.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304641a9458ec378561fe002b4aafaf5409c7e832617270508052782750b35f1ecb4)
- [commander.js例子](http://u.720life.cn/g/f7796fc5eee3148e2180fd3127e1641b13880f175ca8c71fd408bacd99194e63bbd50f74848b6b04e8172c696afed8ec)
- [node-optimist](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046486022e517727a896c612413d8a5bc98335bc5e932c8b381488d34f88c28b870)





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

[文章源地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3f3774eb3101754b788f60ddd954b400f899b5a0ce6975ece9a6ff22b941ca4890f88f505e62966af6c0f506e4e28e09)