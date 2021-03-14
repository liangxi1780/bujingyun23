# 项目说明

## 简介
将思维导图运用到团队协作中, 并提供在线的思维导图绘制功能.

## 相关技术点
* 项目后端采用[Laravel](http://u.720life.cn/g/08fa78e7e6e90c7b9927de4854cdce143b5450f56cd673ff5c0f562ddd84a800) 4.2构建
* 前端使用[Twitter Bootstrap](http://u.720life.cn/g/e23be2821e5181a1a46a005bc6e93d9defdf99ca32552b6780c0e93b692ebec7)作为UI基本构件，[AngularJS]https://angularjs.org
* AngularJS与Laravel采用REST风格的数据交互
* 思维导图的在线绘制基于[RaphaelJS](http://u.720life.cn/g/140ac4aa8794cc0e83d1111612bd3e75ef123b47b578b1ffb9c528154853822d)（一款使用SVG W3C标准的JavaScript矢量图形库)


## 初始化步骤
**为成功初始化，必须安装[Composer](http://u.720life.cn/g/3f9c4b3c4d80694fc0e23fabd7c88654a193fc83266bd5e5e0b41a1222e88a87)、[Bower]http://bower.io

在命令行/终端输入下列指定，或进行相关操作：

* `composer install` : 此命令用于通过Composer安装Laravel框架本身，以及项目所依赖的第三方类或本项目所延伸的子项目
* `npm install` : 此命令用于安装npm包，描述如下：
    * grunt　与　grunt-* 用于构建前端的CSS文件和JS文件，如想部署项目必须安装
    * karma 与　karma-* 用于前端的自动化测试，如不进行相关开发则无需安装
* `bower install`　：　此命令用于通过bower安装前端用到的第三方类库或本项目所延伸的子项目
* `grunt` : 此命令用于执行Ｇrunt，用于构建生产环境所用的各类前端文件
* 设置数据库链接，可以参考 [这里](http://u.720life.cn/g/fa707741c088aa9db14c6132b8153f0413086a7b0b705853c9616c3c2d765f41b6170931187d58ddea123e6301676a1232de0253aa4c412420d5ce4c67952ec1) 和 [这里](http://u.720life.cn/g/fa707741c088aa9db14c6132b8153f0413086a7b0b705853c9616c3c2d765f4158157676d384caae4136167a6a1533f55e29241cc93d0ae49065b424315e5ce6a2deb7441398a42c5a9fb0687c9d593d) 进行配置
* 执行数据库迁移： `php artisan migrate`

## 备注
* 为避免冲突和保护开发者信息，请在命令行中使用下列指令（该指令将假设文件无改动，只能应用于版本库中已跟踪的文件）：
  * 假定不改动， 以设置database.php为例：`git update-index --assume-unchanged app/config/database.php` 
  * 取消设置： `git update-index --no-assume-unchanged app/config/database.php`
* 更多相关信息，请参考 [项目Wiki](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844da0407163c8805e3401e942938bade6ecee82acdbdadfc82d72de42aab8ab3e95157b97023a3592449651f7900334b901)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7fc411c505079acaf1061cea865c00edc9151a668a9489f81c27622ac812efb433cebf4b9213eed7cc0ae6fe9cfd6ef1)