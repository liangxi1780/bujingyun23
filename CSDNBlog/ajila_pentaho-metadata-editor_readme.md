# pentaho-metadata-editor #

### Project Structure

* **assemblies:** 
Project distribution archive is produced under this module
* **editor:** 
Pentaho Metadata Editor library artifact

How to build
--------------

pentaho-metadata-editor uses the maven framework.


#### Pre-requisites for building the project:
* Maven, version 3+
* Java JDK 1.8
* This [settings.xml](http://u.720life.cn/g/bb9e19de933fd87f05600116164183c0b3ddd62d3854e3432c88c12f9e59c6626409c97f395ea682dd11ab9241c6a5abad2e3b55764a1569390def9a16e8d1c4ab6ef88db0131164520a130f318be33932def9b9cd2a974d8d79574edad9264ecac9c6460d4439db2abe20110fd8c68a) in your  /.m2 directory

#### Building it

This is a maven project, and to build it use the following command

```
$ mvn clean install
```

Optionally you can specify -Dmaven.test.skip=true to skip the tests (even though
you shouldn't as you know)

The build result will be a Pentaho package located in ```target```.

#### Running the tests

__Unit tests__

This will run all unit tests in the project (and sub-modules).

```
$ mvn test
```

If you want to remote debug a single java unit test (default port is 5005):

```
$ cd core
$ mvn test -Dtest= > -Dmaven.surefire.debug
```

To skip test

```
$ mvn clean install -DskipTests
```

To get log as text file

```
$ mvn clean install test >log.txt
```


__IntelliJ__

* Don't use IntelliJ's built-in maven. Make it use the same one you use from the commandline.
  * Project Preferences -> Build, Execution, Deployment -> Build Tools -> Maven ==> Maven home directory



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb79a453e00ba05cfe51b2a1490ee1a15d7def415ed32f2bd8b999d863c02c645311b9cd09ee450057ea7670ef6765495a918f92be5e8847ea807898a6f5e3e41)