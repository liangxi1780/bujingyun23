![](https://www.google-analytics.com/__utm.gif?utmwv=4&utmac=UA-92164710-1&utmipc=homekit-server)

# homekit-server
Apple Homekit server for Raspberry PI.

## Usage
```
    cd homekit-server
    npm install
    babel-node index.js
```

## Roles in This Prototype
### Homekit

Apple HomeKit is a framework for communicating with and controlling connected accessories in a user's home. 

### Accessories

Represents a HomeKit device that can be published on your local network.
In this prototype project, both Lamp and Thermometer are accessories.


### Bridge

A kind of Accessory that can host other Accessories "behind" it while only publishing a single device.

The whole project is a Node.js powered Bridge server.

### Lamp

Represents a NodeMCU connected, HSB(hue, saturation and brightness) customizable lamp. See the source code in the examples folder.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e88a26a3da7febc2c42562374d288d4cc068c6c8e881924c38bc2459cae2406b90bbffde53ff1984ebc690a60d4abb579)