 
   
    
   
 

 
  Born To Simplify Development
 

 
   
     
   

   
     
   

   
     
   
 

## What is MyBatis-Plus?

MyBatis-Plus is an powerful enhanced toolkit of MyBatis for simplify development. This toolkit provides some efficient, useful, out-of-the-box features for MyBatis, use it can effectively save your development time.

## Links

-   [Documentation](http://u.720life.cn/g/a0a70c17034799da06b2d8d4948603050a71e15bc943ed4723661a436c442080)
-   [Samples](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460e2dfceae48b05605c598cf2ee6246f384fb36838efeaaebeedfed3e6511bebc95bd9b434ac41e107046e9d10c6ad8ed)
-   [Showcase](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ccb109bda21f3ff511b56059d4076e6c19af81eb094bf390ca593740ec1a1db9)

## Features

-   Fully compatible with MyBatis
-   Auto configuration on startup
-   Out-of-the-box interfaces for operate database
-   Powerful and flexible where condition wrapper
-   Multiple strategy to generate primary key
-   Lambda-style API
-   Almighty and highly customizable code generator
-   Automatic paging operation
-   SQL Inject defense
-   Support active record
-   Support pluggable custom interface
-   Build-in many useful extensions

## Getting started

-   Add MyBatis-Plus dependency
    -   Maven:
        ```xml
         
             com.baomidou 
             mybatis-plus-boot-starter 
             3.2.0 
         
        ```
    -   Gradle
        ```groovy
        compile group: 'com.baomidou', name: 'mybatis-plus-boot-starter', version: '3.1.2'
        ```
-   Modify mapper file extends BaseMapper interface

    ```java
    public interface UserMapper extends BaseMapper  {

    }
    ```

-   Use it
    ```java
    List  userList = userMapper.selectList(
            new QueryWrapper ()
                    .lambda()
                    .ge(User::getAge, 18)
    );
    ```
    MyBatis-Plus will execute the following SQL
    ```sql
    SELECT * FROM user WHERE age >= 18
    ```

> This showcase is just a small part of MyBatis-Plus features. If you want to learn more, please refer to the [documentation](http://u.720life.cn/g/a0a70c17034799da06b2d8d4948603050a71e15bc943ed4723661a436c442080).

## License

MyBatis-Plus is under the Apache 2.0 license. See the [Apache License 2.0](http://u.720life.cn/g/c0fe1da5278ca9f6360e901f74721f845e8fe6a63a2e42f1caa9cfc3bfda716480d0beb5865d0b08259d3122330d798e) file for details.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4d4ad3477955ebe530ad1f6fbcfec0be8b0d52d5fd97fddf968ed808bd54f38ef516df8e60bfa1a4cbb4635f54bab2b0)