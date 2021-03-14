#AgileDataAccess

Agile.DataAccess基于FluentData扩展重写，提供高效的性能与风格简洁的API，支持多种主流数据库访问。当前市面上的 ORM 框架，如 Entity Framework 和 NHibernate，都过于复杂而且难于学习。此外，由于这些框架自身抽象的查询语言以及从数据库到 .NET 对象的映射太过麻烦，导致它们生成的 SQL 都很笨重低效。

Agile.DataAccess是一个轻量级框架，采用函数式编程风格以及简单的 API 并且很容易学会。与其他微型 ORM（如 Dapper 和 Massive）类似关注性能和易用性。它允许开发人员拥有对 SQL 较多的控制，而不是完全依赖 ORM 进行自动生成。它不仅可以使用 SQL 来执行查询、增添和更新操作，还可以支持使用存储过程和事务。可以在不改动已有结构的情况下，与任何业务对象一同工作。

以下是 Agile.DataAccess 的一些其他特性：  

　　· 多结果集（Multiple Result Set）：在一次数据库操作下返回多个数据集；
 
　　· 开发人员可使用强类型对象或动态对象； 

　　· 可为创建时需要特殊处理的复杂对象自定义实体工厂（Custom Entity Factory）； 

　　· 具有添加其他数据库支持的能力。


### 数据库支持列表：


MS SQL Server using the native .NET driver.

MS SQL Azure using the native .NET driver.

MS Access using the native .NET driver.

MS SQL Server Compact 4.0 driver.

Oracle through the ODP.NET driver.

MySQL through the MySQL Connector .NET driver.

SQLite through the SQLite ADO.NET Data Provider.

PostgreSql through the Npgsql provider.

IBM DB2 through the IBM DB2 .NET driver

Sybase through the Sybase provider.


### API 示例 

 

**一、创建数据库上下文** 

方式一：创建默认DataBaseContext，ConnectionStrings["Default"]
```
var Context = new Agile.DataAccess.DataContext();
```

方式二：从指定的"ConnectionStrings[配置名]创建DataContext
```
var Context = new Agile.DataAccess.DataContext("Default");
```

方式三：从数据库连接字符串和数据库类型字符串名创建DataContext
```
var Context = new Agile.DataAccess.DataContext("Data Source=.;Initial Catalog=Agile;User Id=sa;Password=123;", "SqlServer");
``` 

方式四：从数据库连接字符串和数据库类型枚举创建DataContext
```
var Context = new Agile.DataAccess.DataContext("Data Source=.;Initial Catalog=Agile;User Id=sa;Password=123;", DataProvider.SqlServer); 
```
 

**二、执行T-SQL（Script）**

查询返回动态对象列表：
```
List  products = Context.Script("select * from Product").QueryMany ();
``` 

查询返回强类型对象列表：
``` 
List  products = Context.Script("select * from Product").QueryMany ();
```  

查询返回单个动态对象：
``` 
dynamic product = Context.Script("select * from Product where ProductId = 1").QuerySingle ();
```  

查询返回单个强类型对象：
``` 
Product product = Context.Script("select * from Product where ProductId = 1").QuerySingle ();
```  

查询返回数据表：
``` 
DataTable products = Context.Script("select * from Product").QuerySingle ();
```  

查询一个标量值：
``` 
int number = Context.Script("select count(*) from Product").QuerySingle ();
```  

查询一个标量值的列表：
``` 
List  productIds = Context.Script("select ProductId from Product").QueryMany ();
```  

自定义匹配实体类：
``` 
List  products = Context.Script("select p.*,c.CategoryId as Category_CategoryId,c.Name as Category_Name
                                         from Product p
                                         join Category c on p.CategoryId = c.CategoryId").QueryMany ();
``` 

自定义映射：

``` 
List  products = Context.Script("select * from Product").QueryMany (Custom_mapper_dynamic);
 
public void Custom_mapper_dynamic(Product product, dynamic row)
{
        product.ProductId = row.ProductId;
        product.Name = row.Name;
}
``` 
 

自定义映射使用DataReader：

