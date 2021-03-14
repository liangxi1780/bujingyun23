# Docker Exec Image: PHP

A Dockerfile describing an container capable of executing PHP source files.

# Build

```sh
git clone https://github.com/docker-exec/php.git
docker build -t dexec/php .
```

# Usage

In a directory containing a script e.g. foo.php, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.php:/tmp/dexec/build/foo.php \
    dexec/php foo.php
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.php:/tmp/dexec/build/foo.php \
    dexec/php foo.php \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eee80af59830cf95f49bc97959c07548df6d8c5f49e22236284ce4fe298f090896a5c2e8d970bef1f2e29f1945cc905d4661131b4eaa74ab9a9d4c85887bd5b74)