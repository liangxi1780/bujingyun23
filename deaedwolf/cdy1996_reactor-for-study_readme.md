# Reactor Core

[![Join the chat at https://gitter.im/reactor/reactor](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/reactor/reactor?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Reactor Core](https://maven-badges.herokuapp.com/maven-central/io.projectreactor/reactor-core/badge.svg?style=plastic)](https://mvnrepository.com/artifact/io.projectreactor/reactor-core) [![Latest](https://img.shields.io/github/release/reactor/reactor-core/all.svg)]() 

[![Download](https://api.bintray.com/packages/spring/jars/io.projectreactor/images/download.svg)](https://bintray.com/spring/jars/io.projectreactor/_latestVersion)

[![Travis CI](https://travis-ci.org/reactor/reactor-core.svg?branch=master)](https://travis-ci.org/reactor/reactor-core)
[![Codecov](https://img.shields.io/codecov/c/github/reactor/reactor-core.svg)]()
[![Code Quality: Java](https://img.shields.io/lgtm/grade/java/g/reactor/reactor-core.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/reactor/reactor-core/context:java)
[![Total Alerts](https://img.shields.io/lgtm/alerts/g/reactor/reactor-core.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/reactor/reactor-core/alerts)


Non-Blocking [Reactive Streams](http://u.720life.cn/g/db79766f6cf64555e79ec7e7300d90a40cb8657f3ae380d6a8bef28f353f197e03f595347166df745fccb093856e900d) Foundation for the JVM both implementing a [Reactive Extensions](http://u.720life.cn/g/41f537c76e0fca6d89f20fcdbe04b06cee19310ea436df1e74018e79fc3294a6) inspired API and efficient event streaming support.

The `master` branch is now dedicated to development of the `3.3.x` line.

## Getting it
   
**Reactor 3 requires Java 8 or + to run**.

With Gradle from repo.spring.io or Maven Central repositories (stable releases only):

```groovy
    repositories {
//      maven { url 'https://repo.spring.io/snapshot' }
//      maven { url 'https://repo.spring.io/milestone' }
      mavenCentral()
    }

    dependencies {
      //compile "io.projectreactor:reactor-core:3.3.2.BUILD-SNAPSHOT"
      //testCompile("io.projectreactor:reactor-test:3.3.2.BUILD-SNAPSHOT")
      compile "io.projectreactor:reactor-core:3.3.1.RELEASE"
      testCompile("io.projectreactor:reactor-test:3.3.1.RELEASE")
    }
```

See the [reference documentation](http://u.720life.cn/g/431f84fb101dc06b5be76fd425d522b821af90a855ccf3949daf30081018916a1d2802d664b62a216f63c64bc70b690353c350447cc79886d6faf2679f62616d9695b6472ae128538fe14d4a795c787d)
for more information on getting it (eg. using Maven, or on how to get milestones and snapshots).

> **Note about Android support**: Reactor 3 doesn't officially support nor target Android.
However it should work fine with Android SDK 26 (Android O) and above. See the
[complete note](http://u.720life.cn/g/431f84fb101dc06b5be76fd425d522b821af90a855ccf3949daf30081018916a1d2802d664b62a216f63c64bc70b690353c350447cc79886d6faf2679f62616df8a2ef8d4bb9f8e521d318cdc9cbad53330c57974e5ba9dd972b5c6c80831040)
in the reference guide.

## Trouble importing the project in IDE?
Since the introduction of Java 9 stubs in order to optimize the performance of debug backtraces, one can sometimes
encounter cryptic messages from the build system when importing or re-importing the project in their IDE.

For example: 

 - `package StackWalker does not exist`: probably building under JDK8 but `java9stubs` was not added to sources
 - `cannot find symbol @CallerSensitive`: probably building with JDK11+ and importing using JDK8

When encountering these issues, one need to ensure that:

 - Gradle JVM matches the JDK used by the IDE for the modules (in IntelliJ, `Modules Settings` JDK). Preferably, 1.8.
 - The IDE is configured to delegate build to Gradle (in IntelliJ: `Build Tools > Gradle > Runner` and project setting uses that default)
 
Then rebuild the project and the errors should disappear.

## Getting Started

New to Reactive Programming or bored of reading already ? Try the [Introduction to Reactor Core hands-on](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046747c816bdc4328cf0be22ee61f2d170f2ff8e035ab24b351b6ef948c4fadd522) !

If you are familiar with RxJava or if you want to check more detailed introduction, be sure to check 
https://www.infoq.com/articles/reactor-by-example !

## Flux

A Reactive Streams Publisher with basic flow operators.
- Static factories on Flux allow for source generation from arbitrary callbacks types.
- Instance methods allows operational building, materialized on each subscription (_Flux#subscribe()_, ...) or multicasting operations (such as _Flux#publish_ and _Flux#publishNext_).

[ ](http://u.720life.cn/g/431f84fb101dc06b5be76fd425d522b821af90a855ccf3949daf30081018916a4582b952d2596e06d2502a3c5681f3275f8d97995db28037051916a5997839d0a735a9e424fbff2e1645661056ea1f8e)

Flux in action :
```java
Flux.fromIterable(getSomeLongList())
    .mergeWith(Flux.interval(100))
    .doOnNext(serviceA::someObserver)
    .map(d -> d * 2)
    .take(3)
    .onErrorResume(errorHandler::fallback)
    .doAfterTerminate(serviceM::incrementTerminate)
    .subscribe(System.out::println);
```

## Mono
A Reactive Streams Publisher constrained to *ZERO* or *ONE* element with appropriate operators. 
- Static factories on Mono allow for deterministic *zero or one* sequence generation from arbitrary callbacks types.
- Instance methods allows operational building, materialized on each _Mono#subscribe()_ or _Mono#get()_ eventually called.

[ ](http://u.720life.cn/g/431f84fb101dc06b5be76fd425d522b821af90a855ccf3949daf30081018916a4582b952d2596e06d2502a3c5681f3275f8d97995db28037051916a5997839d0b4dd59db4b83cb36122e5ed75ec04880)

Mono in action :
```java
Mono.fromCallable(System::currentTimeMillis)
    .flatMap(time -> Mono.first(serviceA.findRecent(time), serviceB.findRecent(time)))
    .timeout(Duration.ofSeconds(3), errorHandler::fallback)
    .doOnSuccess(r -> serviceM.incrementSuccess())
    .subscribe(System.out::println);
```

Blocking Mono result :
```java    
Tuple2  nowAndLater = 
        Mono.zip(
                Mono.just(System.currentTimeMillis()),
                Flux.just(1).delay(1).map(i -> System.currentTimeMillis()))
            .block();
```

## Schedulers

Reactor uses a [Scheduler](http://u.720life.cn/g/431f84fb101dc06b5be76fd425d522b821af90a855ccf3949daf30081018916a4582b952d2596e06d2502a3c5681f327c62b78ab9b25a15b19c2fa32e9347539ece74ea20c65454a6b777c4c9d3a40b7a82bc663b11bc90cc8524f02af893061) as a
contract for arbitrary task execution. It provides some guarantees required by Reactive
Streams flows like FIFO execution.

You can use or create efficient [schedulers](http://u.720life.cn/g/431f84fb101dc06b5be76fd425d522b821af90a855ccf3949daf30081018916a4582b952d2596e06d2502a3c5681f327c62b78ab9b25a15b19c2fa32e9347539ece74ea20c65454a6b777c4c9d3a40b7bf1c747a2b94f45d136a724a5441fe03)
to jump thread on the producing flows (subscribeOn) or receiving flows (publishOn):

```java

Mono.fromCallable( () -> System.currentTimeMillis() )
	.repeat()
    .publishOn(Schedulers.single())
    .log("foo.bar")
    .flatMap(time ->
        Mono.fromCallable(() -> { Thread.sleep(1000); return time; })
            .subscribeOn(Schedulers.parallel())
    , 8) //maxConcurrency 8
    .subscribe();
```

## ParallelFlux

[ParallelFlux](http://u.720life.cn/g/431f84fb101dc06b5be76fd425d522b821af90a855ccf3949daf30081018916a4582b952d2596e06d2502a3c5681f3275f8d97995db28037051916a5997839d0c413c5ce1a2c159ae7794a8259aea6861c432d9b9dfccbe3239bfc158af6b985) can starve your CPU's from any sequence whose work can be subdivided in concurrent
 tasks. Turn back into a `Flux` with `ParallelFlux#sequential()`, an unordered join or
 use arbitrary merge strategies via 'groups()'.

```java
Mono.fromCallable( () -> System.currentTimeMillis() )
	.repeat()
    .parallel(8) //parallelism
    .runOn(Schedulers.parallel())
    .doOnNext( d -> System.out.println("I'm on thread "+Thread.currentThread()) )
    .subscribe()
```


## Custom sources : Flux.create and FluxSink, Mono.create and MonoSink
To bridge a Subscriber or Processor into an outside context that is taking care of
producing non concurrently, use `Flux#create`, `Mono#create`.

```java
Flux.create(sink -> {
         ActionListener al = e -> {
            sink.next(textField.getText());
         };

         // without cancellation support:
         button.addActionListener(al);

         // with cancellation support:
         sink.onCancel(() -> {
         	button.removeListener(al);
         });
    },
    // Overflow (backpressure) handling, default is BUFFER
    FluxSink.OverflowStrategy.LATEST)
    .timeout(3)
    .doOnComplete(() -> System.out.println("completed!"))
    .subscribe(System.out::println)
```

## The Backpressure Thing

Most of this cool stuff uses bounded ring buffer implementation under the hood to mitigate signal processing difference between producers and consumers. Now, the operators and processors or any standard reactive stream component working on the sequence will be instructed to flow in when these buffers have free room AND only then. This means that we make sure we both have a deterministic capacity model (bounded buffer) and we never block (request more data on write capacity). Yup, it's not rocket science after all, the boring part is already being worked by us in collaboration with [Reactive Streams Commons](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046771a5290ff6264142d2ce80cfff5b3af40930c242efdac86c6936be648bcb2d8a7f66b807793304d46d6549b4095d6e4) on going research effort.

## What's more in it ?

"Operator Fusion" (flow optimizers), health state observers, helpers to build custom reactive components, bounded queue generator, converters from/to Java 9 Flow, Publisher and Java 8 CompletableFuture. The repository contains a `reactor-test` project with test features like the [`StepVerifier`](http://u.720life.cn/g/431f84fb101dc06b5be76fd425d522b836814e3b035f2475d2c66bf4a60822fc0b11974e71c9567b6017bd8921256044d45d1eaee534cd145f552a12373c2f021c15a0797b74bf4d15fccda23621287d336a9ec084a550e5c20c4fa986ebad5f).

-------------------------------------

## Reference Guide
https://projectreactor.io/docs/core/release/reference/docs/index.html

## Javadoc
https://projectreactor.io/docs/core/release/api/

## Getting started with Flux and Mono
https://github.com/reactor/lite-rx-api-hands-on

## Reactor By Example
https://www.infoq.com/articles/reactor-by-example

## Head-First Spring & Reactor
https://github.com/reactor/head-first-reactive-with-spring-and-reactor/

## Beyond Reactor Core
- Everything to jump outside the JVM with the non-blocking drivers from [Reactor Netty](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046771a5290ff6264142d2ce80cfff5b3af260fe79862da85f2af7188324ef8f223).
- [Reactor Addons](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046771a5290ff6264142d2ce80cfff5b3af91e077bfb27a1580192ae2b68d4f21e8) provide for adapters and extra operators for Reactor 3.

-------------------------------------
_Powered by [Reactive Streams Commons](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046771a5290ff6264142d2ce80cfff5b3af40930c242efdac86c6936be648bcb2d8a7f66b807793304d46d6549b4095d6e4)_

_Licensed under [Apache Software License 2.0](www.apache.org/licenses/LICENSE-2.0)_

_Sponsored by [Pivotal](http://u.720life.cn/g/fd4389830ebca1c86423ff34b559c5af5e3dd75b1f7110c685fe6ea7093339d8)_




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5fbce7c85a97dab489e2e47f604476f813bde085c01558abb55c0670937b8c79870e78e7fb10bc356f8de133b180077275080cdddfda909a1828a8d3a3a495f5)