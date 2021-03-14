# gharry

为 [courser](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304645a2fa1a93966ab91972f3fb9af6d2ab5500485a97b84b726a9dbbd8383a12cd) 而写的自动重载工具,
    基于 nodejs `fs.watch`, 文件更改自动重载应用,适用所有 swoole 程序


### install
`npm install gharry`   

or `npm install gharry -g`

### get start
config:
```
{
  "watch": ".", // listen dir string or array
  "script": "demo/index.php", // 
  "language": "php", // execute file
  "ignore": ["node_modules"] // ignore string or array
  "safe": "true" // safe relaod server
  "args": {
    "--env": "dev"
  }
}
```
- watch 监听目录，字符串或者数组
- script 执行脚本 默认 index.js
- language 语言 默认 node
- ignored 忽略的目录 字符或者数组
- safe 是否安全重载程序，默认为 true， 设为 false 时每次更改将强制杀掉程序再重启
- args 命令行参数 如执行 php index.php `--env dev` 对应 args => { "--env": "dev" }


`gharry -c gharry.json` 

`gharry --help`





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2e08c102e21910c9726e9b399fdb25213578508e1fada121368787a2b385132c694a1ae1ea6a735e5901597e428603d8)