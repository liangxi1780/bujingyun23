# example
spring boot mvc 基础项目

1.将项目的启动类Application.java继承SpringBootServletInitializer并重写configure方法
@SpringBootApplication
public class TestApplication extends SpringBootServletInitializer {

    @Override
    protected SpringApplicationBuilder configure(SpringApplicationBuilder application) {
        //此处一定要写TestApplication
        return application.sources(TestApplication.class);
    }

    public static void main(String[] args) throws Exception {
        SpringApplication.run(Application.class, args);
    }

}
2.在pom.xml文件中，project下面增加package标签

 war 
3.还是在pom.xml文件中，dependencies下面添加

 
         org.springframework.boot 
         spring-boot-starter-tomcat 
         provided 
 


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5a00264bcb4536e2b9939d3216ebfaf313f6748bd98f79274a82e2d2d6252a512cbc826b1f4bd2e1afd433218d5aa65d)