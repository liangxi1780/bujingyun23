[![码云Gitee](https://gitee.com/binary/weixin-java-mp-demo-springboot/badge/star.svg?theme=blue)](https://gitee.com/binary/weixin-java-mp-demo-springboot)
[![Github](http://github-svg-buttons.herokuapp.com/star.svg?user=binarywang&repo=weixin-java-mp-demo-springboot&style=flat&background=1081C1)](https://github.com/binarywang/weixin-java-mp-demo-springboot)
[![Build Status](https://travis-ci.org/binarywang/weixin-java-mp-demo-springboot.svg?branch=master)](https://travis-ci.org/binarywang/weixin-java-mp-demo-springboot)
-----------------------

### 本Demo基于Spring Boot构建，实现微信公众号后端开发功能。
### 本项目为WxJava的Demo演示程序，更多Demo请[查阅此处](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046201a511e2ba300ebaea50f02340949bcf9c6e08723baa69a38ac189dcb884c14833fe9bbd023a567a452befb82a6762d)。
#### 如有问题请[【在此提问】](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466773a9e9b47c34d795f0d6dbfac28a3ca1874422be19a5e1a618ec31ec00ae370dbddd094203c653d14f24af0bfbe39e602f7e19059e6e7ddc0aa024717b3a4e)，谢谢配合。

 
	 
		 
			 
         
				   
         
			 
			 
				 
					 
				 
			 
			 
				 
					 
				 
			 
			 
				 
					 
				 
			 
		 
	 
 

## 使用步骤：
1. 请注意，本demo为简化代码编译时加入了lombok支持，如果不了解lombok的话，请先学习下相关知识，比如可以阅读[此文章](http://u.720life.cn/g/408fb60b53d11d245635ad5e8e8cd697fae83842e2e75528f54314d215518c913fe08db285a0f217e685906cb1b6fab7e845894118225fb4d0419105b40f4417)；
1. 另外，新手遇到问题，请务必先阅读[【开发文档首页】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046201a511e2ba300ebaea50f02340949bc907a262f0228eff0d943a43710ca43f5)的常见问题部分，可以少走很多弯路，节省不少时间。
1. 配置：复制 `/src/main/resources/application.yml.template` 或修改其扩展名生成 `application.yml` 文件，根据自己需要填写相关配置（需要注意的是：yml文件内的属性冒号后面的文字之前需要加空格，可参考已有配置，否则属性会设置不成功）；
2. 主要配置说明如下：
```
wx:
  mp:
    configs:
      - appId: 1111 （一个公众号的appid）
        secret: 1111（公众号的appsecret）
        token: 111 （接口配置里的Token值）
        aesKey: 111 （接口配置里的EncodingAESKey值）
      - appId: 2222 （另一个公众号的appid，以下同上）
        secret: 1111
        token: 111
        aesKey: 111
```
3. 运行Java程序：`WxMpDemoApplication`；
4. 配置微信公众号中的接口地址：http://公网可访问域名/wx/portal/xxxxx （注意，xxxxx为对应公众号的appid值）；
5. 根据自己需要修改各个handler的实现，加入自己的业务逻辑。
	



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed184a36e525a6757fe717937d89b7bb298576aa94a2e4a683b16bb9bdcb0697b47bc8ed550d81cb237c4ef036ca6315464efd1fa4ad00b13487b013976bcbfc3)