 

# 文言 wenyan-lang

[http://wenyan-lang.lingdong.works](http://u.720life.cn/g/24abdec631466e975d2c49aaf94dbf206f2cd57f9b213128702a139ccbea73bc02d623ad0470b6957144360c194d26c4)

文言文編程語言。A programming language for the ancient Chinese. [Try it online.](http://u.720life.cn/g/24abdec631466e975d2c49aaf94dbf206f2cd57f9b213128702a139ccbea73bce94f65047f5d72e9636fb137e28a6211)

![](screenshots/screenshot01.png)

## 序

> 夫[唐](http://u.720life.cn/g/dbf1195f8a53209e138d24666db06636670e6934e89047844f9d28761d5ffccba4f3dd7424baf14256dd57d6ff327847)、[虞]https://en.wikipedia.org/wiki/Emperor_Shun ，似所未有。此誠非文脈之所以傳，文心之所以保。[嗟予小子](http://u.720life.cn/g/1028018179db5a053426c09c0ce1d36af8dca85d7fd759db1f265b011fd38916b93205838e04b12ccf088203ae6bb7f13cc33f1fa423a4f1a873a576afe1af260d8d585a73b0b0c772dbe9612421054a)


## Helloworld

Wenyan:

```
吾有一數。曰三。名之曰「甲」。
為是「甲」遍。
	吾有一言。曰「「問天地好在。」」。書之。
云云。
```
Equivalent JavaScript:

```JavaScript
var n = 3;
for (var i = 0; i    : Give a string instead of a file (default: `')
--exec    -x   : Execute output (default: `false')
--inspect -i   : Interactive REPL (default: `false')
--lang    -l    : Language: js/py (default: `js')
--log           : Log file (default: `/dev/null')
--output  -o    : Output file (default: `/dev/stdout')
--roman   -r   : Romanize identifiers (default: `true')
```
Try building the included examples first, e.g.:

```
./build/wenyan.js examples/helloworld.wy -o helloworld.js
```

#### Building platform-specific binaries

- Clone the repo
- `npm install`
- `npm run make_cmdline`

The macOS, Windows and Linux binaries will be in the `./build` folder.


### [The online IDE](http://u.720life.cn/g/24abdec631466e975d2c49aaf94dbf206f2cd57f9b213128702a139ccbea73bce94f65047f5d72e9636fb137e28a6211)

![](screenshots/screenshot02.png)


## Syntax Cheatsheet

A context-free grammar description is under construction. Meanwhile, please check the cheatsheet below, or look into `src/parser.js` to learn about the syntax. Be sure to check out the examples from the online IDE too!

### Variables

| wenyan | JavaScript |
|---|---|
|`吾有一數。曰三。名之曰「甲」。` | `var a = 3;` |
|`有數五十。名之曰「大衍」。` | `var dayan = 50;` |
|`昔之「甲」者。今「大衍」是也。` | `a = dayan;` |
|`吾有一言。曰「「噫吁戲」」。名之曰「乙」。` | `var b = "alas!";` |
|`吾有一爻。曰陰。名之曰「丙」。` | `var c = false;` |
|`吾有一列。名之曰「丁」。` | `var d = [];` |
|`吾有三數。曰一。曰三。曰五。名之曰「甲」曰「乙」曰「丙」。` | `var a=1,b=3,c=5;` |


### Control

| wenyan | JavaScript |
|---|---|
|`若三大於二者。乃得「「想當然耳」」也。` | `if (3>2){ return "of course"; }` |
|`若三不大於五者。乃得「「想當然耳」」。若非。乃得「「怪哉」」也。` | `if(3<=5){return "of course"}else{return "no way"}` |
|`為是百遍。⋯⋯ 云云。` | `for (var i = 0; i < 100; i++){ ... }` |
|`恆為是。⋯⋯ 云云。` | `while (true) { ... }` |
|`凡「天地」中之「人」。⋯⋯ 云云。` | `for (var human of world){ ... }` |
|`乃止。` | `break;` |


### Math

| wenyan | JavaScript |
|---|---|
|`加一以二。` | `1+2` |
|`加一於二。` | `2+1` |
|`加一以二。乘其以三。` | `(1+2)*3` |
|`除十以三。所餘幾何。` | `10%3` |
|`減七百五十六以四百三十三。名之曰「甲」。` | `var a = 756-433;` |
|`夫「甲」「乙」中有陽乎。` | `a \|\| b` |
|`夫「甲」「乙」中無陰乎。` | `a && b` |


### Containers
Arrays are 1-indexed.

| wenyan | JavaScript |
|---|---|
|`吾有一列。名之曰「甲」。充「甲」以四。以二。` | `var a = []; a.push(4, 2);` |
|`銜「甲」以「乙」。以「丙」` | `a.concat(b).concat(c);` |
|`夫「甲」之一。` | `a[0]` |
|`夫「甲」之其餘。` | `a.slice(1);` |
|`夫「玫瑰」之「「名」」。` | `rose["name"]` |
|`夫「寶劍」之長。` | `sword.length;` |


### Functions
| wenyan | JavaScript |
|---|---|
|`吾有一術。名之曰「吸星大法」。是術曰。⋯⋯是謂「吸星大法」之術也。`|`function f(){...}`|
|`吾有一術。名之曰「六脈神劍」。欲行是術。必先得六數。曰「甲」。曰「乙」。曰「丙」。曰「丁」。曰「戊」。曰「己」乃行是術曰。⋯⋯是謂「六脈神劍」之術也。`|`function f(a,b,c,d,e,f){...}`|
|`吾有一術。名之曰「翻倍」。欲行是術。必先得一數。曰「甲」。乃行是術曰。乘「甲」以二。名之曰「乙」。乃得「乙」。是謂「翻倍」之術也。`|`function double(a){var b = a * 2; return b;}`|

## Renderer

`src/render.js` can render a wenyan program into an image that resembles pages from historical printed books. It can also parse the resultant SVG file back to the original program. Below is the rendering of the Universal Turing Machine written in wenyan:

![](screenshots/screenshot03.png)


## Contributed Tools

- [Plugin for VSCode](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462b4d73bfd65a8b5f2560ae554454e8f49fffaefcbf6bce4a2e377445ea9d40ff) by [antfu](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304696ea07cd46a0c9dd61405b971c832ec8)

## Test

Install Mochajs

```Shell
npm install --global mocha
```

Go to src/test folder, run

```Shell
mocha
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec6e1afad7b00de66e6714f87a2d8fb310edb4fea42292234002fbc20844e3880a769c01470a240c2ef4370a4c48da221)