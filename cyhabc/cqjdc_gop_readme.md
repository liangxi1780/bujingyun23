# GOP

[简体中文](README_ZH.md)

[![CircleCI](https://circleci.com/gh/lunny/gop.svg?style=shield)](https://circleci.com/gh/lunny/gop) [![codecov](https://codecov.io/gh/lunny/gop/branch/master/graph/badge.svg)](https://codecov.io/gh/lunny/gop)
[![](https://goreportcard.com/badge/github.com/lunny/gop)](https://goreportcard.com/report/github.com/lunny/gop) 

GOP is a project manangement tool for building your golang applications out of global GOPATH. In fact gop will keep both global GOPATH and every project GOPATH. But that means your project will  **not** go-getable. Of course, GOP itself is go-getable. GOP copy all denpendencies from global GOPATH to your project's `src/vendor` directory and all application's sources are also in `src` directory.

A normal process using gop is below:

```
git clone xxx@mydata.com:bac/aaa.git
cd aaa
gop ensure -g
gop build
gop test
```

## Features

* GOPATH compitable
* Multiple build targets support
* Put your projects out of global GOPATH

## Installation

Please ensure you have installed the `go` command, GOP will invoke it on building or testing

```
go get github.com/lunny/gop
```

## Directory structure

Every project should have a GOPATH directory structure and put a `gop.yml` int the root directory. This is an example project's directory tree.

```
 
├── gop.yml
├── bin
├── doc
└── src
    ├── main
    │   └── main.go
    ├── models
    │   └── models.go
    ├── routes
    │   └── routes.go
    └── vendor
        └── github.com
            ├── go-xorm
            │   ├── builder
            │   ├── core
            │   └── xorm
            └── lunny
                ├── log
                └── tango
```

## Gop.yml

Gop will recognize a gop project which has `gop.yml`. The file is also a project configuration file. Below is an example. If you didn't define any target, the default target is src/main and the target name is the project name.

```yml
targets:
- name: myproject1
  dir: main
  assets:
  - templates
  - public
  - config.ini
  - key.pem
  - cert.pem
- name: myproject2
  dir: web
  assets:
  - templates
  - public
  - config.ini
  monitors:
  - config.ini
```

## Command

### init

Create the default directory structure tree.

```
gop init
```

### ensure

Automatically copy dependencies from $GOPATH to local project directory. `-g` will let you automatically call `go get  ` when the package is missing on `GOPATH`. `-u` will always `go get  ` on all the dependencies and copy them to `vendor`.

```
gop ensure [-g|-u] [target_name]
```

### status

List all dependencies of this project and show the status.

```
gop status [target_name]
```

### add

Add one or more packages to this project.

```
gop add    
```

### update

Update one or more packages to this project. All missing dependent packages will also be added.
-f will update exists dependent packages.

```
gop update [-f]    
```

### rm

Remove one or more packages from this project.

```
gop rm    
```

### build

Run `go build` on the src directory.

```
gop build [target_name]
```

### run

Run `go run` on the src directory. `-w` will monitor the go source code changes and
automatically build and run again.

```
gop run [-w] [target_name]
```

### test

Run `go test` on the src directory.

```
gop test [target_name]
```

### release

Run `go release` on the src directory.

```
gop release [target_name]
```

## TODO

* [ ] Versions support, specify a dependency package verison
* [ ] Support run `gop` in `GOPATH`


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee52fadc5e8ca5ea87e9b51a2d7f2b2f4752087ef8fc6f4d602eecc4597f86e25088ccf627b98ebe6a600599cb77c581a)