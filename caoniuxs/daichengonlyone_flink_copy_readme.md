# Apache Flink

Apache Flink is an open source stream processing framework with powerful stream- and batch-processing capabilities.

Learn more about Flink at [http://flink.apache.org/](http://u.720life.cn/g/dea64e15c9807a3937ec984a38d1ea4c2e62251a26422febe687526069132b35)


### Features

* A streaming-first runtime that supports both batch processing and data streaming programs

* Elegant and fluent APIs in Java and Scala

* A runtime that supports very high throughput and low event latency at the same time

* Support for *event time* and *out-of-order* processing in the DataStream API, based on the *Dataflow Model*

* Flexible windowing (time, count, sessions, custom triggers) accross different time semantics (event time, processing time)

* Fault-tolerance with *exactly-once* processing guarantees

* Natural back-pressure in streaming programs

* Libraries for Graph processing (batch), Machine Learning (batch), and Complex Event Processing (streaming)

* Built-in support for iterative programs (BSP) in the DataSet (batch) API

* Custom memory management for efficient and robust switching between in-memory and out-of-core data processing algorithms

* Compatibility layers for Apache Hadoop MapReduce and Apache Storm

* Integration with YARN, HDFS, HBase, and other components of the Apache Hadoop ecosystem


### Streaming Example
```scala
case class WordWithCount(word: String, count: Long)

val text = env.socketTextStream(host, port, '\n')

val windowCounts = text.flatMap { w => w.split("\\s") }
  .map { w => WordWithCount(w, 1) }
  .keyBy("word")
  .timeWindow(Time.seconds(5))
  .sum("count")

windowCounts.print()
```

### Batch Example
```scala
case class WordWithCount(word: String, count: Long)

val text = env.readTextFile(path)

val counts = text.flatMap { w => w.split("\\s") }
  .map { w => WordWithCount(w, 1) }
  .groupBy("word")
  .sum("count")

counts.writeAsCsv(outputPath)
```



## Building Apache Flink from Source

Prerequisites for building Flink:

* Unix-like environment (We use Linux, Mac OS X, Cygwin)
* git
* Maven (we recommend version 3.0.4)
* Java 7 or 8

```
git clone https://github.com/apache/flink.git
cd flink
mvn clean package -DskipTests # this will take up to 10 minutes
```

Flink is now installed in `build-target`

*NOTE: Maven 3.3.x can build Flink, but will not properly shade away certain dependencies. Maven 3.0.3 creates the libraries properly.
To build unit tests with Java 8, use Java 8u51 or above to prevent failures in unit tests that use the PowerMock runner.*

## Developing Flink

The Flink committers use IntelliJ IDEA to develop the Flink codebase.
We recommend IntelliJ IDEA for developing projects that involve Scala code.

Minimal requirements for an IDE are:
* Support for Java and Scala (also mixed projects)
* Support for Maven with Java and Scala


### IntelliJ IDEA

The IntelliJ IDE supports Maven out of the box and offers a plugin for Scala development.

* IntelliJ download: [https://www.jetbrains.com/idea/](http://u.720life.cn/g/a27ddb2b79548d3a829f3f0224b2480d40c182108896ad3a7f25af80b989b1a9)
* IntelliJ Scala Plugin: [http://plugins.jetbrains.com/plugin/?id=1347](http://u.720life.cn/g/969ae97881968ae936a4e6fc79778647d934c238838914d3f5264c2d8888a00c7b4faf95633d277bb57dca77660a9928)

Check out our [Setting up IntelliJ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466657e5f688d6e19bf17c0af1d61b051dc301ccbe9ed6af20a334ef3a7c75a9ee5cb01a0fadd7ef1b379cb47c56c1988669caa226d6385e45160aa2379b377d2e95869dea3dc16a6b1b4588c3c7fae6bf) guide for details.

### Eclipse Scala IDE

**NOTE:** From our experience, this setup does not work with Flink
due to deficiencies of the old Eclipse version bundled with Scala IDE 3.0.3 or
due to version incompatibilities with the bundled Scala version in Scala IDE 4.4.1.

**We recommend to use IntelliJ instead (see above)**

## Support

Don’t hesitate to ask!

Contact the developers and community on the [mailing lists](http://u.720life.cn/g/dea64e15c9807a3937ec984a38d1ea4c8c6ddacecd71b2b31c99f2ac6a0e0147968bb3f8411a7a67e062bb12dbfaccd8cb5c11a416c629d24dda5532f0f16039) if you need any help.

[Open an issue](http://u.720life.cn/g/abb328ad6e20e28badb9d5d395ec0d58d08c12e8dce696c6fa88a6321ed29219fac1fcefbc5352b58e1940a51db35bdd) if you found a bug in Flink.


## Documentation

The documentation of Apache Flink is located on the website: [http://flink.apache.org](http://u.720life.cn/g/dea64e15c9807a3937ec984a38d1ea4c48541b81b26e0940e7252fa9598ae17d)
or in the `docs/` directory of the source code.


## Fork and Contribute

This is an active open-source project. We are always open to people who want to use the system or contribute to it. 
Contact us if you are looking for implementation tasks that fit your skills.
This article describes [how to contribute to Apache Flink](http://u.720life.cn/g/dea64e15c9807a3937ec984a38d1ea4cb89e95c607cd5ead1f67df238b7a76af8f201a236fac04b91153ecbeb61dd8d7).


## About

Apache Flink is an open source project of The Apache Software Foundation (ASF).
The Apache Flink project originated from the [Stratosphere](http://u.720life.cn/g/7291b492c726423cce5f412d68f0fc9cf1c6d70cf493434df0fe7d3b1a39c551) research project.




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2db56a3b648d67d38151008df1f0b948f31ceabc8a4ea6eac4e5ba7f0f96a7cc5831837150aa418698ed231aa86977f1fe2b60415a2ff6e01e8e813b622d44af)