## 关于本项目
spring boot 2.0后,加强了oauth2的支持。研究源码后，主要是增加了http.oauth2Login()
，在5.1.0.RC1版本，还增加了http.oauth2(),处理更加灵活。

当然，oauth2的功能还在不断完善中，特别在RC版本也是有BUG，有兴趣使用的，可以再等等。

本项目是算是在RC1版本中的二次封装，以适应中国国内oauth2提供商的规范（微信、QQ）以及我单位的中央认证的支持。

## 如何使用本项目
#### 先编译本项目：
mvn install

#### 新建一个spring boot 2 项目，在pom.xml中加入:

         
             cn.edu.dgut.sw.security 
             security-oauth2 
             1.0.1 
         

#### 因为本项目使用了RC版本，所以要修改maven仓库：

     
         
             spring-milestones 
             Spring Milestones 
             https://repo.spring.io/libs-milestone 
             
                 false 
             
         
     
    
#### 还有一些Web项目必要的模块：

         
             org.springframework.boot 
             spring-boot-starter-web 
         

         
             org.springframework.boot 
             spring-boot-starter-thymeleaf 
         

#### 修改application.yml，配置各oauth2提供商的appid和appsecret

~~~
spring:
  thymeleaf:
    cache: false
  security:
    oauth2:
      client:
        registration:
          github:
            client-id: *****
            client-secret: *****
          weixin:
            client-id: *****
            client-secret: ******
          dgut:
            client-id: *****
            client-secret: *****
          qq:
            client-id: *****
            client-secret: *****

            
sai:
  security:
    oauth2:
      authorizationResponseBasePath: /uaa/login      #修改回调地址
~~~        
#### 最后，在spring security中添加配置：
~~~java
@EnableSaiOAuth2Login
public class SaiOAuth2LoginConfiguration extends WebSecurityConfigurerAdapter {

    private SaiOAuth2LoginSecurityConfigurer saiOAuth2LoginSecurityConfigurer;

    public SaiOAuth2LoginConfiguration(SaiOAuth2LoginSecurityConfigurer saiOAuth2LoginSecurityConfigurer) {
        this.saiOAuth2LoginSecurityConfigurer = saiOAuth2LoginSecurityConfigurer;
    }

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        // @formatter:off
        http
                .authorizeRequests()
                .anyRequest().authenticated()
                .and()
                .apply(saiOAuth2LoginSecurityConfigurer)
        ;
        // @formatter:on
    }
}
~~~

#### 上面的配置代码注意两点：
1. 是使用@EnableSaiOAuth2Login注解启用配置。
2. http.apply(saiOAuth2LoginSecurityConfigurer),这样配置才会生效。

### 欢迎大家交流学习
QQ:2231068



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2bb9f296f92353fbe5c19f7852fb1630e0b9e31b77679bf649cb38220a7ab0038c7a04d5be4b8e67debf0e8af58fa762cb7d7bbfe80ebc726115b7c3aeed28ad)