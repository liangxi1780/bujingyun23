JeeWx, 微信管家平台，简称“捷微”.
===============
捷微是一款免费开源的JAVA微信公众账号开发平台.
===============
当前最新版本： 2.3（发布日期：20160323）

![github](http://img.blog.csdn.net/20140706133601296?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvemhhbmdkYWlzY290dA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
 平台介绍：

一、捷微Jeewx简介
-----------------------------------
Jeewx是一个开源、高效、敏捷的微信开发平台，采用JAVA语言基于Jeecg快速开发框架实现，实现了微信平台的基础功能，便于用户二次开发，支持微信第三方平台全网发布、支持微信插件开发机制，可轻松集成微信H5插件。

主要特性
-----------------------------------
* 	1、基于快速开发平台jeecg 3.4.4版本，采用SpringMVC+Hibernate4+Easyui+Jquery+Ehcache等主流架构技术
*   2、支持企业快速开发，完善的用户组织机构，报表，强大的代码生成器快速有效的提高开发效率
*   3、开源免费，jeewx遵循Apache2开源协议(Jeewx提供开源版和商业版，开源版可以免费使用，可商业，无授权问题)
*   4、支持多用户多公众号管理
*   5、详细的二次开发文档，并不断更新增加相关开发案例提供学习参考
*   6、微信功能插件化开发，更易于定制和二次开发
*   7、支持微信第三方平台全网发布
*   8、支持author2.0机制

捷微功能清单
-----------------------------------
*   1，微信公众号管理
*   2，菜单自定义
*   3，关注欢迎语
*   4，关键字管理
*   5，文本消息
*   6，图文消息
*   7，素材消息
*   8，大转盘
*   9，刮刮乐
*   10，微相册
*   11，微网站(广告位、栏目管理、文章管理)
*   12，微信消息管理
*   13，翻译
*   14，天气
*   15, author2.0支持
*   16, 微信插件机制
*   17，用户管理
*   18，角色管理
*   19，菜单管理
*   20， 定时任务
*   21，系统日志
*   22，系统监控
*   23， 统计报表
*   24，字典管理
*   25，微信公众账号第三方平台全网发布
    


【标准开发环境】

    myeclipse8.5 + jdk7 + tomcat6 + mysql_5.0.37 （注意： 不支持jdk8;）

【开发入门】

    第一步：采用Mysql手工创建数据库jeewx-os 采用UTF-8编码
    第二步：执行捷微数据初始化SQL脚本
              脚本位置：doc\db\jeewx-mysql-2.3.sql
    第三步：导入myeclipse8.5，发布项目，启动项目
    第四步：默认项目访问入口
             http://localhost:8080/jeewx/
            输入验证码，默认账号admin/123456进行登录，进入捷微管家后台。
            说明：端口号，根据自己的配置，进行修改
    第五步： 微网站默认站点地址修改
             配置文件：jeewx-os-framework/src/sysConfig.properties
       	     修改说明：domain={http://localhost:8080/jeewx}，把domain修改成项目访问的地址，如果服务器端则把localhost修改成域名或者ip

【微信开发经验分享】

    1. jeewx本地开发无法与微信后台交互，jeewx需有外网IP，才能与微信后台交互
    2. 微信 accesstoken会有2个小时的有效期，jeewx超过2个小时会自动获取

【捷微对接微信公众号】

    [1].Jeewx需要部署有外网访问的 服务器上，例如访问地址：http://www.jeewx.com/jeewx
    [2].修改jeewx 系统默认域名domain    
       	配置文件：jeewx-os-framework/src/sysConfig.properties   
         domain={www.jeewx.com/jeewx} 需要与jeewx部署访问地址一致
    [3].捷微后台创建一个微信公众号，配置上对应的参数{公众微信号\公众号Token\原始ID\APPID\APPSECRET} 
    [4].捷微后台创建公众号成功后，配置微信转发请求地址
                 登录微信后台：https://mp.weixin.qq.com
                 点击->开发->配置（修改服务器配置）
                  填写：URL  = {http://www.jeewx.com/jeewx/wechatController.do?wechat}
						TOKEN = {需要与捷微后台配置TOKEN保持一致}
						EncodingAESKey = {随机生成}
				点击提交，微信显示提交成功，表示微信已经于捷微后台联通，提示错误说明配置不正确。

【捷微演示公众号】 

    官方公众号："JEECG"  "H5互动汇"
![github](http://img.blog.csdn.net/20160323155143399?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323154916164?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")

捷微技术交流
==========

* [1].技术论坛 :  [www.jeecg.org](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb32316db2e8cce2c772ae0d20db42a78d5d7)
* [2].QQ群 ：289709451
* [3].捷微开发资料 :  [Jeewx视频](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb3235c7498b3747e0b953f7e153f50db9c743482c7d8c5e9c3159ce0b5ae6f4df6ffae0d019111a675f87ff925553943b4e3cec7eba8d2caba6f45cbed978a07fddc)  、[Jeewx捷微管家操作文档(开源版)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a47ce8905daa5af1296d2963974eb062f3b39c01b15e2888a5f5090f2f4ff4cd0ef0203b3c2cc6c7cbb9dc405949b814fa)
* [4].技术博客 ：[地址](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a47ce8905daa5af1296d2963974eb062f37cfd41612522b5fc7a9c43adac434f38)
* [5].捷微商业支持 : [捷微商业用户指南](http://u.720life.cn/g/be8a8b9e0e5550eba55db030fde3f809e62ff8569c9c78fc55a6bf7443467333510f281b0337a0a4e9f8b064c968ac23910e9343150eac7ceffa90285aeaaf96) 、[捷微商业注册地址](http://u.720life.cn/g/777ad498d3808edff841aa7bd3054dfd773df2573410e36a071e6b5f1809e72f)  	    、[捷微H5活动营销平台注册地址](http://u.720life.cn/g/1c70cdd57616696ce9968d293fad5968e1056d612e0e94eae2c20b1e80d7bbd2)
* [6].其他开源支持 ： 
        [Jeewx-api极速SDK](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d08b36d58a29f0bb52a854088138891367a858a51f6a13af01cf61f2271755b36) 、
        [H5活动平台](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844de37e13957c6d6f730cca0068f1e052b1cf7692db0bd267012c4087183d4ae421)


![github](http://img.blog.csdn.net/20160323152356873?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323152508827?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323153059001?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323153104923?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323153117501?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20160323153122251?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20140706133652718?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvemhhbmdkYWlzY290dA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")
![github](http://img.blog.csdn.net/20140706133543390?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvemhhbmdkYWlzY290dA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeewx")


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7523b4de0f32818ce9b2be89a2da5a44931e1a1aef93dcbd167b0ec7a931c3dcf4cb180437fc2e5c9c009d505ea3bfb8)