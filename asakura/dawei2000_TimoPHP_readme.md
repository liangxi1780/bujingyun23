## TimoPHP

一个简单、快速、规范、灵活、扩展性好的PHP MVC+框架，主要用于API接口开发（前后端分离已是常态）

官网：http://timo.gumaor.com/

文档：http://timo.gumaor.com/document/

## 我们的目标

做一个轻量级并支持大型应用开发的PHP框架

## MVC+模式

除了M层，我们还可以根据项目实际情况增加层，比如基础层（Base）业务逻辑层（Business/Logic）服务层（Service）策略层（strategy）等等

## MVVC模式

把MVC模式的V（视图）分成了视图模型层和视图层（也可以说是模版层），当然，视图模型层是可选，没有的话就是经典的MVC模式

## 特点
    1、PHP5.6+（建议PHP7）
    2、PSR标准
    3、轻量级，扩展灵活
    4、自定义异常处理，如404
    5、原生模版解析
    6、支出视图组件
    7、模板支持多主题、layout（布局）
    8、写app接口还是挺爽的
    9、加入对cli模式支出，用来写服务、定时脚本挺好的
    10、增加依赖注入服务容器，实现组件之间的松耦合
    11、支持数据库读写分离设置，可具体到某张表
    12、支持控制器分组路由，降低控制器复杂度
    
## 目录结构

```
/data
  |-TimoSNS                         项目目录(自己项目名称，比如用TimoPHP开发的社区应用，叫TimoSNS，自定义)
  |   |-app                         应用目录
  |   |   |-cli                     命令行
  |   |   |-h5                      移动端
  |   |   |-min                     小程序
  |   |   |   |-controller          控制器目录
  |   |   |   |_config.php          项目配置文件
  |   |-business                    公共业务逻辑
  |   |-cache                       运行时缓存目录
  |   |-middleware                  中间件
  |   |-provider                    服务提供者目录
  |   |-component                   组件目录
  |   |-config                      公共配置目录
  |   |-lib                         自定义类库
  |   |-logs                        日志目录
  |   |-model                       模型目录
  |   |-public                      WEB目录（对外访问目录）名称自定义，如wwwroot、public
  |   |   |-min                     小程序
  |   |   |   |_index.php           小程序入口文件
  |   |-send                        推送（微信、小程序、android、IOS）
  |   |-service                     公共服务目录
  |   |-task                        异步任务
  |   |-vendor                      composer安装类库目录
  |   |-bootstrap.php               整个项目的启动文件
  |   |_composer.json
  |-TimoPHP                         框架，和项目在同一级目录
 ```
 
## 基本骨架
 
 https://gitee.com/tomener/timo-skeleton
 
 通过这个可以快速上手使用TimoPHP开发api
 
## 参考项目
 
 TimoPHP官网 http://timo.gumaor.com/

## 新建一个项目
```
cd TimoPHP
php bin/timo.php create project_name(项目名称) application_name(项目下应用名称)
```


## 入口模式

##### 多入口
一个应用一个入口，默认

##### 单一入口
所有应用共用一个入口



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e859e3727421e5ffaa051cb376f64e78eb3877fec95320eb9607b1e18bc87a69bacfceb236231bb9572e04e0bafd5c4d0)