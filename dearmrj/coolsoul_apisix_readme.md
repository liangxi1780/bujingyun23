[中文](README_CN.md)
## APISIX

[![Build Status](https://travis-ci.org/iresty/apisix.svg?branch=master)](https://travis-ci.org/iresty/apisix)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/iresty/apisix/blob/master/LICENSE)
[![Coverage Status](https://coveralls.io/repos/github/iresty/apisix/badge.svg?branch=master)](https://coveralls.io/github/iresty/apisix?branch=master)

- **QQ group**: 552030619
- [![Gitter](https://badges.gitter.im/apisix/community.svg)](https://gitter.im/apisix/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
- [![Twitter](https://img.shields.io/twitter/follow/apisixfast.svg?style=social&label=Follow)](https://twitter.com/intent/follow?screen_name=apisixfast)

## What's APISIX?

APISIX is a cloud-native microservices API gateway, delivering the ultimate performance, security, open source and scalable platform for all your APIs and microservices.

APISIX is based on OpenResty and etcd. Compared with traditional API gateways, APISIX has dynamic routing and plug-in hot loading, which is especially suitable for API management under micro-service system.


## Why APISIX?

If you are building a website, mobile device or IoT (Internet of Things) application, you may need to use an API gateway to handle interface traffic.

APISIX is a cloud-based microservices API gateway that handles traditional north-south traffic and handles east-west traffic between services.

APISIX provides dynamic load balancing, authentication, rate limiting, and other plugins through plugin mechanisms, and supports plugins you develop yourself.

For more detailed information, see the [White Paper](http://u.720life.cn/g/cc087866597a12e9944b1674bf54ccbc29c13717a20bdc8cb8a0d26358e930a6ead8fca41683eb8c4d798813b23436c9b45e906716c89ddb820b01986f4afc289a5a03410266a01e9b53a374794aab54d5ea26ad07de18c91e0143e41fb8b25f28eefefdc6c3ff29dbd8703f04497116ef1034101d43804e537354dea8ea86a8).

![](doc/images/apisix.png)

## Features

- **Cloud-Native**: Platform agnostic, No vendor lock-in, APISIX can run from bare-metal to Kubernetes.
- **hot updates and hot plugins**: Continuously updates its configurations and plugins without restarts!
- **Dynamic Load Balancing**: Round-robin load balancing with weight.
- **Hash-based Load Balancing**: Load balance with consistent hashing sessions.
- **SSL**: Dynamically load an SSL certificate.
- **Forward Proxy**
- **[Health Checks](doc/health-check.md)**：Enable health check on the upstream node, and will automatically filter unhealthy nodes during load balancing to ensure system stability.
- **Circuit-Breaker**: Intelligent tracking of unhealthy upstream services.
- **Authentications**: [key-auth](doc/plugins/key-auth.md), [JWT](doc/plugins/jwt-auth-cn.md)
- **[Limit-req](doc/plugins/limit-req.md)**
- **[Limit-count](doc/plugins/limit-count.md)**
- **[Limit-concurrency](doc/plugins/limit-conn.md)**
- **OpenTracing: [Zipkin](doc/plugins/zipkin.md)**
- **Monitoring and Metrics**: [Prometheus](doc/plugins/prometheus.md)
- **[gRPC transcoding](doc/plugins/grpc-transcoding.md)**：Supports protocol transcoding so that clients can access your gRPC API by using HTTP/JSON.
- **Custom plugins**: Allows hooking of common phases, such as `rewrite`, `access`, `header filer`, `body filter` and `log`, also allows to hook the `balancer` stage.
- **Dashboard**: Built-in dashboard to control APISIX.
- **Version Control**: Supports rollbacks of operations.
- **CLI**: start\stop\reload APISIX through the command line.
- **REST API**
- **Clustering**
- **Scalability**
- **High performance**: The single-core QPS reaches 24k with an average delay of less than 0.6 milliseconds.
- **Anti-ReDoS(Regular expression Denial of Service)**
- **IP whitelist/blacklist**
- **OAuth2.0**: TODO.
- **ACL**: TODO.
- **Bot detection**: TODO.

## Online Demo Dashboard
We provide an online dashboard [demo version](http://u.720life.cn/g/cd70b34d4532e802629c5c0fab6bc0350f68e62f7d2285c41dd602e312514e70)， make it easier for you to understand APISIX.

## Install

APISIX Installed and tested in the following systems:

| OS           | OpenResty | Status |
| ------------ | --------- | ------ |
| CentOS 7     | 1.15.8.1  | √      |
| Ubuntu 16.04 | 1.15.8.1  | √      |
| Ubuntu 18.04 | 1.15.8.1  | √      |
| Debian 9     | 1.15.8.1  | √      |
| Mac OSX      | 1.15.8.1  | √      |

You now have two ways to install APISIX: if you are using CentOS 7, it is recommended to use RPM, other systems please use Luarocks.

We will add support for Docker and more OS shortly.

### Install from RPM for CentOS 7

```shell
sudo yum install yum-utils
sudo yum-config-manager --add-repo https://openresty.org/package/centos/openresty.repo
sudo yum install -y openresty etcd
sudo service etcd start

sudo yum install -y https://github.com/iresty/apisix/releases/download/v0.6/apisix-0.6-0.el7.noarch.rpm
```

You can try APISIX with the [**Quickstart**](#quickstart) now.

### Install from Luarocks

#### Dependencies

APISIX is based on [OpenResty](http://u.720life.cn/g/f6d0e5926518fdbf1653159b0aca06bd140be70b9860f4f8e64d69be1df24dcb), the configures data storage and distribution via [etcd](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304667c320c71c3aa7c94c777b43dadee896).

We recommend that you use [luarocks](http://u.720life.cn/g/6463c06a2aca762d5a264c16a759c6825573fbc21417d70d29a225f447f0db36) to install APISIX, and for different operating systems have different dependencies, see more: [Install Dependencies](doc/install-dependencies.md)

#### Install APISIX

```shell
sudo luarocks install --lua-dir=/usr/local/openresty/luajit apisix
```

If all goes well, you will see the message like this:

> apisix is now built and installed in /usr (license: Apache License 2.0)

Congratulations, you have already installed APISIX successfully.

## Development Manual of APISIX

If you are a developer, you can view the [dev manual](doc/dev-manual.md) for more detailed information.

## Quickstart

1. start server:

```shell
sudo apisix start
```

2. try limit count plugin

Limit count plugin is a good start to try APISIX,
you can follow the [documentation of limit count](doc/plugins/limit-count.md).

Then you can try more [plugins](doc/plugins.md).

## Dashboard
APISIX has the built-in dashboard，open `http://127.0.0.1:9080/apisix/dashboard` with a browser and try it.

Do not need to fill the user name and password, log in directly.

dashboard only allow `127.0.0.0/24` by default, and you can modify `allow_admin` in `conf/config.yaml` by yourself, to add more IPs.

## Benchmark

Using Google Cloud's 4 core server, APISIX's QPS reach to 60,000 with a latency of only 500 microseconds.

You can view the [benchmark documentation](doc/benchmark.md) for more detailed information.

## Architecture Design

English Development Documentation: TODO

[中文开发文档](doc/architecture-design-cn.md)

## Videos and slides

- [APISIX technology selection, testing and continuous integration(Chinese)](http://u.720life.cn/g/c74293c7c96be0b7a6c5633d4bc29940a232f6e6409666abe42aad8e2feb84025703aed65d1c47c2cf8811059d61571c)

- [APISIX high performance practice(Chinese)](http://u.720life.cn/g/c74293c7c96be0b7a6c5633d4bc29940a232f6e6409666abe42aad8e2feb84026d96345d030ed54e61ce0be1b1784b62)

## Landscape

APISIX enriches the [CNCF API Gateway Landscape](http://u.720life.cn/g/b0dc3561dc670ead550bee6b8462454ddb2364950f7a4565f42ae31b60733f872d43b4b8152fd3308f1623af59dd343cd98a81c8a6701b85e78e49544447c2fb44197fc3465b8079523bff1d384fc7cfc77372e8822c7c86ac7729bd624dd14d):

![](doc/images/cncf-landscope.jpg)

## FAQ
There are often some questions asked by developers in the community. We have arranged them in the [FAQ](FAQ.md).

If your concerns are not among them, please submit issue to communicate with us.

## Contributing

Contributions are welcomed and greatly appreciated.

## Acknowledgments

inspired by Kong and Orange.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e60c4e316e2d32e2a3d737881a2fe13b87f84f45d94d814b12f821b1b025429131b13b1ffca829c4159defd24760b80eb)