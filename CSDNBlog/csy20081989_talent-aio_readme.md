 
  talent-aio: 让天下没有难开发的即时通讯
 

 
	  简 介 
		  talent-aio 是基于java aio实现的即时通讯框架，源于作者另一个久经考验的talent-nio框架，但在易用性、性能及代码可读性方面又远远超越了talent-nio（最好的东西才拿来分享，所以talent-nio并不会开源）。官网地址： http://www.talent-tan.com:9292 ，上面有大家期待已久的 入门文档 。同类框架有netty和mina。
	 
	
	  愿 景 
		成为即时通讯界的 JFinal框架 （简洁易用又不失灵活），并且以本框架为基础开发出众多可以开箱即用的应用。
	 
		 
	  应用场景 
		IM、实现各种网络应用层协议（如http、ftp等公有协议，也可以自定义私有协议）、实时监控、RPC等
	 
		
	  特 点 
		 
		   
			 极简洁清晰易懂的API : 无需各种折腾，只需 花上30分钟  学习helloworld 就能很好地掌握并实现一个性能极好的即时通讯应用
		   
		   
			 极震撼的性能 
			 
				 
					可同时支持 10万级 tcp长连接，彻底甩开业界当年的 c10K 烦恼
				 
				 
					每秒可收发 283万 条消息(约 80M )(windows7、i7、8g、群聊场景)
				 
			 
		   
		  
		  
		  
		   
			 极亲民的内置功能 
			 
				 
					框架层面帮你 检测心跳 (tcp server)、 发送心跳 (tcp client)
				 
				 
					框架层面支持 自动重连 (可设置重连间隔时间和重连次数)
				 
				 
					框架层面支持 同步消息 (消息发送后，等到响应消息再往下执行)
				 
				 
					框架层面支持 绑定userid (用于用户关联)、 绑定groupid (用于群聊)
				 
			 
		   
		  
		   
			天生 没有粘包问题 
		   
		  
		 
	 
		
	  案 例 
		 
		   
			某网管系统(管理数百台刀片服务器的系统)
		   
		   
			某直播平台(视频直播+聊天)
		   
		   
			某智能设备检测系统(数据采集)
		   
		   
			某物联网系统(服务端)
		   
		   
			深圳市某在线技术发展有限公司(中银联投资)：某网络安全运营支撑平台
		   
		   
			 redisx 
		   
		   
			 talent_dubbo 
		   
		   
			某移动省公司CRM业务受理消息采集平台(数据采集)
		   
		  
		   
			... ...
		   
		  
		 
	 
		
		
		
		
		
		
		

	  性能测试步骤及数据 
		 
			 
				 
				 
				 
			 
			 
				 
				 
				 
				 
			 
		 
	 




	  talent-aio产生的背景 
		 
			 2011年作者参与了中兴某刀片的网管系统开发，虽然入职才3个月，但大领导还是亲点让作者来改造原来的实时通讯模块，而且不允许使用mina。在这样的背景下，开始学习nio，改造后的系统，可管理上千个节点，消息收发速度极快，最近有和还在职的中兴同事了解过，核心代码仍然在运行，足见其稳定性，这就是后来talent-nio的雏形 
			 后来担任热波间(一个直播平台)的平台端架构师，持续优化和封装了talent-nio，使之可以支持4万TCP长连接，每秒可以收发10万条消息，当年甚至扛住了自杀式的2000人在同一房间无限点赞场景(这个消息量有多大，内行们请脑补) 
			 因为热波间架构师的角色，认识了不少业界朋友，部分朋友表达希望开源talent-nio， 以便参考借鉴，但是talent-nio在易用性方面做得还不是很理想，开源出来的话要么无人问津要么就要消耗大量的咨询时间 
			 几番考虑之后，写了talent-aio，线程池部分和部分思想来源于并优化于talent-nio，在性能大步提升的基础上，易用性得到根本性解决。 
		 
	 





	  参与talent-aio 
		 
			 java aio的驾驭需要有扎实的多线程基础，并且需要掌握很多多线程技巧，而talent-aio是将多线程技巧运用到极致的框架，所以一旦您参与到本项目，你将会从本项目中学到很多关于多线程的技巧。 
			 本项目会陆续提供一些业界案例作为例子供大家参考，譬如融云的IM 

			 
			通过以下方式之一，加入talent-aio技术群(系付费群，对talent-aio或tcp长连接不感兴趣的朋友请不要加入)
				 
					 通过群号加入: 428058412 
					 点击加入:     
					 扫码加入    
				 
			 
			 
			 
			  提交Issue
			 
			给项目提出有意义的新需求，或是帮项目发现BUG，或是上传你本地测试的一些数据让作者参考以便进一步优化。
			 

			 
			点击右上方的
			 
			 Star 
			 
			以便随时掌握本项目的动态
			 
		 
	 



 


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e26b3c0b1fd4c8d1adbdd35e74171fa27d11de685b38815b02d34205d916999a0f9b55651fcd708ab15dab8cd5f4f0b66)