``` 
List  products = Context.Script("select * from Product").QueryMany (Custom_mapper_datareader);
 
public void Custom_mapper_datareader(Product product, IDataReader row)
{
        product.ProductId = row.GetInt32("ProductId");
        product.Name = row.GetString("Name");
}
``` 
 

**三、查询参数的应用（Parameter）**

方式一：
``` 
dynamic products = Context.Script("select * from Product where ProductId = @0 or ProductId = @1")
                          .Parameters(1, 2).QueryMany ();
``` 
 

方式二：(命名参数)
``` 
dynamic products = Context.Script("select * from Product where ProductId = @ProductId")                           
                          .Parameter("ProductId", 1)
                          .QueryMany ();
``` 
  

方式三：(输出参数)
``` 
var command = Context.Script("select @ProductName = Name from Product where ProductId=1")
                     .ParameterOut("ProductName", DataTypes.String, 100);
command.Execute();
string productName = command.ParameterValue ("ProductName");
``` 
 

方式四：（IN参数）  
``` 
List  productIds = new List (){ 1, 2, 3 } ;
dynamic products = Context.Script("select * from Product where ProductId in (@ProductIds)")
                          .Parameter("ProductIds", productIds)
                          .QueryMany ();
``` 
 
**四、查询数据（Select）**

查询返回动态对象列表：
```
List  products = Context.Select("Product").QueryMany ();
```
 

查询返回强类型对象列表：
```
List  products = Context.Select("Product").QueryMany ();
```
 

查询返回单个动态对象：
```
dynamic product = Context.Select("Product").Where("ProductId", 1).QuerySingle ();
```
 

查询返回单个强类型对象： 
```
Product product = Context.Select("Product").Where("ProductId", 1).QuerySingle ();
```


查询返回数据表：
```
DataTable product = Context.Select("Product").QuerySingle ();
```
 

自动构造SQL
```
Product product = Context.Select ().Where("ProductId", 1).QuerySingle();

List  products = Context.Select ().QueryMany();
```
 

分页查询：


```
List  products = Context.Builder ().Select("p.*, c.Name as Category_Name")
                                                   .From("Product p Category c on c.CategoryId = p.CategoryId")
                                                   .Where("p.ProductId > 0 and p.Name is not null")
                                                   .OrderBy("p.Name")
                                                   .Paging(1, 10)
                                                   .QueryMany();

```

 

**五、插入数据（Insert）**

方式一：
```
Context.Script("insert into Product(Name, CategoryId) values(@0, @1);").Parameters("Way", 1).Execute();
```

方式二 :
```
Context.Script("insert into Product(Name, CategoryId) values(@Name, @CategoryId)")        
       .Parameter("Name", "Way")        
       .Parameter("CategoryId", 1)        
       .Execute();
```
 

方式三：(插入数据并返回自增主键)
```
int productId = Context.Script("insert into Product(Name, CategoryId) values(@0, @1);")
                       .Parameters("Way", 1).ExecuteReturnLastId ();
```
 

方式四： (插入数据并返回自增主键)
```
int productId = Context.Script("insert into Product(Name, CategoryId) values(@Name, @CategoryId)")
                       .Parameter("Name", "Way")                        
                       .Parameter("CategoryId", 1)                        
                       .ExecuteReturnLastId ();
```
 

方式五：(自动构造SQL)
```
Context.Insert("Product").Column("Name", "The Warren Buffet Way").Column("CategoryId", 1).Execute();
```
 

方式六： (自动构造SQL)
```
Product product = new Product();
product.Name = "The Warren Buffet Way";
product.CategoryId = 1;

Context.Insert (product, "Product").AutoMap(x => x.ProductId).Execute();
```
 

 

**六、更新数据(Update) **

方式一：
```
int rowsAffected = Context.Script("update Product set Name = @0 where ProductId = @1")
                          .Parameters("The Warren Buffet Way", 1).Execute();
```
 

方式二：
```
int rowsAffected = Context.Script("update Product set Name = @Name where ProductId = @ProductId")
                          .Parameter("Name", "The Warren Buffet Way")                           
                          .Parameter("ProductId" ,1)                           
                          .Execute();
```
 

