spring-boot-start-dubbo
---

* Dubbo是阿里开发的一套分布式通讯框架,Spring-boot是业界比较火的微服务框架，两者可以进行结合实现分布式微服务
* 对于内部远程Rpc调用，可以借用Dubbo能力，达到服务治理的目的

增加feign protocol支持
---

> 该协议主要是为了支持老项目可以消费springcloud提供的接口，并可以利用dubbo的服务发现，构建出一个springboot rest集群，
> dubbo与springboot结合时，不需要dubbo再次导出rest服务。而是由springboot提供rest服务dubbo端只负责注册，构建服务目录。


如何发布Dubbo服务
---

在Spring Boot项目的pom.xml中添加以下依赖:
---

```
  
         com.github.wu191287278 
         spring-boot-starter-dubbo 
         1.5.33 
  
 ```

example

---

```
//服务端，多协议发布服务
@RestController
@Service(version = "1.0.0", protocol = {"dubbo","feign"}, timeout = 10000) //该注解仅仅是描述接口使用,并不会造成多次实例化
@RequestMapping(value = "/user/")
public class UserServiceImpl implements UserService {

    @Autowired
    private UserDao userDao;

    public User selectByPrimaryKey(@PathVariable("id") Long id) {
        return userDao.selectByPrimaryKey(id);
    }

    public Object insert(@RequestBody User t) {
        return userDao.insert(t);
    }

    public Object updateByPrimaryKey(@RequestBody User t) {
        return userDao.updateByPrimaryKey(t);
    }

    public int deleteByPrimaryKey(@PathVariable("id") Long id) {
        return userDao.deleteByPrimaryKey(id);
    }
    
}

@SpringBootApplication
@EnableDubboAutoConfiguration
public class Application {

    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}


//消费端
@FeignClient(path = "/user")
@DubboClient(protocol = "feign", value = @Reference(timeout = 10000, version = "1.0.0"))
public interface UserService {

    @RequestMapping(value = "/{id}", method = RequestMethod.GET)
    User selectByPrimaryKey(@PathVariable("id") Long id);

    @RequestMapping(value = "{id}", method = RequestMethod.DELETE)
    int deleteByPrimaryKey(@PathVariable("id") Long id);

    @RequestMapping(value = "/", method = RequestMethod.POST, consumes = MediaType.APPLICATION_JSON_VALUE)
    Object insert(@RequestBody User t);

    @RequestMapping(value = "/", method = RequestMethod.PUT, consumes = MediaType.APPLICATION_JSON_VALUE)
    Object updateByPrimaryKey(@RequestBody User t);

}

//测试

@SpringBootTest(classes = ConsumerApplication.class)
@RunWith(SpringJUnit4ClassRunner.class)
public class UserServiceTest {

    @Autowired
    private UserService userService;

    @Test
    public void testSelectByPrimaryKey() {
        User user = userService.selectByPrimaryKey(1L);
        System.err.println(user);
    }

    @Test
    public void testInsert() {
        userService.insert(new User()
                .setUsername("test")
                .setPassword("123456")
                .setCreatedTime(new Date())
                .setAddress("北京市"));

    }

    @Test
    public void testUpdate(){
        userService.updateByPrimaryKey(new User()
                .setId(2L)
                .setUsername("test")
                .setPassword("123456")
                .setCreatedTime(new Date())
                .setAddress("北京市"));
    }

    @Test
    public void testDelete(){
        userService.deleteByPrimaryKey(1L);
    }
}

```


在application.properties添加Dubbo的版本信息和客户端超时信息,如下:

```
spring:
  application:
    name: dubbo-demo-consumer
  dubbo:
    application:
      name: ${spring.application.name}
    protocol:
      name: feign
    registry:
      protocol: zookeeper
      address: localhost:2181
    scan: com.example
```



*网关支持，支持聚合dubbo rest服务同时兼容springcloud rest代理
---

maven 依赖

```
 
     org.springframework.cloud 
     spring-cloud-starter-zuul 
 
```

启动类
```
@SpringBootApplication
@EnableDubboProxy
public class DubboApplication {

    public static void main(String[] args) {
        SpringApplication.run(DubboApplication.class, args);
    }
}
```
配置文件

```
spring:
  application:
    name: dubbo-application

  dubbo:
    application:
      name: ${spring.application.name}
    registry:
      protocol: hazelcast
      address: 224.5.6.7:1234
```

泛化代理Dubbo转换成rest

```

spring:
  application:
    name: dubbo-application

  dubbo:
    application:
      name: ${spring.application.name}
    registry:
      protocol: hazelcast
      address: 224.5.6.7:1234
    generic-prefix: /proxy

//rest请求示例 localhost:8100/proxy/
{
	"params":[1],
	"method":"com.example.service.UserService.selectByPrimaryKey",
	"version":"1.0.0"
}

//返回结果
{
  "jsonrpc": "2.0",
  "id": null,
  "result": "{\"id\":1,\"username\":\"wuyu\",\"createdTime\":1493775816000,\"address\":\"安徽省阜阳市\",\"class\":\"com.example.model.User\",\"password\":\"123456\"}"
}


```


演示样例
---

*https://git.oschina.net/wuyu15255872976/dubbo-demo-parent.git*


新增Hazelcast 注册中心
---

```
spring:
  application:
    name: dubbo-application

  dubbo:
    application:
      name: ${spring.application.name}
    registry:
      protocol: hazelcast
      address: 224.5.6.7:1234?managementCenter=http://localhost:8080/mancenter #managementCenter 是hazelcast监控地址，可以不填写
```




Hazelcast 监控中心
---

```
地址：https://hazelcast.org/download/

```

![](https://github.com/wu191287278/picture/blob/master/start-dubbo/1.png)
![](https://github.com/wu191287278/picture/blob/master/start-dubbo/2.png)
![](https://github.com/wu191287278/picture/blob/master/start-dubbo/3.png)
![](https://github.com/wu191287278/picture/blob/master/start-dubbo/4.png)
![](https://github.com/wu191287278/picture/blob/master/start-dubbo/5.png)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e99ff4146c7bc0723c7f98db24c1c6c50bceb51943e5ac70aff518804f2e6d77921e43fd372aa156fbe44f0f295f33a39191884093da47d7f47b2e0def1a8c926)