[简体中文](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462e481b4b06e8e794e91fc258aaf1462b5d7984fb725865e30af4fc8332745b5cf89bc3431882d6e0e5ebf3b26d6a22e2656486bdef9aa4ef9fdb56614789efaf)

# Jenkins CLI

[![Go Report Card][go-report-card-badge]][go-report-card-url]
[![Quality Gate Status][sonar-badge]][sonar-link]
[![GoDoc][godoc-badge]][godoc-url]
![Sonar Coverage](https://img.shields.io/sonar/coverage/jenkins-zh_jenkins-cli?server=https%3A%2F%2Fsonarcloud.io)
[![Travis](https://img.shields.io/travis/jenkins-zh/jenkins-cli.svg?logo=travis&label=build&logoColor=white)](https://travis-ci.org/jenkins-zh/jenkins-cli)
[![Contributors](https://img.shields.io/github/contributors/jenkins-zh/jenkins-cli.svg)](https://github.com/jenkins-zh/jenkins-cli/graphs/contributors)
[![GitHub release](https://img.shields.io/github/release/jenkins-zh/jenkins-cli.svg?label=release)](https://github.com/jenkins-zh/jenkins-cli/releases/latest)
![GitHub All Releases](https://img.shields.io/github/downloads/jenkins-zh/jenkins-cli/total)
[![Docker Pulls](https://img.shields.io/docker/pulls/jenkinszh/jcli.svg)](https://hub.docker.com/r/jenkinszh/jcli/tags)
![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/jenkins-zh/jenkins-cli)
[![Gitter](https://badges.gitter.im/jenkinsci/jenkins-cli.svg)](https://gitter.im/jenkinsci/jenkins-cli?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Jenkins CLI allows you manage your Jenkins in an easy way. No matter if you're a plugin
developer, administrator or just a regular user, it is made for you!

# Features

* Multiple Jenkins support
* Plugins management (list, search, install, upload)
* Job management (search, build, log)
* Open your Jenkins with a browser
* Restart your Jenkins
* Connection with proxy support

# Get it

We support Mac, Linux and Windows for now.

## Mac

You can use `brew` to install jcli.
```
brew tap jenkins-zh/jcli
brew install jcli
```

## Linux

To install `jcli` on your Linux OS, execute the following command:
```
curl -L https://github.com/jenkins-zh/jenkins-cli/releases/latest/download/jcli-linux-amd64.tar.gz|tar xzv
sudo mv jcli /usr/local/bin/
```

## Windows

You can find the latest version [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462e481b4b06e8e794e91fc258aaf1462b3b239df3350a39c4ceca7b89f99966acf998214c147ba39f0fb5c5462811ced93765e69cbe0de4e14d2d3778ea038cbcff88921f99d9ddebb0fa736941d94ee8). Download the tar file and copy the uncompressed `jcli` directory into your system path.

## Other package managers

Here are other package managers:

* [GoFish](http://u.720life.cn/g/dbb76656c1a2b908d7f15f704703cdac) users can use `gofish install jcli`
* [Scoop](http://u.720life.cn/g/07086b44341f50347c09864bb5b86824c148beb2e23bbf8280773976d0a961fb) users can use `scoop install jcli`

If you cannot download `jcli` from GitHub, please try the following ways:

`jcli_id=$(docker create jenkinszh/jcli) && sudo docker cp $jcli_id:/usr/local/bin/jcli /usr/local/bin/jcli && docker rm -v $jcli_id`

Download different version of OS? Just need to change the docker image tag:

|image|description|
|---|---|
|`jenkinszh/jcli`|Linux|
|`jenkinszh/jcli:darwin`|Mac|
|`jenkinszh/jcli:win`|Windows, you can find it from `/usr/local/bin/jcli.exe`|
|`jenkinszh/jcli:dev`|Developing version, find can find them from `/bin/linux/jcli` or `/bin/darwin/jcli` or `/bin/windows/jcli.exe`|

Want to try the latest features? Download the developing version of different platform:

- `jcli_id=$(docker create jenkinszh/jcli:dev) && sudo docker cp $jcli_id:/bin/linux/jcli . && docker rm -v $jcli_id`
- `jcli_id=$(docker create jenkinszh/jcli:dev) && sudo docker cp $jcli_id:/bin/darwin/jcli . && docker rm -v $jcli_id`
- `jcli_id=$(docker create jenkinszh/jcli:dev) && sudo docker cp $jcli_id:/bin/windows/jcli.exe . && docker rm -v $jcli_id`

# Get started

Read [this document](doc/README.md) for more details on how to use `jcli`.

# Contribution

If you're interested in this project. Please go through the
[contribution guide](CONTRIBUTING.md). Any contributions are welcome.

Thanks to JetBrains for giving us the open source licence.  
[![goland.svg](https://raw.githubusercontent.com/jenkins-zh/jenkins-cli/master/goland.svg)](https://www.jetbrains.com/?from=jenkins-cli)

# Stargazers over time

[![Stargazers over time](https://starchart.cc/jenkins-zh/jenkins-cli.svg)](https://starchart.cc/jenkins-zh/jenkins-cli)

[go-report-card-url]: https://goreportcard.com/report/jenkins-zh/jenkins-cli
[go-report-card-badge]: https://goreportcard.com/badge/jenkins-zh/jenkins-cli
[sonar-badge]: https://sonarcloud.io/api/project_badges/measure?project=jenkins-zh_jenkins-cli&metric=alert_status
[sonar-link]: https://sonarcloud.io/dashboard?id=jenkins-zh_jenkins-cli
[godoc-url]: https://godoc.org/github.com/jenkins-zh/jenkins-cli
[godoc-badge]: http://img.shields.io/badge/godoc-reference-5272B4.svg?style=flat-square



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eaf3a6e436295a49e5a6cdb9428798cab70177a46a7da912f16f16f1e9c2002710645516849dee70af23624f0565c1c9d)