# sqlFilter
The rapid development of plug-in
Project depend：http://git.oschina.net/egzosn/QueryParams

According to certain rules to generate SQL or HQL 
### page test
```html
 
   
      
   
   
      .top{

          width: 100%;
          height: 50px;
          text-align: center;
      }
      .content{
          border: 1px solid #666;
          width: 100%;
          height: 600px;
      }
   
   
 Dynamically generated sql 
  

         
             
            name(and ; right like):  
            age(and ; >=):  
            sex(or ; =):  
                 
             
         

  
   
 


```

###Effect of the page

![image](https://github.com/cnzzs/sqlFilter-tool/blob/master/demo/src/main/resources/pageTest.png?raw=true)


###The results

```html
------? Instead of the form ------
sql: from test t where t.age>= ? or t.sex= ? and t.name like ?
P1:15P2:maleP3:Minna%
------The key, the value form ------
sql:from test t where t.age>= :age or t.sex= :sex and t.name like :name
key:sex; value:male
key:name; value:Minna%
key:age; value:15
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed6a630606129aedef1044d16ab8efbb38f6c10db7cb6082d5afb2dc4485da10bcb603e76c9e862061dea3f916e6f94c5)