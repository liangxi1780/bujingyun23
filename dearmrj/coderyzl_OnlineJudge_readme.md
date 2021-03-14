# OnlineJudge 2.0

[![Python](https://img.shields.io/badge/python-3.6.2-blue.svg?style=flat-square)](https://www.python.org/downloads/release/python-362/)
[![Django](https://img.shields.io/badge/django-1.11.4-blue.svg?style=flat-square)](https://www.djangoproject.com/)
[![Django Rest Framework](https://img.shields.io/badge/django_rest_framework-3.4.0-blue.svg?style=flat-square)](http://www.django-rest-framework.org/)
[![Build Status](https://travis-ci.org/QingdaoU/OnlineJudge.svg?branch=master)](https://travis-ci.org/QingdaoU/OnlineJudge)

> #### An onlinejudge system based on Python and Vue. [Demo](http://u.720life.cn/g/c748889508b046f322691f0654b69f5e956f4d48bfe0c8339c0b0748aaf84124)

[中文文档](README-CN.md)

## Overview

+ Based on Docker; One-click deployment
+ Separated backend and frontend; Modular programming; Micro service
+ ACM/OI rule support; realtime/non-realtime rank support
+ Amazing charting and visualization
+ Template-problem support
+ More reasonable permission control
+ Multi-language support: `C`, `C++`, `Java`, `Python2`, `Python3`
+ Markdown & MathJax support
+ Contest participants IP limit(CIDR)

Main modules are available below:

+ Backend(Django): [https://github.com/QingdaoU/OnlineJudge](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466ee5f7c05ab9d67761b951920ae84b9f5577ba7a5ef9cd868fbaf2b1574e3b1c)
+ Frontend(Vue): [https://github.com/QingdaoU/OnlineJudgeFE](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466ee5f7c05ab9d67761b951920ae84b9f1ba61c451d9eec707f96fe5171b2fde3)
+ Judger Sandbox(Seccomp): [https://github.com/QingdaoU/Judger](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e83e921d1031b569fc9315d39ec7102b95541ac84ae4b45a9b05e198cb877f82)
+ JudgeServer(A wrapper for Judger): [https://github.com/QingdaoU/JudgeServer](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e83e921d1031b569fc9315d39ec7102b477ad0430bad858bb3c033ce15a399ca)

## Installation

Follow me:  [https://github.com/QingdaoU/OnlineJudgeDeploy/tree/2.0](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466ee5f7c05ab9d67761b951920ae84b9f98dfa35ce541879a9b7a3f41612c1c21e7b6c8639af173befebc4d67213ccc2b)

## Documents

[https://docs.onlinejudge.me/](http://u.720life.cn/g/82f63e7bafb32f6f85d2b993c471f6b0b87d3a0efe87a6662349c7a69838acca)

## Screenshots

### Frontend:

![problem-list](https://user-images.githubusercontent.com/20637881/33372506-402022e4-d539-11e7-8e64-6656f8ceb75a.png)

![problem-details](https://user-images.githubusercontent.com/20637881/33372507-4061a782-d539-11e7-8835-076ddae6b529.png)

![statistic-info](https://user-images.githubusercontent.com/20637881/33372508-40a0c6ce-d539-11e7-8d5e-024541b76750.png)

![contest-list](https://user-images.githubusercontent.com/20637881/33372509-40d880dc-d539-11e7-9eba-1f08dcb6b9a0.png)

You can control the menu and chart status in rankings.

![acm-rankings](https://user-images.githubusercontent.com/20637881/33372510-41117f68-d539-11e7-9947-70e60bad3cf2.png)

![oi-rankings](https://user-images.githubusercontent.com/20637881/33372511-41d406fa-d539-11e7-9947-7a2a088785b0.png)

![status](https://user-images.githubusercontent.com/20637881/33372512-420ba240-d539-11e7-8645-594cac4a0b78.png)

![status-details](https://user-images.githubusercontent.com/20637881/33365523-787bd0ea-d523-11e7-953f-dacbf7a506df.png)

![user-home](https://user-images.githubusercontent.com/20637881/33365521-7842d808-d523-11e7-84c1-2e2aa0079f32.png)

### Admin: 

![admin-users](https://user-images.githubusercontent.com/20637881/33372516-42c34fda-d539-11e7-9f4e-5109477f83be.png)

![judge-server](https://user-images.githubusercontent.com/20637881/33372517-42faef9e-d539-11e7-9f17-df9be3583900.png)

![create-problem](https://user-images.githubusercontent.com/20637881/33372513-42472162-d539-11e7-8659-5497bf52dbea.png)

![create-contest](https://user-images.githubusercontent.com/20637881/33372514-428ab922-d539-11e7-8f68-da55dedf3ad3.png)

## Browser Support

Modern browsers(chrome, firefox) and Internet Explorer 10+.

## Thanks

+ I'd appreciate a star if you find this helpful.
+ Thanks to everyone that contributes to this project.
+ Special thanks to [heb1c](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462aa4655ec11fc2d16c24a9b675f5037b), who has given us a lot of suggestions.

## License

[MIT](http://u.720life.cn/g/ba059582536a397f7c573b87c8bea647045b0ef049248233b6f76e909e70200fe7048b25e29c8bab79aeff32ea74556a)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e70943c3bff5bcecce415b4c339b99ab295a9e83c3986a189d404430490c2fc446f02d350b676c69016fc735672ce0499)