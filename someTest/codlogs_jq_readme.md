jq
==

jq is a lightweight and flexible command-line JSON processor.

[![Coverage Status](https://coveralls.io/repos/stedolan/jq/badge.svg?branch=master&service=github)](https://coveralls.io/github/stedolan/jq?branch=master),
Unix: [![Build Status](https://travis-ci.org/stedolan/jq.svg?branch=master)](https://travis-ci.org/stedolan/jq),
Windows: [![Windows build status](https://ci.appveyor.com/api/projects/status/mi816811c9e9mx29?svg=true)](https://ci.appveyor.com/project/stedolan/jq)


If you want to learn to use jq, read the documentation at
[https://stedolan.github.io/jq](http://u.720life.cn/g/68eef27d1e5b104f469d5a3038b11be404fbe043e17afd8980ae67b6bcdaff4f).  This
documentation is generated from the docs/ folder of this repository.
You can also try it online at [jqplay.org](http://u.720life.cn/g/ce1cd501108267ca8686fd1a5413d2179f8bd8a6187fe7bcc97b5573f25f7b21).

If you want to hack on jq, feel free, but be warned that its internals
are not well-documented at the moment. Bring a hard hat and a
shovel.  Also, read the wiki: https://github.com/stedolan/jq/wiki, where
you will find cookbooks, discussion of advanced topics, internals,
release engineering, and more.

Source tarball and built executable releases can be found on the
homepage and on the github release page, https://github.com/stedolan/jq/releases

If you're building directly from the latest git, you'll need flex,
bison (3.0 or newer), libtool, make, automake, and autoconf installed.
To get regexp support you'll also need to install Oniguruma or clone it as a
git submodule as per the instructions below.
(note that jq's tests require regexp support to pass).  To build, run:

    git submodule update --init # if building from git to get oniguruma
    autoreconf -fi              # if building from git
    ./configure --with-oniguruma=builtin
    make -j8
    make check

To build without bison or flex, add `--disable-maintainer-mode` to the
./configure invocation:

    ./configure --with-oniguruma=builtin --disable-maintainer-mode

(Developers must not use `--disable-maintainer-mode`, not when making
changes to the jq parser and/or lexer.)

To build a statically linked version of jq, run:

    make LDFLAGS=-all-static

After make finishes, you'll be able to use `./jq`.  You can also
install it using:

    sudo make install

If you're not using the latest git version but instead building a
released tarball (available on the website), then you won't need to
run `autoreconf` (and shouldn't), and you won't need flex or bison.

To cross-compile for OS X and Windows, see docs/Rakefile's build task
and scripts/crosscompile.  You'll need a cross-compilation environment,
such as Mingw for cross-compiling for Windows.

Cross-compilation requires a clean workspace, then:

    # git clean ...
    autoreconf -i
    ./configure
    make distclean
    scripts/crosscompile    

Use the `--host=` and `--target=` ./configure options to select a
cross-compilation environment.  See also 
["Cross compilation"](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046754c6c89cf6c93998bc07ff604d8114fe9195249ee7bc6162b808b542ba1a31ffe289c213a9c6d21d3ecb9460d23807b) on
the wiki.

Send questions to https://stackoverflow.com/questions/tagged/jq or to the #jq channel (http://u.720life.cn/g/940d835d5bcfd1347e04a767d0d36afb0349a9659554014b2019d1e0e8f0e020) on Freenode (http://u.720life.cn/g/1c6ab4bd483726b0ba9428e66ce59265c8070e75b7f8f0cf2152602d95bac5d4).



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e469879d2854214c7cb642ec02c3a57119093ad8c0b1721784b45165ae64b838f99ebed870d6b5c5ee1a74b7687693ab4)