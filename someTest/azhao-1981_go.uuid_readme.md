# UUID package for Go language

[![Build Status](https://travis-ci.org/satori/go.uuid.png?branch=master)](https://travis-ci.org/satori/go.uuid)
[![Coverage Status](https://coveralls.io/repos/github/satori/go.uuid/badge.svg?branch=master)](https://coveralls.io/github/satori/go.uuid)
[![GoDoc](http://godoc.org/github.com/satori/go.uuid?status.png)](http://godoc.org/github.com/satori/go.uuid)

This package provides pure Go implementation of Universally Unique Identifier (UUID). Supported both creation and parsing of UUIDs.

With 100% test coverage and benchmarks out of box.

Supported versions:
* Version 1, based on timestamp and MAC address (RFC 4122)
* Version 2, based on timestamp, MAC address and POSIX UID/GID (DCE 1.1)
* Version 3, based on MD5 hashing (RFC 4122)
* Version 4, based on random numbers (RFC 4122)
* Version 5, based on SHA-1 hashing (RFC 4122)

## Installation

Use the `go` command:

	$ go get github.com/satori/go.uuid

## Requirements

UUID package requires Go >= 1.2.

## Example

```go
package main

import (
	"fmt"
	"github.com/satori/go.uuid"
)

func main() {
	// Creating UUID Version 4
	u1 := uuid.NewV4()
	fmt.Printf("UUIDv4: %s\n", u1)

	// Parsing UUID from string input
	u2, err := uuid.FromString("6ba7b810-9dad-11d1-80b4-00c04fd430c8")
	if err != nil {
		fmt.Printf("Something gone wrong: %s", err)
	}
	fmt.Printf("Successfully parsed: %s", u2)
}
```

## Documentation

[Documentation](http://u.720life.cn/g/5f846f4bbbea46aa04e8bf5989edd9eac67f11a10b21c647ec2d578f6f2f14cdf43c3cf018b0407ce8b0063b511422b9) is hosted at GoDoc project.

## Links
* [RFC 4122](http://u.720life.cn/g/3e0d9166348e22f7e642add25dc4874d9db276f2f6326c9cd858e8e53e6bc9942d041a3353fb15a804e509f6ea708a1f)
* [DCE 1.1: Authentication and Security Services](http://u.720life.cn/g/86a75ed82adfc8670b1dfb9ae38e79f21d6d67e4ee7422ae739c19521f9911a3dec194e9f1e03c7d628e19d2e450bb9ca42d12c65bf0539c1ed4f542e9b39f3ce1762e2ec6d91d193b0a0934f9e22d3d)

## Copyright

Copyright (C) 2013-2016 by Maxim Bublis  .

UUID package released under MIT License.
See [LICENSE](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304676c2d910f15af5556135c7a6bf8b2c7f7178b3fa119e92aee4dc1bcf04ca369e58b93e57b0ea0ba91af5d7fb06075cc0) for details.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ece36c01b3df149e27063f27e02fc563b597d06964f9f50de355a5f2a6578a9adabcab2bd3f7f9ab300acb360b92b549b)