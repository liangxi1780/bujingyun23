#spring-oauth-server


 Spring与Oauth2的整合示例 

项目用Maven管理


使用的技术与版本号
 
  JDK (1.8.0_40) 
  Servlet (3.1.0) 
  Spring (4.1.6.RELEASE) 
  Spring Security (4.0.1.RELEASE) 
  spring-security-oauth2 (2.0.7.RELEASE) 
  Log4j (1.2.14) 
 
 

 
   Oauth客户端项目请访问  spring-oauth-client 
 
 
   在线测试访问地址  https://andaily.com/spring-oauth-server/ 
 
 
   Shiro与OLTU整合的Oauth2项目  http://git.oschina.net/mkk/oauth2-shiro 
   (相比spring-oauth-server, 该项目入门门槛相对较低, 代码更加透明, 理解更容易,可扩展性更强, 且模块化开发)
 
 

 
 如何使用? 
 
 
项目是Maven管理的, 需要本地安装maven(开发用的maven版本号为3.1.0), 还有MySql(开发用的mysql版本号为5.6)
 
 
 下载 (或clone)项目到本地
 
 
创建MySQL数据库(如数据库名oauth2), 并运行相应的SQL脚本(脚本文件位于others/database目录),
 
   运行脚本的顺序: initial_db.ddl -> oauth.ddl -> initial_data.ddl
 
 
修改 spring-oauth-server.properties (位于src/main/resources目录)中的数据库连接信息(包括username, password等)
 
 
将本地项目导入到IDE(如Intellij IDEA)中,配置Tomcat(或类似的servlet运行服务器), 并启动Tomcat(默认端口为8080);
 
注意将项目的 contextPath(根路径) 设置为 'spring-oauth-server'.
 
   另: 也可通过maven package命令将项目编译为war文件(spring-oauth-server.war),
         将war放在Tomcat中并启动(注意: 这种方式需要将spring-oauth-server.properties加入到classpath中并正确配置数据库连接信息).
 
 
