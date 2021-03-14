'请一定记得使用dev分支开发，本地也可以建立自己的分支'
'git clone http://git.oschina.net/harleydog/hedge -b dev'
# 研究股票量化对冲

##一、项目环境搭建

1.安装Java
  >请安装jdk1.8,官网链接(http://u.720life.cn/g/0832d3c13dcf440b8c2ddd37014597194dfce0f4546bd12c9ba469d981d9d729007ebfc8068b2baf5cdf0064d40d49996eb00a28cfaf8cc7c27b0ae1f475650e5183bcaf126e450bca74a1fc482915f2) 

  >环境变量设置: 
  >`JAVA_HOME = JAVA安装目录，默认是C:\Program Files\Java\jdk1.8.0_65` 
  >`PATH = %PATH%;%JAVA_HOME%\bin;` 

2.开发工具
  >请使用Eclipse\ MyEclipse \ Intellij IDEA均可,支持正版 
  >![请参考Intellij IDEA中Java8语法的配置]
  >(http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d1cbdd535913c0715998fbdf789851069e3aeb8e4fe96f8c8aa2b2a33e219f2e3b86340fb1d180e28a14998ce5193b3f1facf6ecb9e89009b7c69821fd6d8bfc5) 

3.Maven
  >Maven下载: (http://u.720life.cn/g/bc840264f6cc23df0a8935b6f2922fec94ff6a8561d0b6bc316737cabaa302466bafbf8b7785b308988d92b91090cab8) 
  >环境变量配置 
  >`M2_HOME = Maven解压缩目录` 
  >`PATH = %PATH%;%JAVA_HOME%\bin;%M2_HOME%\bin;` 

  >另外请修改%M2_HOME%\conf\setting.xml配置文件 
  >将资源库修改为比较快的网站，推荐使用ibiblio或者oschina 
  >请参考配置（用代码直接覆盖[$MAVEN_HOME/conf/setting.xml]） 
  >(http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b003a120240c8fe21e3688b2f60d34e72b50730b897ffafbfa4c1d865e3a378aca56f4a23de89548606f2b80ed78630c59124823e62d1d3f4bb1362a2b9815880) 

3.nginx
  >本机开发可以考虑不安装nginx，直接用tomcat即可 
  >如打算安装nginx，请参考配置 
  >(http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b003a120240c8fe21e3688b2f60d34e72b50730b897ffafbfa4c1d865e3a378ac36bb9613f64ddcd723a4d22ea0ad60c4065705204de5692f705dda76362e3e32) 

4.tomcat
  >本项目中使用tomcat作为提供后台服务的容器 
  >tomcat下载:(http://u.720life.cn/g/27381b9b9aecbc3251722641d01ac5edc77564859caea78d2808d4c11b071bd2) 
  >本项目用到了JNDI数据源，请参考配置 
  >(http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b003a120240c8fe21e3688b2f60d34e72b50730b897ffafbfa4c1d865e3a378ac000b27b8d7130863d8592abd9291b376569b48996707a6ac728796e7fba02722) 
  >(http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b003a120240c8fe21e3688b2f60d34e72b50730b897ffafbfa4c1d865e3a378ac000b27b8d7130863d8592abd9291b376569b48996707a6ac728796e7fba02722) 

5.DB
   >如果开发请使用本地MySQL，DB初始化脚本请使用 
   >MySQL下载: (http://u.720life.cn/g/b82b5139a48b1e95aee5194da6c4350a74fcc7c781509dd46ea3c6cbb333a137) 
   >(http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b003a120240c8fe21e3688b2f60d34e72b50730b897ffafbfa4c1d865e3a378ac9355097916d874a46ebbaf095a01da02500ebdfc4ac548ef84c70042193c6cc2) 
   >具体的数据导入 可以联系作者索要 

6.外部API参考
   >本项目中使用的一些外部API参考如下 
   >1. 盈透证券TWS API:(http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d1cbdd535913c0715998fbdf78985106945f5897b7342b6a151a8ba8cf3e16faf) 
   >2.老虎证券API:(http://u.720life.cn/g/f5fbf1788b17d825362c29f15299ab418493b1befccf8904e67613374a42b950ce023ff00f8f22fd676b19931f617326) 
   >3.富途证券API:(http://u.720life.cn/g/87ce621b154ef4b89b93d8e25759622cc850d9eedab745ef3df4716329467e2371453157ecea853238212910010e2b46) 
   >4. DBTest,基于内存数据库的单元测试API(http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d1cbdd535913c0715998fbdf789851069a8bd58aa747b7c02862d0a472e011dd0) 
   >5. 淘宝开放平台:(http://u.720life.cn/g/7edd52ce728ea8f8fb7b39ea9c5196117b073e8a2a7badbf97d7a83795212394) 
   >6. 阿里大鱼短信发送接口:（http://www.alidayu.com/） 
   >7. 雪球网(抓取股票数据):(http://u.720life.cn/g/88051d2bd97bceb0b5bb3fc39e980dda3b0019d84333fca6c20d3194db6fc13f) 


##二、代码说明
1. 重要的包说明 
>1.1. com.diorsunion.hedge.algo :算法实现包，量化算法和股票对冲算法都实现在此包中 
>1.2. com.diorsunion.hedge.bo.datasync :数据同步不包,完成每天抓取数据同步到本地库中的功能 
>1.3. com.diorsunion.hedge.bo.db 基于数据库CRUD的业务实现类 
>1.4. com.diorsunion.hedge.bo.net 访问外部网络接口（比如雪球网）的功能 
>1.5. com.diorsunion.hedge.bo.quota 一些量化指标的计算和实现，比如MACD,KDJ 
>1.6. com.diorsunion.hedge.bo.sms 手机短信发送功能的实现 
>1.7. com.diorsunion.hedge.bo.stockdatainit 算法启动数据初始化的功能 
>1.8. com.diorsunion.hedge.common 公共类库 
>1.9. com.diorsunion.hedge.dal.entity 数据访问实体层 
>1.10. com.diorsunion.hedge.dal.repository 数据访问操作层 
>1.11. com.diorsunion.hedge.domain 业务域对象 
>1.12. com.diorsunion.hedge.exception 异常包 
>1.13. com.diorsunion.hedge.task 定时任务调度 
>1.14. com.diorsunion.hedge.util 工具包集合 
>1.15. com.diorsunion.hedge.web web层，包括controller和interceptor 
>
>其他..

2. 重要的类说明
2.1.目前大部分的启动函数都在src/test/java中,以测试的方式来完成功能 
> 2.1.1 com.diorsunion.hedge.algo.test 算法测试包 
> 2.1.2 com.diorsunion.hedge.bo.datasync.test 数据同步测试包 
> 2.1.3 com.diorsunion.hedge.bo.db.test  业务测试包 
> 2.1.4 com.diorsunion.hedge.bo.net.test  网络接口测试包 
> 2.1.5 com.diorsunion.hedge.bo.quota.test  量化指标生成测试包 
> 2.1.6 com.diorsunion.hedge.bo.sms.test  短信息发送测试包 

2.2.重要的测试基类
> 2.2.1 com.diorsunion.hedge.base.EmbeddedBOBaseTest 内存数据库单元测试基类 
> 2.2.1 com.diorsunion.hedge.base.ExternalApiBaseTest 外部API集成测试基类 
> 2.2.1 com.diorsunion.hedge.base.NetBaseTest 网络接口集成测试基类 
> 2.2.1 com.diorsunion.hedge.base.RealDataSourceBOBaseTest 真实数据库集成测试基类 
> 2.2.1 com.diorsunion.hedge.base.RepositoryBaseTest 持久层单元测试基类 

##三、当前目标（2016-04-24）
1. 量化指标（MACD,KDK,RSI,BOLL）的计算和数据定时同步 
2. 核心算法的完善 
3. 网页的制作，包括算法运行效果等 


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed5e15710e05dcba9a396c68cec204ce3cdbc618a52fa3dde633e062c8e71702b8b44abc13ee17c13b659ea55ecd373da)