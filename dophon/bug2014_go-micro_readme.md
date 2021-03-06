# Go Micro [![License](https://img.shields.io/:license-apache-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![Go.Dev reference](https://img.shields.io/badge/go.dev-reference-007d9c?logo=go&logoColor=white&style=flat-square)](https://pkg.go.dev/github.com/micro/go-micro?tab=doc) [![Travis CI](https://api.travis-ci.org/micro/go-micro.svg?branch=master)](https://travis-ci.org/micro/go-micro) [![Go Report Card](https://goreportcard.com/badge/micro/go-micro)](https://goreportcard.com/report/github.com/micro/go-micro)

Go Micro is a framework for distributed systems development.

## Overview

Go Micro provides the core requirements for distributed systems development including RPC and Event driven communication. 
The **micro** philosophy is sane defaults with a pluggable architecture. We provide defaults to get you started quickly 
but everything can be easily swapped out. 

 

Plugins are available at [github.com/micro/go-plugins](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304655961715f860d02645a4b3c684b863f696ab4c0b8eb4612ca4b070aba2c32ee6).

Follow us on [Twitter](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54feb7dab5c5b9a0385de33f22187ea55e85) or join the [Community](http://u.720life.cn/g/46e9011b46b5531d48181e98373ba9a61007f86905c463915d2cf54035174b94).

## Features

Go Micro abstracts away the details of distributed systems. Here are the main features.

- **Service Discovery** - Automatic service registration and name resolution. Service discovery is at the core of micro service 
development. When service A needs to speak to service B it needs the location of that service. The default discovery mechanism is 
multicast DNS (mdns), a zeroconf system.

- **Load Balancing** - Client side load balancing built on service discovery. Once we have the addresses of any number of instances 
of a service we now need a way to decide which node to route to. We use random hashed load balancing to provide even distribution 
across the services and retry a different node if there's a problem. 

- **Message Encoding** - Dynamic message encoding based on content-type. The client and server will use codecs along with content-type 
to seamlessly encode and decode Go types for you. Any variety of messages could be encoded and sent from different clients. The client 
and server handle this by default. This includes protobuf and json by default.

- **Request/Response** - RPC based request/response with support for bidirectional streaming. We provide an abstraction for synchronous 
communication. A request made to a service will be automatically resolved, load balanced, dialled and streamed. The default 
transport is [gRPC](http://u.720life.cn/g/8c024964a090786d506fe3e8c0519724).

- **Async Messaging** - PubSub is built in as a first class citizen for asynchronous communication and event driven architectures. 
Event notifications are a core pattern in micro service development. The default messaging system is a HTTP event message broker.

- **Pluggable Interfaces** - Go Micro makes use of Go interfaces for each distributed system abstraction. Because of this these interfaces 
are pluggable and allows Go Micro to be runtime agnostic. You can plugin any underlying technology. Find plugins in 
[github.com/micro/go-plugins](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304655961715f860d02645a4b3c684b863f696ab4c0b8eb4612ca4b070aba2c32ee6).

## Getting Started

To make use of Go Micro

```golang
import "github.com/micro/go-micro/v2"
```

See the [docs](http://u.720life.cn/g/46e9011b46b5531d48181e98373ba9a61b52b16e9b07130c5e296595f926ce6ea36161be96218b58174bb684ed76d5d2) for detailed information on the architecture, installation and use of go-micro.

## License

Go Micro is Apache 2.0 licensed.




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7f1bd4923f3d649c29eba0420f299a1337346c1878f01725010b81cf7e6479795c9822870311d660afb93a70ee9948a2)