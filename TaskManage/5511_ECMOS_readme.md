# ECMOS安装
###使用install安装
执行路径http://you web site/install
一路安装下去就可以


### 2017-02-20更新日志
1. 增加了外部登陆调用接口
2. 增加了外部注册调用接口
3. 修改了导入已有类的兼容性问题
4. 登陆接口:格式如/?app=api&appid=[管理员后台填写的登陆appid]&appkey=[管理员后台填写的登陆appkey]&uid=[用户的email|用户的mobile|用户的code|用户的username]&act=[userLogin|emailLogin|codeLogin|mobileLogin]
5. 注册接口：接口为/?app=api&appid=[管理员后台填写的登陆appid]&appkey=[管理员后台填写的登陆appkey]&username=&email=&mobile=&password=&act=register
 * 其中username,email,mobile,不能全为空

### 2016-12-04更新日志
1. 修改了调试模式的开启条件需要config.inc.php中的DEBUG_MODE
- 增加了新的调用方式SL(),与LM()是为了与新的模块兼容，SL()默认调用/includes/libraries/zllib/下的文件夹或目录，如SL('member'),将调用/includes/libraries/zllib/member.lib.php或/includes/libraries/zllib/member/member.lib.php系统采用自动载入，LM()与&m('');载入效果是一样的，不过，LM()可以直接使用比如LM('goods')->find($where);


### 2016-12-04紧急更新日志
1. 增加了防注入插件
2. 修改了团购的注入漏洞
3. 防注入插件需要在商城后台插件处开启
4. 修改了商品发布处的因为高度限制产生的部分信息被隐藏

### 2016-10-13 更新记录
1. 修改了短信调用接口,短信0.055元一条。


### 2016-09-17 更新记录
1. 后台管理员界面index.js错误引起的更新弹层不显示。
2. 修改了升级功能，调用了系统说明，以及当前版本的功能说明显示。
3. 增加网银支付接口
4. 增加银联支付接口
5. 增加首页按区域显示，或筛选功能。
6. 修复SQL安装之后文件未删除引起的后续安装出错

### 2016-09-16 更新记录
1. 验证码不能显示的BUG，由于宽高数值的错误引起的。
- 修改了双核浏览器的跨内核登录兼容功能。
- 修改了后台在低版本IE的不兼容问题，去掉了部分ICON，改成文字，以便兼容低版本IE
- 修改了首页在低版本IE的兼容问题。
- 增加注册关键词过滤插件，可以过滤注册的关键词，不允许某些词语被注册。需要在后台/扩展/插件处开启
- 增加了匿名登陆功能
- 修复了手机版登陆时grade表错误


### 2016-09-02更新记录
1. 更新了升级功能不能自动连接服务器的bug
2. 增加了管理员独立密码功能，后台管理员密码使用新的算法，以及不同于前台的密码体系，让ECMALL本身的因为管理员与用户帐号存与一起造成的可能密码泄漏或易猜测问题，得到解决

###2016-8-28修复内容
1. 修复了安装后，安装时输入的密码无效的bug。
- 修复了未安装情况下的不能自动跳转到安装路径。
- 增加了两套店铺模板
- 增加在线升级功能，用户可以在线直接进行升级。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e66c4356f031a41387f2e6a5cad4cf3d525923e5a2176ab8b4bd65d3d6dc706a4e31c2fac76d5aa247566282b375d6f33)