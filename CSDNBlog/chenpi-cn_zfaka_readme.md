# ZFAKA发卡系统(本系统基于yaf+layui开发)

>**郑重申明：本项目为开源程序，仅做技术交流使用**

>演示地址：https://faka.zlkb.net/

>永久免费、绝对开源，不支持特殊定制，欢迎提供各种需求和意见与建议。


# 一、系统介绍
>包含自动/手工发卡功能，有会员中心和后台中心。

1.1 会员模块
* 默认情况下，不支持注册，当然后台可以开放注册；

* 注册成会员可查看历史购买记录。
	
1.2 购买模块
* 支持自动发卡和手工发卡模式；

1.3 后台模块
* 包含设置模块、订单模块、商品模块、配置模块、卡密导入导出等；后台可对首页模版进行切换，验证码、注册、登录、找回密码进行后台开关控制；
	
1.4 支付渠道
* 官方接口－支付宝当面付

* 官方接口－支付宝电脑网站支付

* 官方接口－微信扫码支付

* 官方接口－微信H5支付

* 官方接口－PayPal支付

# 二、系统部署
>**友情提示：很多人安装失败都是因为没有仔细看所有的wiki，所以请仔细看完所有的wiki再操作**

>**友情提示：感谢佰阅部落友情提供Docker版 [直达链接](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f0cc031f9f6d8c21e760db7ef8c30593fa2fcf40f618dad474f3ff44a18eeefc)**

## 2.1 环境安装

### 2.1.1 lnmp环境
>参考：[lnmp环境中如何进行配置](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c206c856d6cac752bd70bc44d346a4e6c5cfde3ff3cb2443bd2b40a8e6b25818ef6f32ff20c4c3c641ea419ae09fb45105ab2cb8298c17257f7badaa86a803e9c3fc23f3c663a32d7e4a95eadf6619ab6f550628f1d2614a1d1d27517f1622cc7).

### 2.1.2 宝塔环境
>参考：[宝塔环境中如何进行配置](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c1c5468c2df75481a42b65404fb90017ed7f9ed11caa4bfe5c0aec15acef0d20edfb28055b4e9de5a7f07fe21ea21a96c818430db97143d46f08d427222ee8ac9c9265815469881545378b82b45ba39e9d8eb3124ae68b98e7741220cd6683c11d05bddc46893d91da8a6c6513f56c031).

### 2.1.3 YAF安装
>参考：[lnmp环境中如何安装yaf](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c206c856d6cac752bd70bc44d346a4e6c5cfde3ff3cb2443bd2b40a8e6b25818ef6f32ff20c4c3c641ea419ae09fb4510b5791d3c0a9a0102837745fc951e958a8b0a06d109e4d8d13840e61cc743051e).

>参考：[宝塔环境中如何安装yaf](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c1c5468c2df75481a42b65404fb90017ed7f9ed11caa4bfe5c0aec15acef0d20edfb28055b4e9de5a7f07fe21ea21a96c818430db97143d46f08d427222ee8ac91771d7603612ac98cde24622c00496872079981dcb42895743931f2ddabc2646).

### 2.1.4 rewrite配置
>参考：[rewrite配置](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c078938af24e4e14f511d017c389620bae5b083debc693f3b45ddc11c37551b3dc16fdec69c6754521eb526a6bce4e552).

 #####################################################  

## 特别补充说明：yaf的环境安装比较麻烦，需要注意一些问题；

* 务必：配置nginx vhost中root路径一定要加上public目录，例如:  /alidata/wwwroot/faka.zlkb.net/public;

* 务必：配置nginx vhost中一定要添加rewrite规则

* 务必：取消防跨站攻击(open_basedir)

* 务必：注意nginx环境下path_info的配置(记的要取消)

* 务必：YAF配置开启命名空间 yaf.use_namespace=1

* 务必：项目运行给站点用户权限

* 建议：mysql数据库配置时建议这样操作参考：https://zlkb.net/302.html

 #######################################################  

## 2.2 系统安装
>参考：[系统安装指南](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c78daab0600cc56d17e09b873bb5f501fe5e41d5c5fa05be1a0959a546172abbad662c9ac9867ef27e84620627fa66223f3a025b9dc971f45b7f0c0745ff8c1cf).

### 2.2.1 下载代码
>测试版：
 git clone https://github.com/zlkbdotnet/zfaka.git [这是最新测试版]  

>稳定版：请访问这里下载：https://github.com/zlkbdotnet/zfaka/releases

### 2.2.2 修改配置文件名
>新增：需要进入系统conf目录下，application.ini.new修改为 application.ini

### 2.2.3 配置目录权限

* /conf/application.ini 配置文件，可读可写

* /install  安装目录，需要可读写

* /log      日志目录，需要可写

* /temp     缓存目录，需要可读写

### 2.2.4 直接访问安装

### 2.2.5 安装计划任务crontab模块,配置定时计划,用于定时发送邮件
* lnmp环境计划任务crontab的部署
>参考：[lnmp环境中如何部署计划任务](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c206c856d6cac752bd70bc44d346a4e6c5cfde3ff3cb2443bd2b40a8e6b25818ef6f32ff20c4c3c641ea419ae09fb45106387da3bd33faf867510c11f9c50245de235349893fdad342db53c1ae61e8d7cacacfe35309a0218e43a4d8afa9dd1f2ccad029a2f350a9f538eb992057e7036)

* 宝塔环境计划任务crontab的部署
>参考：[宝塔环境中如何部署计划任务](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c1c5468c2df75481a42b65404fb90017ed7f9ed11caa4bfe5c0aec15acef0d20edfb28055b4e9de5a7f07fe21ea21a96c818430db97143d46f08d427222ee8ac9d618543ed5bf22f50fe1dbea046d292fc0687eccc0461282b0e104052e0d3ee5909312c44de6435aaddc0d97687ca9b7338f153335a6495b645e7112431cfbb0).

### 2.3 系统配置
>参考：[系统配置指南](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c78daab0600cc56d17e09b873bb5f501f574ada4c33d4cfc56802b01b16ffa4c46f543d5185272051113ab6dfba688c2edec49edcc6621798eed05f0b4ef353c2)

### 2.4 后台安全
>参考： [后台地址安全增强处理](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c78b3ed2fd06c92c176d5194d32c08d14a642b0264a2457de3a123f244e06ec58cbe35dd886a22f567d242261757fe6034e8e05fca161c1c931c9748fd386fcfd275dc5030e6400ea7944eacd2ea02716959a18961df380f0fe72bdf87844a08c121867c26260e7f79e635914890948a5)

# 三、系统升级
> 参考：[系统如何升级？](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c78daab0600cc56d17e09b873bb5f501fe5e41d5c5fa05be1a0959a546172abbab4fb6cd64618f01b6d4e458dd3f0a7184e0c46ad8e4c978ff6df2abbb9ad5439a3425467e9bc350499bbb70fd6ec7d69)

# 四、BUG与问题反馈
* 相关问题QQ交流群：701035212 [收费群]
   
# 五、推广时间
* 全国IDC行业精英群:572511758

# 六、捐赠&打赏
>捐赠名单：[查看名单](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046031c7bccd03c46a8faea9f691967be4c031921109ff877beeca348f8083c2d1d2dbb45bcff0308e00eeff966dc7a643ab4f9f2bfb0c355825f182aa792ddf1d6)

![1](https://github.com/zlkbdotnet/zfaka/blob/master/public/res/images/pay/supportme.jpg)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee93da047da6c38f5b8a2c52926d59feb91b92dc73bf3c73f380d56d508453cc998985a7ae0b98d172e17f9ea702cf3aa)