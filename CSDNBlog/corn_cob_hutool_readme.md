 
	   
 
 
	 A set of tools that keep Java sweet. 
 
 
	 
		  
	 
	 
		  
	 
	 
		  
	 
	 
		  
	 
	 
		  
	 
	 
		  
	 
 
 
	-- 主页： http://hutool.cn/  --
 
 
	-- QQ群②： 871141901  --
 

-------------------------------------------------------------------------------

## 简介

Hutool是一个Java工具包，也只是一个工具包，它帮助我们简化每一行代码，减少每一个方法，让Java语言也可以“甜甜的”。Hutool最初是我项目中“util”包的一个整理，后来慢慢积累并加入更多非业务相关功能，并广泛学习其它开源项目精髓，经过自己整理修改，最终形成丰富的开源工具集。

Hutool是Hu + tool的自造词，前者致敬我的“前任公司”，后者为工具之意，谐音“糊涂”，寓意追求“万事都作糊涂观，无所谓失，无所谓得”的境界。

-------------------------------------------------------------------------------

## 包含组件
一个Java基础工具类，对文件、流、加密解密、转码、正则、线程、XML等JDK方法进行封装，组成各种Util工具类，同时提供以下组件：

- hutool-aop              JDK动态代理封装，提供非IOC下的切面支持
- hutool-bloomFilter   布隆过滤，提供一些Hash算法的布隆过滤
- hutool-cache           缓存
- hutool-core             核心，包括Bean操作、日期、各种Util等
- hutool-cron             定时任务模块，提供类Crontab表达式的定时任务
- hutool-crypto          加密解密模块
- hutool-db               JDBC封装后的数据操作，基于ActiveRecord思想
- hutool-dfa              基于DFA模型的多关键字查找
- hutool-extra            扩展模块，对第三方封装（模板引擎、邮件、Servlet、二维码等）
- hutool-http             基于HttpUrlConnection的Http客户端封装
- hutool-log              自动识别日志实现的日志门面
- hutool-script           脚本执行封装，例如Javascript
- hutool-setting         功能更强大的Setting配置文件和Properties封装
- hutool-system        系统参数调用封装（JVM信息等）
- hutool-json            JSON实现
- hutool-captcha      图片验证码实现

-------------------------------------------------------------------------------

## 文档 

[中文文档](http://u.720life.cn/g/17a180c798e6efa0a4495086733fde19b994d90e60e641368865fcaf5cdaf5d8)

[参考API](http://u.720life.cn/g/b6749edd47dfb34db84492b28bcc9586659cdb7d6f7640732157e49f19b1d5fe426128b5d2880bc29387b1a3d9064ead)

-------------------------------------------------------------------------------

## 安装

### Maven
在项目的pom.xml的dependencies中加入以下内容:

```xml
 
     cn.hutool 
     hutool-all 
     4.1.14 
 
```

### Gradle
```
compile 'cn.hutool:hutool-all:4.1.14'
```

### 非Maven项目

点击以下任一链接，下载`hutool-all-X.X.X.jar`即可：

- [Maven中央库1](http://u.720life.cn/g/dbe7e997259d1c03ff78b9040174184dc00a60698e6a3f91d94d1eda8483020c58a522ac50f990226b844b6d8e458164a9bb973a3fb4268e2525bc5885912730)
- [Maven中央库2](http://u.720life.cn/g/ef7fb0b2230c8fa1a9059592fbae18e0a8e40e6ddb96c586ddb75b302038ce73b0543cb1555fe8c6cdfed8266612539503b7c2742a8ea424e87330db88c82605)

-------------------------------------------------------------------------------

## 版本变更

- [Release版本变更说明](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e87e130a340bb2150e0df73d2f77a94e892c996da3327cf8da6cbf41ab41a82821959e727b89f40540865a06f638f16f4)

- [SNAPSHOT版本变更说明](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e87e130a340bb2150e0df73d2f77a94e87d910d4bb63679461ce30cbd975cd7507cb23322e8e6f3cf65810802d5566ba4)

-------------------------------------------------------------------------------

## 添砖加瓦

### 提供bug反馈或建议

- [码云Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e87e130a340bb2150e0df73d2f77a94e865ef2e7856fc4d6011d2db2d84a02793)
- [Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046707fe3a61e2887e2dc70b2f3f1aa5755861871980e36d2207ac38ca4b43da5c7)

### 遵照的原则

Hutool欢迎任何人为Hutool添砖加瓦，贡献代码，不过作者是一个强迫症患者，为了照顾病人，需要提交的pr（pull request）符合一些规范，规范如下：

1. 注释完备，尤其每个新增的方法应按照Java文档规范标明方法说明、参数说明、返回值说明等信息，如果愿意，也可以加上你的大名。
2. Hutool的缩进按照Eclipse（不要跟我说IDEA多好用，作者非常懒，学不会）默认（tab）缩进，所以请遵守（不要和我争执空格与tab的问题，这是一个病人的习惯）。
3. 新加的方法不要使用第三方库的方法，Hutool遵循无依赖原则（除非在extra模块中加方法工具）。
4. 请pull request到`v4-dev`分支。Hutool在4.x版本后使用了新的分支：`v4-master`是主分支，表示已经发布中央库的版本，这个分支不允许pr，也不允许修改。`v4-dev`分支是开发分支，Hutool的下个版本或者SNAPSHOT版本在这个分支上开发，你可以pr到这个分支。

### 贡献代码的步骤

1. 在Gitee或者Github上fork项目到自己的repo
2. 把fork过去的项目也就是你的项目clone到你的本地
3. 修改代码（记得一定要修改v4-dev分支）
4. commit后push到自己的库（v4-dev分支）
5. 登录Gitee或Github在你首页可以看到一个 pull request 按钮，点击它，填写一些说明信息，然后提交即可。
6. 等待作者合并

-------------------------------------------------------------------------------

## 捐赠

如果你觉得Hutool不错，可以捐赠请作者吃包辣条~，在此表示感谢^_^。

点击以下链接，将页面拉到最下方点击“捐赠”即可。

[前往捐赠](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4683ece0916124993b55aad53000232f)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7a13ceb5142b000201848835e10950a30f769499ab146bc0c2dc9dbd6ed84d9ba02cba424b259530742f6fd4a9920584)