# Eclipse TypeScript Plug-in

An Eclipse plug-in for developing in the TypeScript language.

## Installation
1. Install [Node.js](http://u.720life.cn/g/c47729c1c499a00d6e30af9fa18eaddd7b41ca24e187ea438549a271175cdbab)
1. Open Eclipse and go to Help->Install New Software
1. Add the update site: http://eclipse-update.palantir.com/eclipse-typescript/
1. Reboot Eclipse
1. (optional) Right-click on a project and select Configure->Enable TypeScript Builder

## Features
* code completion
* compile-on-save
* cross-project compilation
* error annotations/markers
* find references
* format code
* highlight matching brace
* hover for JSDoc
* mark occurrences
* open definition
* outline view
* quick outline
* rename refactor
* syntax highlighting
* task tags
* toggle comments

## Additional Information
* Eclipse Kepler (4.3) and Luna (4.4) are supported
* Eclipse must be running via Java 6+
* [Wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046920b897f6b9faf68e083a6c83bfce690c3d51ce2c0a910f60ad96f2e68efec50238f1bc9fb0b006480f5d4d66d080fcb) (contains information about developing the plug-in)

## Development
### Update Typescript
* Clone Typescript into a sibling folder
* Run `npm install` in the Typescript project
* Run `npm install -g dos2unix jake`
* Update Typescript branch in `./scripts/updateTypeScript.sh`
* Run `./scripts/updateTypeScript.sh`

### Build and Test
* Run `maven package`
* Install zip in Eclipse following `Install New Software...` -> `Add...` -> `Archive...`



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e84f43ad1083eb91869c63fd847426d3660c549c113f7ffff19e807732e4de03dbc171e952d5f33786bc3a2d69178ef33)