# rojo  


原是github上的一个开源项目[rojo](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d9a364a9bfc21693520292b0b59108f1)，本作进行了重构
使得它更加高效，功能上也更完善。

## 问题

使用redis的java客户端jedis的时候需要操作一系列key，保存某个对象的时候，需要把一个
个属性组合为key，然后set到redis，较繁琐。

## 解决方案

rojo是为了简化对象持久化到redis时的操作的，它提供了几个运行时解析的annotation来做
这件事情，把用户从设计对象属性的各种key的繁重劳作中解脱出来，而把精力主要放在对象
模型的设计上。

## 使用

直接上代码：
```java
@Entity
public class BaseEntity {

    @Id(Generator = "common::id")
    private long id;
    @Value(unique = true)
    private String name;

    public long getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

}
```

    这个BaseEntity使用了几个annotation。Entity表示此对象可被持久化到redis；Id指定了此类
对象的唯一id，Id拥有Generator属性，用来定制id生成策略，默认为空字符串，表示需要用户自行
管理id。@Id(Generator = "common::id")表示使用common::id这个redis的自增长key来自动生成id
    Value这个annotation可标注于基本类型（byte、short、int、long、float、double、String）
的属性上，以及元素为基本类型的集合（Collection、List、Set）以及Map属性上。	
    Value拥有几个重要是属性。当被标注的属性为基本类型时，可以指定它的unique为true（默认false）
以表达被标注属性的唯一性，比如BaseEntity的name属性就是唯一的，当持久化BaseEntity时，会
查看是否已经有一个与此对象相同（equal）的name属性的BaseEntity存在，如存在则持久化失败
    下面再看另一个Entity。
	
```java
@Entity(Cache=true)
public class TestEntity extends BaseEntity {

    @Value
    private List  list;
    @Value
    private Set  set;
    @Value
    private Map  map;
    @Value(sort = true, bigFirst = true, size = 100)
    private int age;

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }

    public void setMap(Map  map) {
        this.map = map;
    }

    public Map  getMap() {
        return map;
    }

    public void setSet(Set  set) {
        this.set = set;
    }

    public Set  getSet() {
        return set;
    }

    public List  getList() {
        return list;
    }

    public void setList(List  strings) {
        this.list = strings;
    }

}
```   
	
	这个TestEntity是继承自BaseEntity,因此id和name与BaseEntity相同不在赘述。此外此类
拥有list、set、map和age四个属性，list、set、map分别是元素类型为基本类型的集合类，也
在上面曾提过不赘述。看一下age这个属性，标注的Value注解拥有三个属性：sort、bigFirst、
size，用来表达持久化时按照此属性值排序到一个有序列表里面；sort为true表明需要排序，
bigFirst指定排序是按照从大到小的顺序，size指明排序列表的总长度（此例中排序列表长100）

    看一下如何持久化TestEntity到redis：
	```
	    Jedis je = new Jedis("localhost", 6379);
        je.auth("4swardsman");
        je.ping();
        je.flushAll();
        Repository re = new Repository(je);
		```
	首先就是创建一个Repository（指定Jedis对象）。很简单。
	```java
	    TestEntity ss = new TestEntity();
        ss.setName("test" + i);
        ss.setAge(i);
        List  l = new ArrayList ();
        l.add("fd");
        l.add("akjl;sfd");
        ss.setList(l);
        Map  map = new HashMap ();
        ss.setMap(map);
        map.put("a", 1);
        map.put("b", 2);
        re.writeAndFlush(ss);
		```
	以上就是初始化一个TestEntity并设置好各属性，最后调用Repository的writeAndFlush
方法写入redis。如果写入成功，返回的long值就是ss对象的id（>0）并且ss的id属性会被正确
赋值;如果失败则返回值  T get(Class  claz, long id, String p)方法
可用于获取对象的单个属性；void delete(Class claz, long id) 方法用于删除对象；
List  rank(Class claz, String p, long start, long end)方法用于获取排名列表。
    
	另外值得一提的还有缓存机制（Entity注释的Cache属性为true则开启缓存），当写入和获取一个对象后，
此对象会立即进入缓存，以便于下次获取时，有更好的效率。
坐标：

```xml
   
       org.beykery 
       rojo 
       1.1.4 
   
```

## 结语

enjoy it.

	
	



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e00a9cbca79ed94f62d9b45833809396992a8c58cfe4cd79e4e2e3f1490727ac7f91af21ee859edca36293d4875384c54)