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
* Configuration as Code support
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

You can find the latest version [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462e481b4b06e8e794e91fc258aaf1462b3b239df3350a39c4ceca7b89f99966acf998214c147ba39f0fb5c5462811ced93765e69cbe0de4e14d2d3778ea038cbc5557af90cf12d74121102027634ad049  
Download the tar file and copy the uncompressed `jcli` directory into your system path.

## Other package managers

Here are other package managers:

* [GoFish](http://u.720life.cn/g/dbb76656c1a2b908d7f15f704703cdac)  users can use `gofish install jcli`
* [Scoop](http://u.720life.cn/g/07086b44341f50347c09864bb5b86824c148beb2e23bbf8280773976d0a961fb)  users can use `scoop install jcli`
* [Chocolatey](http://u.720life.cn/g/9bc921a271360009e6bb627886d4751c85613deafd0f7d9a708fc49ea906fe8e50f497c3898442b5fa2fe290fe2bc563)  users can use `choco install jcli`
* [Snapcraft](http://u.720life.cn/g/cb8c0f263f2db7ede4fdced37178390a2989243f28a858d5cb0f93b143a3e14e)  users can use `sudo snap install jcli`

See more about [how to download jcli](doc/download.md).
You can find the download details [from here](http://u.720life.cn/g/6b383302d1d1276f49c2f01f71fa99ea81ba8ea3021fab3fcbca0e711e9311d77e56cd36342c2f5913d97ab4589c33a3d031afd1f12cfb42cfdd0647ecf3bb909d67b5b9f7b6d8ec518856a4814e7d207db3dd83ca1cb1884f37c9c75457c3d9 

# Get started

Read the [official document](http://u.720life.cn/g/2ae88258c1ab8fe2dab19785b2a9f3a46967768796271784272871b0f0870886)  for more details on how to use `jcli`.

Or, you can take [a live interactive course](http://u.720life.cn/g/010da99562b7f242ed9a52aa02382a2b05f408569c9230ff80fef9168a1c86e5e64e1c6264b79fc5f05783cfd83cec5d8a14d61a9131c2a2200a28057febb35e)  of Jenkins CLI.

# Plugins

Jenkins CLI could have more features by installing a plugin for it. You can install a plugin by the following command:

```
jcli config plugin fetch
jcli config plugin install account
```

All official plugins could be found at [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b50f05bab6b7daf2141da8dd5a6d9d29fdf85e5ecfb4b77977e1640752def493 

# Contribution

If you're interested in this project. Please go through the
[contribution guide](CONTRIBUTING.md). Any contributions are welcome.

Thanks to JetBrains for giving us the open source licence.  
[![goland.svg](./goland.svg)](https://www.jetbrains.com/?from=jenkins-cli)

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