方式三：
```
int rowsAffected = Context.Update("Product")
                          .Column("Name", "The Warren Buffet Way")
                          .Where("ProductId", 1)
                          .Execute();
```
 

方式四： (自动构造SQL)
```
int rowsAffected = Context.Update (product, "Product")
                          .AutoMap(x => x.ProductId)
                          .Where(x => x.ProductId)
                          .Execute();
```
  

插入或更新补填方法：


```
var product = new Product();
product.Name = "The Warren Buffet Way";
product.CategoryId = 1;  

var insertBuilder = Context.Insert (product, "Product").Fill(FillBuilder);  
var updateBuilder = Context.Update (product, "Product").Fill(FillBuilder); 
 
public void FillBuilder(IInsertUpdateBuilder  builder)
{
        builder.Column(x => x.Name);
        builder.Column(x => x.CategoryId);
}

```

 

 

**七、删除数据（Delete）**

方式一：
```
int rowsAffected = Context.Script("delete from Product where ProductId = 1").Execute();
```
 

方式二：
```
int rowsAffected = Context.Script("delete from Product where ProductId = @0").Parameters(1).Execute();
```
 

方式三：
```
int rowsAffected = Context.Script("delete from Product where ProductId = @ProductId ")
                          .Parameter("ProductId ", 1).Execute();
```

方式四：(自动构造SQL)
```
int rowsAffected = Context.Delete("Product").Where("ProductId", 1).Execute();
```
 

方式五：(自动构造SQL)
```
int rowsAffected = Context.Delete (product, "Product")
                          .Where(x => x.ProductId)
                          .Execute();
``` 
 


**八、记录是否存在（Exists）**

方式一：
```
bool result = Context.Exists("Product").Where("ProductId", 1).Execute();
```
 

方式二：
```
bool result = Context.Exists (product, "Product")
                     .Where(x => x.ProductId)
                     .Execute();
```
 

 

**九、存储过程（Procedure）**

方式一：
```
var rowsAffected = Context.Script("ProductUpdate")
                          .CommandType(DbCommandTypes.StoredProcedure)
                          .Parameter("ProductId", 1)
                          .Parameter("Name", "The Warren Buffet Way")
                          .Execute();
```
 

方式二：
```
var rowsAffected = Context.Procedure("ProductUpdate")
                          .Parameter("Name", "The Warren Buffet Way")
                          .Parameter("ProductId", 1).Execute();
```
 

方式三：

```
var command = Context.Procedure("ProductUpdate")
                     .ParameterOut("Number", DataTypes.Int16)
                     .Parameter("Name", "The Warren Buffet Way")
                     .Parameter("ProductId", 1);
int rowsAffected = command.Execute();
int number = command.ParameterValue ("Number");
```

 

方式四：
```
var rowsAffected = Context.Procedure (product, "ProductUpdate").AutoMap(x => x.CategoryId).Execute();
```
 

方式五：
```
var rowsAffected = Context.Procedure (product,"ProductUpdate")                            
                          .Parameter(x => x.ProductId)
                          .Parameter(x => x.Name)                           
                          .Execute();
```
 

 

**十、事物应用 （Transaction）**

使用事务时，包装里面的代码使用using语句来确保数据库连接关闭。默认情况下，如果发生任何异常或者不提交事物将自动回滚。


```
using (var context = Context.BeginTransaction())
{
     context.Script("update Product set Name = @0 where ProductId = @1")
            .Parameters("The Warren Buffet Way", 1)
            .Execute();
 
     context.Update("Product")             
            .Column("Name", "The Warren Buffet Way")
            .Where("ProductId", 1)
            .Execute();
 
     context.Update (product, "Product")
            .AutoMap(x => x.ProductId)
            .Where(x => x.ProductId)
            .Execute();
 
     context.Commit();
}
```

博客园地址：[http://www.cnblogs.com/MuNet/p/5740833.html](http://u.720life.cn/g/31b4df2dec4e570182ebec3760a67aad)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2a5a2f0dc4b38cf7c42de0a609a1df577473e03f385454b209009489744ab900b7578d340aa654ba5072977d0439aa50468d2684cf97b4a2fb2ce84ef225ec2a)