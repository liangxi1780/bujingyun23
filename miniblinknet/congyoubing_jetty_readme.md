##Ketty
>基于netty实现的服务端Nio MVC业务开发平台，提供性能监控，日志分析，动态扩展的功能。

###ketty-srv模块
>基于netty实现支持自定义协议扩展的Nio MVC高性能业务框架

####协议
- Http
- Ketty(自定义私有协议)


####基于注解的 mvc

- @Inject注入
- @Path 路径支持
- @Param参数自动注入value

####支持方法调用频率限制RateLimiter

``` java
@Action
public class SimpleAction {

    @Inject
    private UserService userService;

    // 每秒最多可调用100次，超过100次丢弃，
	@Rate(value=100)
	@Interceptor(id = "echoInterceptor")
    @Path
    public User getUserByUid(@Param String uid) {
        return userService.getUserByUid(uid);
    }
}

```

####拦截器 example
``` java
@Around
public class EchoInterceptor extends BaseInterceptor {

    private final static Logger LOGGER = LoggerFactory.getLogger(EchoInterceptor.class);

    @Override
    public boolean before() {
        LOGGER.info("==============EchoInterceptor before=========");
        return true;
    }

    @Override
    public boolean after() {
        LOGGER.info("==============EchoInterceptor after=========");
        return true;
    }
}
```

#### KettyServer example
``` java
// nio mvc 业务server启动类example
new KettyServer.Builder()
                .tcpNoDelay(true)
                .soKeepAlive(true)
                .setHttpProtocol()
                .host("localhost")
                .port(8888)
                .build()
                .start();

// 测试jetty客户端
public class JettClientTest {
	public static ClientSender clientSender = new ClientSender("localhost", 8888);
	public static void main(String[] args) throws Exception {
		KettyRequest request = new KettyRequest();
		request.setUri("/simpleAction/getUserByUid");
		JSONObject params = new JSONObject();
		params.put("uid", "12345677");
		request.setParameter(params);
		String result = clientSender.sendAndWait(request);
		System.out.println("result : " + result);
	}
}
```

#### HttpServer example
``` java
// nio mvc 业务server启动类example
public class SimpleServer {
    public static void main(String[] args) throws Exception {
         new KettyServer.Builder()
                        .setKettyProtocol()
                        .port(8888)
                        .build()
                        .start();
    }
}

```
####TODO 

- 支持自定义协议扩展
- 安全验证
- 性能优化
- WebSocket协议的实现

###ketty-client模块
>KettyServer高可用NIO客户端

####High availability
支持多个节点，节点不可用自动移除

#### Client pool
支持连接池

#### 断链自动重连

#### 自动维护心跳

###ketty-codec模块
>编解码框架

####KettyRequest

 
 
	 header 
	 body 
 
 	
	 size 
	 len 
	 uri 
	 msgId 
	 paramsMap 
	 body 
 
 	
	 short(2byte) 
	 short(2byte) 
	 string 
	 int(4byte) 
	 map 
	 JSONString 
 
 

####KettyResponse

 
 
	 header 
	 body 
 
 	
	 size 
	 len 
	 msgId(消息id) 
	 resCode(消息返回码) 
	 body 
 
 	
	 short(2byte) 
	 short(2byte) 
	 int(4byte) 
	 short(2byte) 
	 JSONString 
 
 

###ketty-router模块
>服务代理模块，提供路由分发功能

###ketty-monitor模块
>性能监控
>报警

###ketty-analysis模块
>接口统计分析
>智能推荐

[READ MORE](http://u.720life.cn/g/ac384fa62cc301d561adc7988a6e325a55c804d4d8f0c7843031a8c1ab886e90)






 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e53a122aa334a30ff29cc44ca42dde37e67b9b304ea95a2d818d35ba5859605a26fefc589bb35d449404b0f7639511d57)