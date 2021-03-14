# [Soul](http://u.720life.cn/g/5ee55c6789b370b66433a3efa30e7f383a6ef09e3aeac90ff3db18611de66b56)

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/4367ffad5b434b7e8078b3a68cc6398d)](https://www.codacy.com/app/yu199195/soul?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Dromara/soul&amp;utm_campaign=Badge_Grade)
[![Total lines](https://tokei.rs/b1/github/Dromara/soul?category=lines)](https://github.com/Dromara/soul)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg?label=license)](https://github.com/Dromara/soul/blob/master/LICENSE)
[![Build Status](https://travis-ci.org/Dromara/soul.svg?branch=master)](https://travis-ci.org/Dromara/soul)
[![Maven Central](https://img.shields.io/maven-central/v/org.dromara/soul.svg?label=maven%20central)](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22org.dromara%22%20AND%soul)
[![QQ群](https://img.shields.io/badge/chat-on%20QQ-ff69b4.svg?style=flat-square)](https://shang.qq.com/wpa/qunwpa?idkey=03bbb6f74b3257989316c0a8cf07cec117314dbdfe4fa7a20870b298b7db2c3b)

### Reactive gateway based on webflux

# Architecture
 
 ![](https://yu199195.github.io/images/soul/soul-framework.png)  
  
# Execution Flow
 
 ![](https://yu199195.github.io/images/soul/soul-handler.png)
  
# Modules

 * soul-admin : Plug-in and other information configuration management background
 
 * soul-bootstrap : With the startup project, users can refer to
 
 * soul-common :  Framework common class
 
 * soul-configuration : zookeeper configuration project
 
 * soul-spring-boot-starter : Support for the spring boot starter
 
 * soul-web : Core processing packages include plug-ins, request routing and forwarding, and so on
 
 * soul-extend-demo : Demo of the extension point
 
 * soul-test : the rpc test project

# Features

   * It provides plugins such as current limiting, fusing, forwarding, routing monitoring and so on.
   
   * Seamless docking with HTTP,Restful,websocket,dubbo and springcloud.
   
   * Plug-in hot plug, users can customize the development.
   
   * Selectors and rules are dynamically configured for flexible matching.

   * Support for cluster deployment.
   
   * Support A/B test and grayscale publishing。
   

# Plugin

 Whenever a request comes in ,Soul Execute all open plug-ins through the chain of responsibility.
 
 Plugins are the heart of soul And plug-ins are extensible and hot-pluggable.
 
 Different plug-ins do different things 
 
 Of course, users can also customize plug-ins to meet their own needs.
 
 If you want to customize, see [plugin-extend](http://u.720life.cn/g/5ee55c6789b370b66433a3efa30e7f38531e7a7619097dd52043655c701ad31d9b7f34ec52442dc6c1fe4fd270da26ec712ee2b5fbc342aa1b29812ded056e14)
 

# Selector & rule 

  According to your HTTP request headers, selectors and rules are used to route your requests.
  
  Selector is your first route, It is coarser grained, for example, at the module level.
  
  Rule is your second route and what do you think your request should do,For example a method level in a module.
  
  The selector and the rule match only once, and the match is returned. So the coarsest granularity should be sorted last.
   
  
# Data Caching 
 
  All data is cached HashMap in the JVM So it's very fast.
  
  When the user is managing changes in the background,
  
  Soul dynamically updates the cache by listening to the zookeeper node.
  
  This solution might rely on zookeeper,It may be replaced in the future [issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464c882a0181b9511255551d53d709edf6de33b4c248c84f3c7485cb6157ad8077)
  
  Node design for zookeeper [zookeeper-node](http://u.720life.cn/g/5ee55c6789b370b66433a3efa30e7f38531e7a7619097dd52043655c701ad31d236c226d4d1823060b31ae40697d89efb3cbb67c15f4d146131343392c053443)
 

# Prerequisite
 
   * JDK 1.8+

   * Zookeeper
   
   * Mysql
   
# About
  
   Soul Has been used in our production environment,Its performance and flexibility allow us to use up very cool.
   
   In double 11, we deployed 6 clusters, which supported a large volume of our business.
   
   If you want to use it, you can see [Quick Start](http://u.720life.cn/g/5ee55c6789b370b66433a3efa30e7f38531e7a7619097dd52043655c701ad31d9ba2db40dd44060dfbba25d5043daccfff6cb61c6ed4cb04ac23f13911ba6bbd)
     
# Stargazers over time

[![Stargazers over time](https://starchart.cc/Dromara/soul.svg)](https://starchart.cc/Dromara/soul)

  
# Support

 ![](https://yu199195.github.io/images/soul-qq.png)
  



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5467d3b56166ffc74d3755315fa84a0cb3c1b76d0204b4c10553d8cc2aec302ab5065c0fd6caba43880789e9638debdc)