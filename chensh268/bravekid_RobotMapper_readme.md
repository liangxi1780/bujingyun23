# RobotMapper

## Releases

[![NuGet](https://img.shields.io/nuget/v/RobotMapper.svg?style=plastic)](https://www.nuget.org/packages/RobotMapper/)

**项目地址：**[https://gitee.com/wuyuege/RobotMapper](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2d533abc848c283e36aed04e7822a707aaf38a55e5eb457df530a619aac80f4d)

---

##   RobotMapper诞生背景
1. 在日常项目开发中，需要将数据访问层的Entity转化为数据传输层的DTO，或者将数据传输层的DTO转化为前端的ViewModel,而手写转换方法很烦，而且随着结构的增加，类的增加，代码量会比较大且不利于更新维护，因此需要一款能够自动映射工具帮我们实现这些工作。
1. 我们对映射工具也有如下要求：     
- **转化效率必须高**：显然，查询数据只需要0.001毫秒但是映射花费1秒这是我们不能接受的；      
- **配置必须简单甚至无需配置或者自动配置**：每次映射都需要进行复杂的配置无异于手动映射让人烦躁；  
- **解决循环引用问题**：尤其是数据访问层，由于数据库表之间的关系，我们的Entity会有很多一对一，一对多，多对多的导航属性，类型之间的互相引用必不可少，传统的映射工具无法**自动解决该问题**，要么进入死循环要么映射效率低下；

#### 那么本映射工具“RobotMapper”就是为了解决以上问题而诞生的，是的，它叫RobotMapper,一切都是自动化完成！

---

## RobotMapper使用介绍
让我们先创建对应的DTO和Entity

**Entity**
```CSharp
namespace Entity
{
    public class User
    {
        public User()
        {
            Roles = new List ();
        }
        public string Id { get; set; }
        public string Name { get; set; }
        public string Code { get; set; }
        public string Department { get; set; }
        public List  Roles { get; set; }
        public User User12 { get; set; }
    }
}

namespace Entity
{
    public class Role
    {
        public string Name { get; set; }

        public List  Users { get; set; }
    }
}
```

**DTO**

```CSharp
namespace DTO
{
    public class User
    {
        public User()
        {
            Roles = new List ();
        }
        public string Id { get; set; }
        public string Name { get; set; }
        public string Code { get; set; }
        public string Department { get; set; }
        public List  Roles { get; set; }
        public User User12 { get; set; }
        public string UserName { get; set; }
    }
}

namespace DTO
{
    public class Role
    {
        public string Name { get; set; }

        public List  Users { get; set; }
    }
}
```
**接下来创建User**

```CSharp
public static User 创建扁平化User()
{
    Entity.User user = new User()
    {
        Code = "Liuhai",
        Id = "hai.liu",
        Department = "部门1",
        Name = "海哥",
    };
    return user;
}
```


1. **无需配置**：

```CSharp
var user = TestHelper.创建扁平化User();
var newuser = user.RobotMap ();
Assert.AreEqual(user.Code, newuser.Code);
Assert.AreEqual(user.Id, newuser.Id);
Assert.AreEqual(user.Department, newuser.Department);
Assert.AreEqual(user.Name, newuser.Name);
```

---

2. **解决循环引用**     
**创建一个循环引用User**

```CSharp
public static User 创建循环引用User()
{
    Entity.User user = new User()
    {
        Code = "Liuhai",
        Id = "hai.liu",
        Department = "部门1",
        Name = "海哥",
    };
    user.Roles.Add(new Role()
    {
        Name = "角色1",
        Users = new List () { new User() { Name = "SB" } }
    });

    return user;
}
```
**仍然是自动映射**

```CSharp
var user = TestHelper.创建循环引用User();
var newuser = user.RobotMap ();
Assert.AreEqual(user.Code, newuser.Code);
Assert.AreEqual(user.Id, newuser.Id);
Assert.AreEqual(user.Department, newuser.Department);
Assert.AreEqual(user.Name, newuser.Name);
Assert.IsTrue(newuser.Roles.Count == 1);
```

---

3. **效率问题**

```CSharp
var user = TestHelper.创建循环引用User();
for (int i = 1; i  ();
}
```
以上代码大家可自行测试，映射十万次：仅需1s

---


4. **批量映射**    

```CSharp
List  users = new List ();
for (int i = 1; i  ();
```
以上代码大家可自行测试，批量映射一万条：仅需190毫秒

---

### 其他功能：
- 支持自定义映射配置：
    
```CSharp
[TestMethod]
public void 测试配置Bind()
{
    Mapper.Initialize(creator =>
    {
        creator.CreatMap (config =>
        {
            config.Bind(x => x.User12.Name, y => y.UserName);
            config.BindName(x => x.User12, y => y.User13);
            config.Ignore(y => y.Roles);
        });
    });
}
```

---

- 支持忽略属性：

```CSharp
[TestMethod]
public void 测试忽略规则转换()
{
    Mapper.Initialize(creator =>
    {
        creator.CreatMap (config =>
        {
            config.Ignore(y => y.Code);
            config.Ignore("Department", "Name");
        });
    });
    var user = TestHelper.创建扁平化User();
    var newuser = user.RobotMap ();
    Assert.IsNull(newuser.Code);
    Assert.IsNull(newuser.Department);
    Assert.IsNull(newuser.Name);
}
```

---
- 支持即用即配

```CSharp
[TestMethod]
public void 测试即用即配绑定()
{
    var user = TestHelper.创建自引用User();
    var newuser = user.RobotMap (config=> 
    {
        config.Bind(x => x.User12.Name, y => y.UserName);
        config.BindName(x => x.User12, y => y.User13);
    });
    Assert.AreEqual(user.User12.Name, newuser.UserName);
}
```

```CSharp
[TestMethod]
public void 测试即用即配忽略()
{
    var user = TestHelper.创建扁平化User();
    var newuser = user.RobotMap (config=> 
    {
        config.Ignore(y => y.Code);
        config.Ignore("Department", "Name");
    });
    Assert.IsNull(newuser.Code);
    Assert.IsNull(newuser.Department);
    Assert.IsNull(newuser.Name);
}
```

---
- 子类映射启用父类策略    

在类与类之间进行映射时，当没有配置两者之间的映射关系时，可自动启用父类映射绑定规则：    
==优先级为：源子类-目标子类>>源父类->>目标子类->>源->>目标父类->>源父类->>目标父类==    
使用详情可查看： [子类映射启用父类策略](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2d533abc848c283e36aed04e7822a707b1461bf52ccf30a5ca365bddb3a1386137f1e187220224961fac6ecfb3bbab3def0c341f0765f86633ced3ebf6ab2eb9d01d4cb499bea4d8e72ff0a962ded9508a25df808a6f7106d755157cc00bd58f12576923ab5c26263581005ae4dd30059bb8e96cf876093541153170474f94b1)

###### 注：即用即配的策略仅在本次映射中生效，与全局配置互不影响！

---
### 详细文档：

- [自动配置策略](https://gitee.com/wuyuege/RobotMapper/wikis/pages?title=默认配置规则&parent=)
- [智能化解决循环引用问题](https://gitee.com/wuyuege/RobotMapper/wikis/pages?title=智能化解决循环引用问题&parent=)
- [高效与高速](https://gitee.com/wuyuege/RobotMapper/wikis/pages?title=高效与高速&parent=)
- [自定义绑定和忽略](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2d533abc848c283e36aed04e7822a707ffcafe1f65cd741b438d6f036bbc16ed4cc5395077d1f977d91c571675420e23de3961def5cce390ca42bc9bbed452ee2ce793c9cc840727aadd678ab3813e8f)
- [即用即配](https://gitee.com/wuyuege/RobotMapper/wikis/pages?title=即用即配&parent=)
- [RobotMapper支持的类型](https://gitee.com/wuyuege/RobotMapper/wikis/pages?title=RobotMapper支持的类型&parent=)
- [RobotMapper目前不支持的类型](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2d533abc848c283e36aed04e7822a707ffcafe1f65cd741b438d6f036bbc16ed706da8d5b0350b6cdf1ece00aa46a72cfafe01b6f3db08cc955638d15fa382d2e28f6d2dcde67716a60f5a43bd25c20379f438f6818f0df2099a7e4a7b1f33cd)
- 其他功能：待完善

---

## 最后希望大家能为我找出bug，也希望大家能够给我提一些意见和建议！



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e620a9d067e96b7997390004f579775ab595917d52ccba039ace405dcdc2fcb7a31ac2245fd0a64326ab195cc813d13b1)