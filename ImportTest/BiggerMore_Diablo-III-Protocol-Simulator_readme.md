SUMMARY
=======

a diablo III network protocol simulator / replayer

version
-------

2.02 18.09.2011

author
------

sku/thesku

description
-----------

parses diablo3 tcp streams and maps the packets to their respective  
protobuf messages, simulates client and server behaviour and keeps track  
of bound services / responses etc.

credits
-------

shadow^dancer, TOM_RUS, d3.dev, diablo3dev.com, raistlinthewiz

legal
-----

code posted to public domain by sku, no copyright  
use at your own risk

DATA FILE FORMAT
================

1) open wireshark  
2) filter for tcp.srcport==1119||tcp.dstport==1119  
3) rightclick any packet -> Follow TCP stream  
4) save all bytes to all.dat  
5) save client->server bytes to c2s.dat  
6) save server->client bytes to s2c.dat  
7) place these 3 files in the ./data folder  

CHANGELOG
=========

2.01.18.09.2011 - added HeroDigest dumps (not in html format yet)  
2.02.18.09.2011 - log complete message type + scope to html, not just name  
                  started work on sandbox

OMG
===

yes, this is a poc, it's ugly and has a lot of repetitive code  
get over it


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef0ca9ab7b43815a3152d2d653499d57bcb0731fce5e9e4f7b549589c7f200ad80ecee1434c37bca442a4203ce33670c78a4a358d4fe0ea96d1750235943f2eb2)