参考 oauth_test.txt (位于others目录)的内容并测试之(也可在浏览器中访问相应的地址,如: http://localhost:8080/spring-oauth-server).
 
 
 


 
 grant_type 
 
说明Oauth支持的grant_type(授权方式)与功能
 
      authorization_code  -- 授权码模式(即先登录获取code,再获取token) 
      password  -- 密码模式(将用户名,密码传过去,直接获取token) 
      refresh_token  -- 刷新access_token 
      implicit  -- 简化模式(在redirect_uri 的Hash传递token; Auth客户端运行在浏览器中,如JS,Flash) 
      client_credentials  -- 客户端模式(无用户,用户向客户端注册,然后客户端以自己的名义向'服务端'获取资源) 
 



 
 帮助与改进 
 
 
 
 与该项目相关的博客请访问  http://blog.csdn.net/monkeyking1987/article/details/16828059 
 
 
 
 
 如果在使用过程中遇到特殊的问题(如:如何将oauth_code存入数据库),请访问项目的  Wiki  
 与  附件 . 
  
 我会把大家反馈的问题解决办法添加在这里.
  
 若在这两个地方没有找到解决办法的,
 欢迎发邮件到 shengzhao@shengzhaoli.com 一起讨论.
 
 

 
 
 如果在使用项目的过程中发现任何的BUG或者更好的提议, 建议将其提交到项目的  Issues  中, 
 我会一直关注并不断改进项目. 
 
 
 

 
 功能扩展 
 
     
         oauth_code存入数据库的配置 ,  请下载文件  oauth_code存入数据库的配置.jpg 
     
     
         改变token过期的时间的配置 , 请下载文件 改变token过期的时间的配置.jpg 
     
     
         自定义 grant_type , 默认情况支持的grant_type包括 [password,authorization_code,refresh_token,implicit], 若不需要其中的某些grant_type,
        则可以修改 oauth_client_details 表中的 authorized_grant_types 字段的值;
         
        若想把整个Oauth服务修改来只支持某些grant_type, 请修改  security.xml 文件中的
         oauth2:authorization-server  中的内容,将对应的 grant_type 注释或删掉即可
     
     
         
             如何刷新access_token(refresh_token) , 在通过客户端(如移动设备)登录成功后返回的数据如下
             
             {"access_token":"3420d0e0-ed77-45e1-8370-2b55af0a62e8","token_type":"bearer","refresh_token":"b36f4978-a172-4aa8-af89-60f58abe3ba1","expires_in":43199,"scope":"read write"}
             
             
            若需要刷新获取新的token(一般在 expires_in 有效期时间快到时), 请求的URL类似如下
             
             http://localhost:8080/oauth/token?client_id=mobile-client&client_secret=mobile&grant_type=refresh_token&refresh_token=b36f4978-a172-4aa8-af89-60f58abe3ba1
             
             
            注意: refresh_token 参数值必须与登录成功后获取的 refresh_token 一致, 且grant_type = refresh_token
             
            另: 刷新token 需要 ClientDetails 支持 refresh_token 类型的 grant_type (默认是支持的)
         
     
 


 
 开发计划 
 
从 0.3版本开始将项目的所有计划的开发内容列出来, 方便大家跟进, 也欢迎你加入.
 
项目的开发管理使用开源项目  andaily-developer .
 
 
        
             
                Version:  0.5  [planning]
                 
                Date: 2016-02-19 / ------
             
             
                  (118) - Add java-config(零配置) 的支持, 以及启用 新的注解  
                  (138) - OAuth 'token' Restful API  
                  (139) - User Overview/ user add/archive  
                  (143) - Add project API document  
             
             
        
        
             
                Version:  0.4  [finished]
                 
                Date: 2015-11-09 / 2015-11-30
             
             
                   (97) - Fix custom access_token_validity,refresh_token_validity issue(#5)   
                   (109) - 升级 spring-security-oauth2 的版本到 2.0.6以上, 目前是1.0.5    
                   (113) - Upgrade spring, spring security version to > 4.0   
                   将项目添加到在线测试服务器   
                   (115) - Sync update spring-oauth-client version with spring-oauth-server   
                   (116) - Remove mybatis dependency   
                   Upgrade JAVA to 1.8; Servlet 3.0   
                   Oauth table add index    
             
        
        
             
                Version:  0.3  [finished]
                 
                Date: 2015-05-14 / 2015-06-07
             
             
                  #73 - Upgrade 'spring-security-oauth2' version to '2.0.6.RELEASE' (current: 1.0.5.RELEASE)      [CANCELED]  
                   #74 - oauth mysql ddl add create_time,  default is now()     
                   #75 - Add user information API, for   spring-oauth-client   project use
                     
                    URL: /unity/user_info
                    Login: Yes (ROLE_UNITY)
                    Data Format: JSON

                    URL: /m/user_info
                    Login: Yes (ROLE_MOBILE)
                    Data Format: JSON
                     
                      
                 
                   #77 - User add Privilege domain.
                                  Addition initial two user: unityuser(ROLE_UNITY),mobileuser("ROLE_MOBILE).
                                  If default user, return all privilegs, otherwise return specify privilege(s)    
                   #78 - Initial 'sprint-oauth-client' project(maven), add sub-modules   
                   #91 - User log4j replace logback dependency    
                   #92 - Add database table column description. (添加数据库表的字段说明)    
                   #93 - 将默认的 oauth_code存入数据库(当前是存入内存)    
                    spring-oauth-server project add Bootstrap CSS     
                   #95 - Add 'client-details' management; create/delete, show testing links   

             
        
 
 

 
 数据库表字段说明 
 
    在0.3版本中添加了 db_table_description.html 文件(位于/others目录), 用来说明数据库脚本文件 oauth.ddl 中各表,各字段的用途及使用场合.
     
    也可在线访问 http://andaily.com/spring-oauth-server/db_table_description.html .
 


 
 Project Log 
 
     
           2013-11-19      Initial project, start push code  
           2013-11-20      发布 0.1 版本  
           2015-05-06         发布 0.2 版本  
           2015-05-27       创建项目博客,访问地址  http://andaily.com/blog/?cat=19   
           2015-06-07         发布 0.3 版本  
          
             2015-06-16        添加github访问:  https://github.com/monkeyk/spring-oauth-server ,
            以后的更新将同步github与gitosc.
          
           2015-11-09         开始开发 0.4-beta 版本  
           2015-11-18         发布  0.4-beta  版本  
           2016-01-02         发布  0.4  版本  
           2016-02-19         Add 0.5 version development planning  
     
 


 
 更多资源 
 以下是在学习工作中收集的更多关于Oauth的资源,对深入理解与运用Oauth有帮助 
 
        
             
                 RFC 6749 - The OAuth 2.0 Authorization Framework , OAuth2.0协议(英文)
             
        
        
             
                 OAuth 2.0 &mdash; OAuth , OAuth2.0官方网站
             
        
        
             
                 OAUTH2核心参数说明 , 重点介绍了grant_type 与 response_type 以及示例
             
        
        
             
                 OAuth2 flows , 详细介绍Oauth2的流程,各类错误发生时的响应
             
        
        
             
                 OAuth 2 开发人员指南（Spring security oauth2） , 翻译OAuth 2 Developers Guide(spring security oauth2)
             
        
        
             
                 理解OAuth 2.0 , 介绍Oauth2各类grant_type的使用
             
        
        
             
                 OAuth2：隐式授权（Implicit Grant）类型的开放授权 , 介绍grant_type='implicit'模式
             
        
        
             
                 Apache Oltu , Java版的 Oauth参考实现, 建议去了解了解
             
        
 


 
 
    与项目相关的技术文章请访问  http://andaily.com/blog/?cat=19  (不断更新与Oauth相关的文章)
 
 
     问答与讨论 
     
    与项目相关的，与Oauth相关的问题与回答，以及各类讨论请访问 
     http://andaily.com/blog/?dwqa-question_category=oauth 
 


 
 使用案例 
 以下是已知的使用(或基于) spring-oauth-server 开源项目的各类商业项目(排名不分先后), 若你有案例希望添加, 请联系作者. 
 
      Hongkong Parkway Online (在线医疗服务系统)  
      海尔日日平台 (B2B电商平台)  
      wdcy-game (手机游戏服务端)  
      Honyee Management System (企业管理系统)  
      AoLin Open Platform (国际物流开发平台)  
      IDS (移动安全产品)  
      ......  
 


 
 
     捐助 
     
    支付宝: monkeyking1987@126.com (**钊)
     
    快意江湖 -- 100元
     
    yufan -- 100元
 

 
 
 关注更多我的开源项目请访问  http://andaily.com/my_projects.html 
 
 
 若需更多的技术支持请联系  monkeyk@shengzhaoli.com 
 
 
  若需商业技术支持或提供技术解决方案, 请联系  sz@monkeyk.com  
 或访问  http://monkeyk.com/kso/ 
 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec99b9d3c01084cd8784ceb0f31055f3954f784fc287c68444d2bbbc81ea5bebe64fb605c25205683e6945b022bf8dc49e9ede50bb6464e48926b62f1313751fa)