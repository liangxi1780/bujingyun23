# Apache ZooKeeper [![Build Status](https://travis-ci.org/apache/zookeeper.svg?branch=master)](https://travis-ci.org/apache/zookeeper) [![Maven Central](https://img.shields.io/maven-central/v/org.apache.zookeeper/zookeeper)](https://zookeeper.apache.org/releases.html) [![License](https://img.shields.io/github/license/apache/zookeeper)](https://github.com/apache/zookeeper/blob/master/LICENSE.txt)
![alt text](https://zookeeper.apache.org/images/zookeeper_small.gif "ZooKeeper")

For the latest information about Apache ZooKeeper, please visit our website at:

   http://zookeeper.apache.org/

and our wiki, at:

   https://cwiki.apache.org/confluence/display/ZOOKEEPER

---------------------------
Packaging/release artifacts

Either downloaded from https://zookeeper.apache.org/releases.html or
found in zookeeper-assembly/target directory after building the project with maven.

    apache-zookeeper-[version].tar.gz

        Contains all the source files which can be built by running:
        mvn clean install

        To generate an aggregated apidocs for zookeeper-server and zookeeper-jute:
        mvn javadoc:aggregate
        (generated files will be at target/site/apidocs)

    apache-zookeeper-[version]-bin.tar.gz

        Contains all the jar files required to run ZooKeeper
        Full documentation can also be found in the docs folder

As of version 3.5.5, the parent, zookeeper and zookeeper-jute artifacts
are deployed to the central repository after the release
is voted on and approved by the Apache ZooKeeper PMC:

  https://repo1.maven.org/maven2/org/apache/zookeeper/zookeeper/

## Java 8

If you are going to compile with Java 1.8, you should use a
recent release at u211 or above.

# Contributing
We always welcome new contributors to the project! See [How to Contribute](http://u.720life.cn/g/acfc5b59532704bd6169598f69392ed2a6b808eac39329606d87b7e1789510dc38f45e3c4920674405187cea8b2d4789ea74291d2474dd32b762e48442ea9d038e2e80e2c2f19a80b4397e4c75e1f07f) for details on how to submit patch through pull request and our contribution workflow.





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e316c865c32dd716409866360117c10275385c385ec6481a8dc130da28d27bd9b5445c9bfbeb27c2c588a5089c056bc55)