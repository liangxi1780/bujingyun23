[![Build Status](https://travis-ci.org/sqshq/PiggyMetrics.svg?branch=master)](https://travis-ci.org/sqshq/PiggyMetrics)
[![codecov.io](https://codecov.io/github/sqshq/PiggyMetrics/coverage.svg?branch=master)](https://codecov.io/github/sqshq/PiggyMetrics?branch=master)
[![GitHub license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/sqshq/PiggyMetrics/blob/master/LICENCE)
[![Join the chat at https://gitter.im/sqshq/PiggyMetrics](https://badges.gitter.im/sqshq/PiggyMetrics.svg)](https://gitter.im/sqshq/PiggyMetrics?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

# Piggy Metrics

**A simple way to deal with personal finances**

This is a [proof-of-concept application](http://u.720life.cn/g/a549d3194e5635a711697a2bb22b681cabba1d8f14bd892772ed4ccfaab7ad7d), which demonstrates [Microservice Architecture Pattern](http://u.720life.cn/g/d53e9a1490b9cb345039c58b05d2ff0fde46a8e7fc8b98c1261bd50dda824b923d63c4ce6ba0f0b0ca5e5554a60eaee3) using Spring Boot, Spring Cloud and Docker.
With a pretty neat user interface, by the way.

![](https://cloud.githubusercontent.com/assets/6069066/13864234/442d6faa-ecb9-11e5-9929-34a9539acde0.png)
![Piggy Metrics](https://cloud.githubusercontent.com/assets/6069066/13830155/572e7552-ebe4-11e5-918f-637a49dff9a2.gif)

## Functional services

PiggyMetrics was decomposed into three core microservices. All of them are independently deployable applications, organized around certain business domains.

 

#### Account service
Contains general user input logic and validation: incomes/expenses items, savings and account settings.

Method	| Path	| Description	| User authenticated	| Available from UI
------------- | ------------------------- | ------------- |:-------------:|:----------------:|
GET	| /accounts/{account}	| Get specified account data	|  | 	
GET	| /accounts/current	| Get current account data	| × | ×
GET	| /accounts/demo	| Get demo account data (pre-filled incomes/expenses items, etc)	|   | 	×
PUT	| /accounts/current	| Save current account data	| × | ×
POST	| /accounts/	| Register new account	|   | ×


#### Statistics service
Performs calculations on major statistics parameters and captures time series for each account. Datapoint contains values, normalized to base currency and time period. This data is used to track cash flow dynamics in account lifetime.

Method	| Path	| Description	| User authenticated	| Available from UI
------------- | ------------------------- | ------------- |:-------------:|:----------------:|
GET	| /statistics/{account}	| Get specified account statistics	          |  | 	
GET	| /statistics/current	| Get current account statistics	| × | × 
GET	| /statistics/demo	| Get demo account statistics	|   | × 
PUT	| /statistics/{account}	| Create or update time series datapoint for specified account	|   | 


#### Notification service
Stores users contact information and notification settings (like remind and backup frequency). Scheduled worker collects required information from other services and sends e-mail messages to subscribed customers.

Method	| Path	| Description	| User authenticated	| Available from UI
------------- | ------------------------- | ------------- |:-------------:|:----------------:|
GET	| /notifications/settings/current	| Get current account notification settings	| × | ×	
PUT	| /notifications/settings/current	| Save current account notification settings	| × | ×

#### Notes
- Each microservice has its own database, so there is no way to bypass API and access persistance data directly.
- In this project, I use MongoDB as a primary database for each service. It might also make sense to have a polyglot persistence architecture (сhoose the type of db that is best suited to service requirements).
- Service-to-service communication is quite simplified: microservices talking using only synchronous REST API. Common practice in a real-world systems is to use combination of interaction styles. For example, perform synchronous GET request to retrieve data and use asynchronous approach via Message broker for create/update operations in order to decouple services and buffer messages. However, this brings us to the [eventual consistency](http://u.720life.cn/g/d53e9a1490b9cb345039c58b05d2ff0fcf4009427f6c96b0ddcc5ed4f62b525f082c9c130545e8a44891d9bf725e7bef3c03b26547d5c0d0ee2fd6a866538cfab7dd2800909958054f723c031a009679) world.

## Infrastructure services
There's a bunch of common patterns in distributed systems, which could help us to make described core services work. [Spring cloud](http://u.720life.cn/g/e0845233bf5cae93142c4c8e1c8864d4e670a90f87afc2ad04fb4c1d1899c07f5e589ea1eb3c1de8cd6a344e91ef9caf) provides powerful tools that enhance Spring Boot applications behaviour to implement those patterns. I'll cover them briefly.
 
### Config service
[Spring Cloud Config](http://u.720life.cn/g/947e344a27d6d8817be37f0194b09df354861817a6bf36c77a9b933abdc46faa433f691cf52ea6097c8abcdcad7dab62947de49978badf14e416b67ce4dff075517560363ad4765a31f72af0c3fb7f66) is horizontally scalable centralized configuration service for distributed systems. It uses a pluggable repository layer that currently supports local storage, Git, and Subversion. 

In this project, I use `native profile`, which simply loads config files from the local classpath. You can see `shared` directory in [Config service resources](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aec0970e436528524885e225b5a4f12fd4093eef8201ec26b73c7debcc38181ab7b3055623f5be5a356ca4959862ff46eb5). Now, when Notification-service requests its configuration, Config service responses with `shared/notification-service.yml` and `shared/application.yml` (which is shared between all client applications).

##### Client side usage
Just build Spring Boot application with `spring-cloud-starter-config` dependency, autoconfiguration will do the rest.

Now you don't need any embedded properties in your application. Just provide `bootstrap.yml` with application name and Config service url:
```yml
spring:
  application:
    name: notification-service
  cloud:
    config:
      uri: http://config:8888
      fail-fast: true
```

##### With Spring Cloud Config, you can change app configuration dynamically. 
For example, [EmailService bean](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aecdc87a589acb78bb5fde4188041fd176c4ea947c4f04ea96a459bbe6ecb28f2a93b1d2bd19cc6e6899a944dc3375a8f4aac75c1534a6b56e48da2dda27b6449ced830971290c4378cbf2f04d93edb2945b98e5111fddb8f60f430a92a0568c4bd177f5ec247e50bb50de9a89e65c8a01e) was annotated with `@RefreshScope`. That means, you can change e-mail text and subject without rebuild and restart Notification service application.

First, change required properties in Config server. Then, perform refresh request to Notification service:
`curl -H "Authorization: Bearer #token#" -XPOST http://127.0.0.1:8000/notifications/refresh`

Also, you could use Repository [webhooks to automate this process](http://u.720life.cn/g/947e344a27d6d8817be37f0194b09df354861817a6bf36c77a9b933abdc46faa433f691cf52ea6097c8abcdcad7dab62947de49978badf14e416b67ce4dff0758f7049c449e306e871365ec16030927bf8bfe074a59a0813389b7a5b1c52b95558f2bf366d0fee3a618deb2520f6ca64)

##### Notes
- There are some limitations for dynamic refresh though. `@RefreshScope` doesn't work with `@Configuration` classes and doesn't affect `@Scheduled` methods
- `fail-fast` property means that Spring Boot application will fail startup immediately, if it cannot connect to the Config Service.
- There are significant [security notes](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aecccbbb71e1e7e0ab2cf3ca35ecd4bafad) below

### Auth service
Authorization responsibilities are completely extracted to separate server, which grants [OAuth2 tokens](http://u.720life.cn/g/a6fc20f29c5b3b6059eab4d4320b2e4d4c7598a0c7f5b34088e1beed2c40a0335115f0c056294c5edcd767144f5b309b) for the backend resource services. Auth Server is used for user authorization as well as for secure machine-to-machine communication inside a perimeter.

In this project, I use [`Password credentials`](http://u.720life.cn/g/a6fc20f29c5b3b6059eab4d4320b2e4d4c7598a0c7f5b34088e1beed2c40a033a7af9f2d7e0f80ef146be27d125cebd7) grant type for users authorization (since it's used only by native PiggyMetrics UI) and [`Client Credentials`](http://u.720life.cn/g/a6fc20f29c5b3b6059eab4d4320b2e4d4c7598a0c7f5b34088e1beed2c40a0336b7f0a835e9c703e71f163069251bd54) grant for microservices authorization.

Spring Cloud Security provides convenient annotations and autoconfiguration to make this really easy to implement from both server and client side. You can learn more about it in [documentation](http://u.720life.cn/g/947e344a27d6d8817be37f0194b09df354861817a6bf36c77a9b933abdc46faa64484fe4bdf36d886ab011f9a9385bc4ed9453a98667d04a385da231dd99bf8f1f5db00d8c1689be996774ca8937d151) and check configuration details in [Auth Server code](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aec0970e436528524885e225b5a4f12fd40fbd997dee6ee9facbcdc8b081ed37157b91da81132c65e9f3e7525d5b60cf23a11a60a1b06c29ce42b406a48be0979e61db1b31c44ae8f7cc1db1c6a43777713).

From the client side, everything works exactly the same as with traditional session-based authorization. You can retrieve `Principal` object from request, check user's roles and other stuff with expression-based access control and `@PreAuthorize` annotation.

Each client in PiggyMetrics (account-service, statistics-service, notification-service and browser) has a scope: `server` for backend services, and `ui` - for the browser. So we can also protect controllers from external access, for example:

``` java
@PreAuthorize("#oauth2.hasScope('server')")
@RequestMapping(value = "accounts/{name}", method = RequestMethod.GET)
public List  getStatisticsByAccountName(@PathVariable String name) {
	return statisticsService.findByAccountName(name);
}
```

### API Gateway
As you can see, there are three core services, which expose external API to client. In a real-world systems, this number can grow very quickly as well as whole system complexity. Actually, hundreds of services might be involved in rendering of one complex webpage.

In theory, a client could make requests to each of the microservices directly. But obviously, there are challenges and limitations with this option, like necessity to know all endpoints addresses, perform http request for each piece of information separately, merge the result on a client side. Another problem is non web-friendly protocols which might be used on the backend.

Usually a much better approach is to use API Gateway. It is a single entry point into the system, used to handle requests by routing them to the appropriate backend service or by invoking multiple backend services and [aggregating the results](http://u.720life.cn/g/97198f316c1244420730eea30f94c747a646151e443024e5afd3162106db7be43218aa82df3d274eb67c6ae814b5cdf2bbf9800ece18c5941f12ea0158b5c70b). Also, it can be used for authentication, insights, stress and canary testing, service migration, static response handling, active traffic management.

Netflix opensourced [such an edge service](http://u.720life.cn/g/97198f316c1244420730eea30f94c747a646151e443024e5afd3162106db7be49474067a3d71885928945a64be2c4c32bf5d02a55a3c4ae7e9ab0846cb658f5c5324c109b7379546c2a21800a0f758fd), and now with Spring Cloud we can enable it with one `@EnableZuulProxy` annotation. In this project, I use Zuul to store static content (ui application) and to route requests to appropriate microservices. Here's a simple prefix-based routing configuration for Notification service:

```yml
zuul:
  routes:
    notification-service:
        path: /notifications/**
        serviceId: notification-service
        stripPrefix: false

```

That means all requests starting with `/notifications` will be routed to Notification service. There is no hardcoded address, as you can see. Zuul uses [Service discovery](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aecdc87a589acb78bb5fde4188041fd176c3f5c960f3b5fb951079ade26de0ff6edd3b94cb598c32ef5c65b359f2a46e691) mechanism to locate Notification service instances and also [Circuit Breaker and Load Balancer](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aecdc87a589acb78bb5fde4188041fd176cac9e752a49308254df8b0d9c3513130c21fa0eabec10cc232da986fd5a011da34b5c8a5d44e02aa6da5debee7fde137be2ae9b9b7e9aa32cda5ecf42bb94459a), described below.

### Service discovery

Another commonly known architecture pattern is Service discovery. It allows automatic detection of network locations for service instances, which could have dynamically assigned addresses because of auto-scaling, failures and upgrades.

The key part of Service discovery is Registry. I use Netflix Eureka in this project. Eureka is a good example of the client-side discovery pattern, when client is responsible for determining locations of available service instances (using Registry server) and load balancing requests across them.

With Spring Boot, you can easily build Eureka Registry with `spring-cloud-starter-eureka-server` dependency, `@EnableEurekaServer` annotation and simple configuration properties.

Client support enabled with `@EnableDiscoveryClient` annotation an `bootstrap.yml` with application name:
``` yml
spring:
  application:
    name: notification-service
```

Now, on application startup, it will register with Eureka Server and provide meta-data, such as host and port, health indicator URL, home page etc. Eureka receives heartbeat messages from each instance belonging to a service. If the heartbeat fails over a configurable timetable, the instance will be removed from the registry.

Also, Eureka provides a simple interface, where you can track running services and a number of available instances: `http://localhost:8761`

### Load balancer, Circuit breaker and Http client

Netflix OSS provides another great set of tools. 

#### Ribbon
Ribbon is a client side load balancer which gives you a lot of control over the behaviour of HTTP and TCP clients. Compared to a traditional load balancer, there is no need in additional hop for every over-the-wire invocation - you can contact desired service directly.

Out of the box, it natively integrates with Spring Cloud and Service Discovery. [Eureka Client](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aecad2a0b76257ff175f4fd794be2b60fdb609f8b51c24d50d3f9657846850a3aa7) provides a dynamic list of available servers so Ribbon could balance between them.

#### Hystrix
Hystrix is the implementation of [Circuit Breaker pattern](http://u.720life.cn/g/d53e9a1490b9cb345039c58b05d2ff0ffe5e59e5fab08748e0757eda0279a570435c1d7f02336872c4b8f1886514fa7b745c0709c9ecbfabc77aea0cde432724), which gives a control over latency and failure from dependencies accessed over the network. The main idea is to stop cascading failures in a distributed environment with a large number of microservices. That helps to fail fast and recover as soon as possible - important aspects of fault-tolerant systems that self-heal.

Besides circuit breaker control, with Hystrix you can add a fallback method that will be called to obtain a default value in case the main command fails.

Moreover, Hystrix generates metrics on execution outcomes and latency for each command, that we can use to [monitor system behavior](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aecc8ed2e51103cd70b98c44bf7d6d1ef3e485e7ff6be49a582142a4b8ab97a927e).

#### Feign
Feign is a declarative Http client, which seamlessly integrates with Ribbon and Hystrix. Actually, with one `spring-cloud-starter-feign` dependency and `@EnableFeignClients` annotation you have a full set of Load balancer, Circuit breaker and Http client with sensible ready-to-go default configuration.

Here is an example from Account Service:

``` java
@FeignClient(name = "statistics-service")
public interface StatisticsServiceClient {

	@RequestMapping(method = RequestMethod.PUT, value = "/statistics/{accountName}", consumes = MediaType.APPLICATION_JSON_UTF8_VALUE)
	void updateStatistics(@PathVariable("accountName") String accountName, Account account);

}
```

- Everything you need is just an interface
- You can share `@RequestMapping` part between Spring MVC controller and Feign methods
- Above example specifies just desired service id - `statistics-service`, thanks to autodiscovery through Eureka (but obviously you can access any resource with a specific url)

### Monitor dashboard

In this project configuration, each microservice with Hystrix on board pushes metrics to Turbine via Spring Cloud Bus (with AMQP broker). The Monitoring project is just a small Spring boot application with [Turbine](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b7bcccfb7832580a41c9f19ed16d5d7545ba2ae7f34a17ef3b73ff0bd1c22d4b) and [Hystrix Dashboard](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304666137d055b4cfd58b3447d8fd46cd8a6f609e912598080d36137f234f7c78f1cd69d26f174e42242d808476be5dd0deb).

See below [how to get it up and running](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aec757bce64622d8f477fa1db0454ea9a9de4da08c282286f0f558f061d0aa695c8).

Let's see our system behavior under load: Account service calls Statistics service and it responses with a vary imitation delay. Response timeout threshold is set to 1 second.

 

 	|   |   |  
--- |--- |--- |--- |
| `0 ms delay` | `500 ms delay` | `800 ms delay` | `1100 ms delay`
| Well behaving system. The throughput is about 22 requests/second. Small number of active threads in Statistics service. The median service time is about 50 ms. | The number of active threads is growing. We can see purple number of thread-pool rejections and therefore about 30-40% of errors, but circuit is still closed. | Half-open state: the ratio of failed commands is more than 50%, the circuit breaker kicks in. After sleep window amount of time, the next request is let through. | 100 percent of the requests fail. The circuit is now permanently open. Retry after sleep time won't close circuit again, because the single request is too slow.

### Log analysis

Centralized logging can be very useful when attempting to identify problems in a distributed environment. Elasticsearch, Logstash and Kibana stack lets you search and analyze your logs, utilization and network activity data with ease.
Ready-to-go Docker configuration described [in my other project](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3f0e88420c4684e3980e0ebace54125e2bc0ba682241d07469251988f9b75789b).

### Distributed tracing

Analyzing problems in distributed systems can be difficult, for example, tracing requests that propagate from one microservice to another. It can be quite a challenge to try to find out how a request travels through the system, especially if you don't have any insight into the implementation of a microservice. Even when there is logging, it is hard to tell which action correlates to a single request.

[Spring Cloud Sleuth](http://u.720life.cn/g/484d775526c71402f16d1f30e64380d7cc584a736ba73bded688b81b39b4e3993b7a71a2a8909c7f0d6c025969ea2902) solves this problem by providing support for distributed tracing. It adds two types of IDs to the logging: traceId and spanId. The spanId represents a basic unit of work, for example sending an HTTP request. The traceId contains a set of spans forming a tree-like structure. For example, with a distributed big-data store, a trace might be formed by a PUT request. Using traceId and spanId for each operation we know when and where our application is as it processes a request, making reading our logs much easier. 

The logs are as follows, notice the `[appname,traceId,spanId,exportable]` entries from the Slf4J MDC:

```text
2018-07-26 23:13:49.381  WARN [gateway,3216d0de1384bb4f,3216d0de1384bb4f,false] 2999 --- [nio-4000-exec-1] o.s.c.n.z.f.r.s.AbstractRibbonCommand    : The Hystrix timeout of 20000ms for the command account-service is set lower than the combination of the Ribbon read and connect timeout, 80000ms.
2018-07-26 23:13:49.562  INFO [account-service,3216d0de1384bb4f,404ff09c5cf91d2e,false] 3079 --- [nio-6000-exec-1] c.p.account.service.AccountServiceImpl   : new account has been created: test
```

- *`appname`*: The name of the application that logged the span from the property `spring.application.name`
- *`traceId`*: This is an ID that is assigned to a single request, job, or action
- *`spanId`*: The ID of a specific operation that took place
- *`exportable`*: Whether the log should be exported to [Zipkin](http://u.720life.cn/g/cf45ebab08d11246d3cf0ea344832383200bf15968fa75116c8014490b19f8c1)

## Security

An advanced security configuration is beyond the scope of this proof-of-concept project. For a more realistic simulation of a real system, consider to use https, JCE keystore to encrypt Microservices passwords and Config server properties content (see [documentation](http://u.720life.cn/g/947e344a27d6d8817be37f0194b09df354861817a6bf36c77a9b933abdc46faa433f691cf52ea6097c8abcdcad7dab62947de49978badf14e416b67ce4dff07551b3dc142b5df4b178b9fb6c6a1deebd) for details).

## Infrastructure automation

Deploying microservices, with their interdependence, is much more complex process than deploying monolithic application. It is important to have fully automated infrastructure. We can achieve following benefits with Continuous Delivery approach:

- The ability to release software anytime
- Any build could end up being a release
- Build artifacts once - deploy as needed

Here is a simple Continuous Delivery workflow, implemented in this project:

 

In this [configuration](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aecdc87a589acb78bb5fde4188041fd176c1a11df63d93dd7eb895406395536e25d), Travis CI builds tagged images for each successful git push. So, there are always `latest` image for each microservice on [Docker Hub](http://u.720life.cn/g/ce46a7789a867c84732a8edd85365bef4e87be312190a843a2ca854d953de68e) and older images, tagged with git commit hash. It's easy to deploy any of them and quickly rollback, if needed.

## How to run all the things?

Keep in mind, that you are going to start 8 Spring Boot applications, 4 MongoDB instances and RabbitMq. Make sure you have `4 Gb` RAM available on your machine. You can always run just vital services though: Gateway, Registry, Config, Auth Service and Account Service.

#### Before you start
- Install Docker and Docker Compose.
- Export environment variables: `CONFIG_SERVICE_PASSWORD`, `NOTIFICATION_SERVICE_PASSWORD`, `STATISTICS_SERVICE_PASSWORD`, `ACCOUNT_SERVICE_PASSWORD`, `MONGODB_PASSWORD` (make sure they were exported: `printenv`)
- Make sure to build the project: `mvn package [-DskipTests]`

#### Production mode
In this mode, all latest images will be pulled from Docker Hub.
Just copy `docker-compose.yml` and hit `docker-compose up`

#### Development mode
If you'd like to build images yourself (with some changes in the code, for example), you have to clone all repository and build artifacts with maven. Then, run `docker-compose -f docker-compose.yml -f docker-compose.dev.yml up`

`docker-compose.dev.yml` inherits `docker-compose.yml` with additional possibility to build images locally and expose all containers ports for convenient development.

#### Important endpoints
- http://localhost:80 - Gateway
- http://localhost:8761 - Eureka Dashboard
- http://localhost:9000/hystrix - Hystrix Dashboard (Turbine stream link: `http://turbine-stream-service:8080/turbine/turbine.stream`)
- http://localhost:15672 - RabbitMq management (default login/password: guest/guest)

#### Notes
All Spring Boot applications require already running [Config Server](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f5c3ded7320b61d773303ed1484c7aeccb7d131b29fdcfc9561e6738d87b2ff35ce821c18e0c0512c88f0132ca4aa763) for startup. But we can start all containers simultaneously because of `depends_on` docker-compose option.

Also, Service Discovery mechanism needs some time after all applications startup. Any service is not available for discovery by clients until the instance, the Eureka server and the client all have the same metadata in their local cache, so it could take 3 heartbeats. Default heartbeat period is 30 seconds.

## Contributions are welcome!

PiggyMetrics is open source, and would greatly appreciate your help. Feel free to suggest and implement improvements.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eccc0a107eaec0d98447c61589af7b5e526f92b7036333567947dbbb9befb0e7eb42db9cc28667284553a111fb79f42525730d02173091b07090758691e164781)