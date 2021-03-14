#Spring框架参考文档 翻译

**文档地址**

中文文档:[http://spring.oschina.mopaas.com/](http://u.720life.cn/g/3d3c1eebe7d1a3ce4b19ffb3e57807e89fa619207522cc50e254f65d86af1be0b306863a011de5ef8e4a8b3c5c17ee5d)  

英文文档:[http://spring.oschina.mopaas.com/html_en/](http://u.720life.cn/g/3d3c1eebe7d1a3ce4b19ffb3e57807e89fa619207522cc50e254f65d86af1be023f6f8299a2aff993c3acdd84045999f)

**基本说明**

Spring文档为adoc格式，文件已经按基本的章节拆分为多个adoc文件，该文件在`src/asciidoc/chapter`路径下。  

**参与翻译**

1. 首先加QQ群Team翻译小组：111763438  

2. 进群后，会先发申请链接，加入OSC的Team

3. 进入Team后需要先绑定gitosc账号。

4. 可以从下面的章节中选择还没有人翻译的章节

5. 跟群主说明要翻译的章节（主要用来防止重复，同时更新下面的状态），确定后可以开始翻译。

6. **翻译前请看下面的要求**。

##I. 全部章节(加粗内容为已分配的章节)

- **1.introduction.adoc          - [lixiuwen](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844df42af76ec8f5a4417f2f88b5b2d52372)**
- **2.spring-whats-new.adoc      - [isea533](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4c31eba0d6793a436fac9bb2aa2e9ed44)**
- **3.beans.adoc                 - [isea533](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4c31eba0d6793a436fac9bb2aa2e9ed44)**
- **3.1.beans.adoc(5.1. Introduction&5.2. Container overview) - [isea533](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4c31eba0d6793a436fac9bb2aa2e9ed44)**
- **3.2.beans.adoc(5.3. Bean overview) - [isea533](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4c31eba0d6793a436fac9bb2aa2e9ed44)**
- **3.3.beans.adoc(5.4. Dependencies) - [reeco](http://u.720life.cn/g/b56a32676c52deea69b3fa6af7eae602b9bf8805b5874ccfe28bf5e2696b0acd)**
- **3.4.beans.adoc(5.5. Bean scopes) - [sealin](http://u.720life.cn/g/b56a32676c52deea69b3fa6af7eae602b54acae16968d2e3cfb0595023abec41)**
- 3.5.beans.adoc(5.6. Customizing the nature of a bean) -
- 3.6.beans.adoc(5.7. Bean definition inheritance) -
- 3.7.beans.adoc(5.8. Container Extension Points) -
- 3.8.beans.adoc(5.9. Annotation-based container configuration) -
- 3.9.beans.adoc(5.10. Classpath scanning and managed components) -
- 3.10.beans.adoc(5.11. Using JSR 330 Standard Annotations) -
- 3.11.beans.adoc(5.12. Java-based container configuration) -
- 3.12.beans.adoc(5.13. Environment abstraction) -
- 3.13.beans.adoc(5.14. Registering a LoadTimeWeaver) -
- 3.14.beans.adoc(5.15. Additional Capabilities of the ApplicationContext) -
- 3.15.beans.adoc(5.16. The BeanFactory)              -
- **4.resources.adoc             - [tianya](tianyatianya-PC)**
- **5.validation.adoc            - [jassen](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d139d5a2288b9201bd84529023642de19)**
- **7.expressions.adoc           - [Ji.K'](http://u.720life.cn/g/7b6a6acbcbc263c200f13005264c1f7f790c6b93a7a0764dcfa7427de43c7571)**
- **8.aop.adoc                   - [ym919202](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d365697fc2e379bb31c0c343d4bec36f5a19d9655a6929a220727a56d8f927541)**
- **9.aop-api.adoc(10.1. Introduction) - [waylau](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304671774a88747b5c0044ba08a6e8e78897)**
- 9.1.aop-api.adoc(10.2. Pointcut API in Spring) -
- 9.2.aop-api.adoc(10.3. Advice API in Spring) -
- 9.3.aop-api.adoc(10.4. Advisor API in Spring) -
- 9.4.aop-api.adoc(10.6. Concise proxy definitions) -
- 9.5.aop-api.adoc(10.7. Creating AOP proxies) -
- 9.6.aop-api.adoc(10.8. Manipulating advised objects) -
- 9.7.aop-api.adoc(10.9. Using the "auto-proxy" facility) -
- 9.8.aop-api.adoc(10.10. Using TargetSources) -
- 9.9.aop-api.adoc(10.11. Defining new Advice types) -
- 10.testing.adoc(11. Introduction) -
- 10.1.testing.adoc(11.3. Integration Testing) -
- 10.2.testing.adoc(11.3.3. JDBC Testing Support) -
- 10.3.testing.adoc(11.3.4. Annotations) -
- 10.4.testing.adoc(11.3.5. Spring TestContext Framework) -
- 10.4.1.testing.adoc(11.3.5.3. Context management) -
- 10.4.2.testing.adoc(11.3.5.4. DI) -
- 10.5.testing.adoc(11.3.6. Spring MVC Test Framework) -
- 10.6.testing.adoc(11.3.7. PetClinic Example) -
- **11.spring-data-tier.adoc     - [阿信](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844dbad1a4df22ea4d3ffeb4a96f9827e0b0d9b62e3a646512dfbb12613ed5f522a4)**
- **12.dao.adoc                  - 已经分配**
- 13.jdbc.adoc                 -
- **14.orm.adoc                  - [waylau](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304671774a88747b5c0044ba08a6e8e78897)**
- 15.oxm.adoc                  -
- **16.spring-web.adoc           - [tianya](tianyatianya-PC)**
- 17.view.adoc                 -
- **18.web-integration.adoc      - [阿信](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844dbad1a4df22ea4d3ffeb4a96f9827e0b0d9b62e3a646512dfbb12613ed5f522a4)**
- 19.portlet.adoc              -
- **20.websocket.adoc            - [zipu888](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844dbf3249461f8188a64ec4f6bd4bd840ee5524c986847ec5421d06c5bcf569bbbe)**
- 21.spring-integration.adoc   -
- 22.ejb.adoc                  -
- 23.jms.adoc                  -
- 24.jmx.adoc                  -
- 25.cci.adoc                  -
- **26.mail.adoc                 - 抢小孩糖吃**
- **27.scheduling.adoc           - [qxs](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844db07234b06782175a04a130e78bc3bb31)**
- 28.dynamic-language.adoc     -
- **29.cache.adoc                - 抢小孩糖吃**
- 31.classic-spring.adoc       -
- 32.classic-aop-spring.adoc   -
- 33.xsd-config.adoc           -
- 34.extensible-xml.adoc       -
- 35.spring.tld.adoc           -

##II. 翻译一般要求

为了大家在翻译的时候文件格式正确，而且翻译比较一致，需要遵守一定的要求。

###第一条、 adoc语法

Spring文件使用的adoc语法，和markdow比较接近。  

只有大概了解这种语法才能在翻译的时候知道应该翻译什么，那些不应该翻译。所以要求大家简单了解adoc语法。

asciidoc语法--快速参考：

> [http://asciidoctor.org/docs/asciidoc-syntax-quick-reference/](http://u.720life.cn/g/fa2370206704fba46e83dd8f242bfff9010f609529e964aae7c659fa02cbd39a3eb1a2ad944185194eebc4e777ba6dc60efa9eb21826e3fcb84cb830aa96a49c)  

asciidoc中文文档：

>[http://houqp.github.io/wbwa/wbwa.html](http://u.720life.cn/g/ad2bd6bef1668726f8a3a87e02d79ae1df6172b4c542e5b55f60aad0feec1392e3e66a7a3f35ca7bb9f1849df8c0d509)

建议大家一定看看，否则翻译后的文档会出现一些格式错误。  

为了便于查询adoc的预览效果，可以安装Chrome插件：

> [https://github.com/asciidoctor/asciidoctor-chrome-extension](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304687161d347b91d5f7886c506cebcdaa8f650bbd7b26ddf2a4de729c968b63ea4ac8c520afa8f4ccdd63816423e10641d0)  


###第二条、 代码部分

在adoc语法中：

	[source,xml,indent=0]
	[subs="verbatim,quotes,attributes"]
	----
		 
			 
				 org.springframework 
				 spring-context 
				 {spring-version} 
				 runtime 
			 
		 
	----

这种是代码内容，这里面的内容一般不需要做任何修改。但是如果代码中有**注释**内容，需要把注释翻译成中文。  

###第三条、 词库  

对于一些英语中专有的词汇，不需要进行翻译的可以不翻译。

例如：Spring不需要翻译，list,map等等不需要翻译，像bean也不用翻译。  

具体遇到那些词可以在群内讨论。  

##III. 编译本项目   

**目录结构**：

为了便于独立翻译，已经手工将`index.adoc`和`appendix.adoc`进行了拆分。拆分后的内容在`src\asciidoc\chaptor`中。

Spring项目使用的**Gradle**,编译文档也需要用到**Gradle**，所以如果你想编译本项目，需要按如下进行操作：  

###1. 下载并配置Gradle

按照官方的进行配置即可，主要是bin加入Path

###2. 在项目的根目录执行命令

>gradle

然后会下载项目依赖，其中jruby有20多M，整体下载速度一般（使用的osc的maven库）。  

项目运行到最后会报错。

**报错解决**：

报错是因为文件编码的问题，需要修改一个jar包。这个jar包只有执行上面的命令后才会下载下来。  

这个jar包的目录可能是这样：  

>E:\.gradle\caches\modules-2\files-2.1\org.asciidoctor\asciidoctor-java-integration\0.1.4\3596c7142fd30d7b65a0e64ba294f3d9d4bd538f

或者你找到**.gradle**目录后搜索**asciidoctor-java-integration-0.1.4.jar**查找。  

在jar包的**asciidoctor-java-integration-0.1.4.jar\gems\asciidoctor-0.1.4\lib**这个目录下，有一个**asciidoctor.rb**文件。  

在这个文件中找到110行左右，在下面这行代码前添加内容：  

	FORCE_ENCODING = RUBY_VERSION > '1.9' && Encoding.default_external != Encoding::UTF_8


添加的内容为：  

	Encoding.default_external = Encoding::UTF_8

修改后的文件为：  

	# utf8
	Encoding.default_external = Encoding::UTF_8
	
	# Flag to indicate whether encoding of external strings needs to be forced to UTF-8
	# _All_ input data must be force encoded to UTF-8 if Encoding.default_external is *not* UTF-8
	# Address failures performing string operations that are reported as "invalid byte sequence in US-ASCII" 
	# Ruby 1.8 doesn't seem to experience this problem (perhaps because it isn't validating the encodings)
	FORCE_ENCODING = RUBY_VERSION > '1.9' && Encoding.default_external != Encoding::UTF_8


然后将修改后的**asciidoctor.rb**覆盖jar包目录中的文件即可。  

**最后**，再次执行：  

>gradle  

经过几分钟的编译就好了。编译成功的输出日志：

>E:\Git\spring-framework-reference>gradle  
>:asciidoctor  
>:referenceHtmlMulti  
>  
>BUILD SUCCESSFUL  
>  
>Total time: 3 mins 56.987 secs  

成功后可以在根目录下的**build**中看到生成的内容。  

**目前为了节省编译时间，现在只生成了分章节的html。**




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e733d1b626439eefd18e3ad6333962cc04e2826b1a8b5e6982322b56f58252d9ab83b8e0cbd674cf86400af0b7b33365df6b2a2338b13b5922c6f4ee2b4b590d6)