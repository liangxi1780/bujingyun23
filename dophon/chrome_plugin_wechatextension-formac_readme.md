
 
 
 

![platform](https://img.shields.io/badge/platform-macos-lightgrey.svg)  [![release](https://img.shields.io/badge/release-v1.9.6-brightgreen.svg)](https://github.com/MustangYM/WeChatExtension-ForMac/releases)  ![support](https://img.shields.io/badge/support-wechat%202.3.26-blue.svg)

## 声明
> 适用于Mac版的WeChat拓展功能, 由于之前大家常用的WeChatPlugin在默认分支切换成remove删库了, 坊间猜测原因, 众说纷纭, 我们不去深究了.
本着开源的精神, 我决定继续维护这个项目, 对[tk](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304649231a5927e83a617613aeb398cfa2a5)在此表示感谢!

## 最新支持版本
>  mac版微信2.3.26

## 手机端也能收到被撤回的消息
1. > 如果Mac拦截到A发送来的消息, 手机也会同步收到的这条已经拦截的消息(自己发送给自己). 目前只支持同步文字消息与图片消息, 其他类型也可以做, 但意义不大.
 
 
 

2. > 可以对同步的消息进行筛选, 以免群消息打扰
 
 
 

## 免认证登录与多开
 
 
 

## 消息防撤回
 
 
 

## 屏蔽更新
勾选"禁止更新"后, 微信检测更新的逻辑会被屏蔽掉, 包括手动"检查更新"的按钮. 取消勾选"禁止更新"后并重启微信, 则恢复原有更新检测逻辑.
 
 
 

## 懒癌版安装

 
 
 

感谢 [lmk123](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464576fa321d4d87c1847181e6fa187973)为此项目开发的懒癌安装 [Oh My WeChat](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466e74a909febfdf73430a46d870dcabf1cccc2e0e451d03a2617d4e99b0ab2384)

打开`应用程序-实用工具-Terminal(终端)`，执行下面的命令安装 [Oh My WeChat](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466e74a909febfdf73430a46d870dcabf1cccc2e0e451d03a2617d4e99b0ab2384)：

```sh
curl -o- -L https://raw.githubusercontent.com/lmk123/oh-my-wechat/master/install.sh | bash -s
```

安装完成后会自动安装微信插件，可以访问 [Oh My WeChat 的项目主页](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466e74a909febfdf73430a46d870dcabf1f7c286139027b9bdd6b4e550e2386d7c99d14b3fc6c0a7e660163125d4cef143)查看更多用法。


## 普通安装

#### 1. 确保你的Mac上已经安装了微信App.

#### 2. 下载本项目到你的电脑里, 并双击打开.
 
 
 

##### 3. 依次打开文件夹
 
 
 

#### 4. 打开你电脑中的终端工具
 
 
 
 
#### 5. 在Rely/Install.sh执行这个安装脚本
 
 
 

#### 6. 重启微信, 安装完成.

## 怎么卸载?
1. > 在Rely文件夹中找到Uninstall.sh
2. > 拖到终端工具中, 回车执行即可
 
 
 

## 感谢捐赠者
  
   
    
       EGOISTK21  
    
   
    
      CoderLineChan  

  
    
      RyanLiGod  
  
    
    
      JpacheGitHub  
  
   
    
      y451687300  
  
   
    
      imjonat  
  
   

## 更新日志
```
2019-8-07 修复联系人信息获取接口改变导致自动回复和Alfred的大面积闪退, sorry. 新增自动下载聊天高清图功能.
2019-7-26 适配2.3.26版本, 修复闪退, 屏蔽更新.
2019-7-10 修复清除空会话闪退
2019-6-28 修复消息筛选Bug, 群聊撤回同步到手机显示真实联系人昵称
2019-6-25 适配OSX 10.9
2019-6-25 消息防撤回同步到手机, 增加筛选功能, 可以只同步群聊或单聊
2019-6-19 详细安装方法
2019-6-5  修复会话多选闪退, 点击公众号类型消息闪退
2019-5-28 支持系统浏览器打开网页
2019-5-14 如果Mac拦截到A发送来的消息, 手机也会同步收到的这条已经拦截的消息, 小助手一键更新.
2019-5-10 目前更新还很不方便, 稍后会加入更加方便的一键更新.
2019-5-10 现在在最新版的微信中的多开和消息撤回是可以用的, 如果不能用, 请检查小助手的版本. 

```

## 交流QQ群
> 一群 229555512
> 二群 239049786

## 维护不易, 可以请我喝咖啡
> 算了吧, 咱逆向的都是屌丝, 哪有闲钱.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e21fad09ce4f9841b8d11a1ade5b361482b9444d3ca5b13ef458672748aae7f21da27c32678df6426e8ffa452ee0d390e69ea20a06e026db2e42a2dc9d3a73e8f)