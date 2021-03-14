# jackson-dataformat-toml

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fjustdb%2Fjackson-dataformat-toml.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fjustdb%2Fjackson-dataformat-toml?ref=badge_shield)

jackson dataformat for toml. The reader is based on [tomlj](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304614f024fde982342860014e586f26ee35) and the writer is based on javascript toml parser [@iarna/toml](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c96f5f623c62e2699ca81a1f8814aade640fef191ec693e412030c7d0e120850158).  

** TOML 0.5.0 **

## Get it

## Maven

Functionality of this package can be used using following Maven dependency:

```xml
 
  ...
   
     com.teesoft 
     jackson-dataformat-toml 
     1.0 
   
  ...
 
```

## Use it

With simple 2-property POJO like this:

```java
// Note: can use getters/setters as well; here we just use public fields directly:
public class MyValue {
  public String name;
  public int age;
  // NOTE: if using getters/setters, can keep fields `protected` or `private`
}
```

```java
TOMLMapper mapper = new TOMLMapper();
MyValue value = new MyValue();
value.name = "justdb";
value.age = 1;
String toml = mapper.writeValueAsString(value);
mapper.writeValue(new File("target/test.toml"), value);
MyValue valueNew = mapper.readValue(toml, MyValue.class);
```

## License

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fjustdb%2Fjackson-dataformat-toml.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fjustdb%2Fjackson-dataformat-toml?ref=badge_large)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3bb24c5b773fa675ba183230101dcb9e8f9cd713c1573697c567e63a3fc4183cabd3afd77fe9123ca82d44cb02f9292568f35be5b43928ee0fa13a3076021e6d)