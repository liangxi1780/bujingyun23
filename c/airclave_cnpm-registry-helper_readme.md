# NPM 源切换脚本

这是一批用于帮助中国大陆程序猿切换 npm/yarn 镜像的脚本，且支持 Electron 框架的换源。

**注意**

> 1. 如果您要准备发布 npm 包，请记得将源还原回官方源，淘宝镜像无法处理库的上传。
>
> 2. 如果您尚未安装 Yarn，请忽略警告信息。

**推广项目**

[NRM](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461b383a85ff9be7376da21bb9462dfbcc)  是一款以 Node 编写的 NPM 换源工具。说实话，它已经能满足大部分需求了，但它并没有提供完善的 Electron 框架的换源。该项目提供的脚本可视为其临时补充。

## 切换方法

(Windows NT)

```sh
git clone https://github.com/langyo/cnpm-registry-helper
to_taobao.bat
```

(*nix / Mac)

```sh
git clone https://github.com/langyo/cnpm-registry-helper
sh ./to_taobao.sh
```

## 还原方法

(Windows NT)

```sh
git clone https://github.com/langyo/cnpm-registry-helper
to_global.bat
```

(*nix / Mac)

```sh
git clone https://github.com/langyo/cnpm-registry-helper
sh ./to_global.sh
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)