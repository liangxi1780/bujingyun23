# BootstrapAdmin

 English  |  中文 

---

##### Version & Coverage
[![Release](https://img.shields.io/endpoint.svg?logo=Groupon&logoColor=red&color=green&label=release&url=https%3A%2F%2Fargo.zylweb.cn%2FBA%2Fapi%2FGitee%2FReleases)](http://argo.zylweb.cn/BA/Tools/Index?ReturnUrl=https%3A%2F%2Fgitee.com%2FLongbowEnterprise%2FBootstrapAdmin%2Freleases)
[![Coveralls](https://img.shields.io/coveralls/github/ArgoZhang/BootstrapAdmin/master.svg?logo=ReverbNation&logoColor=green)](https://coveralls.io/github/ArgoZhang/BootstrapAdmin)
[![Codecov](https://img.shields.io/codecov/c/gh/argozhang/bootstrapadmin/master.svg?logo=codecov)](https://codecov.io/gh/argozhang/bootstrapadmin/branch/master)

##### Gitee
[![Appveyor build](https://img.shields.io/endpoint.svg?logo=appveyor&label=build&color=blueviolet&url=https%3A%2F%2Fargo.zylweb.cn%2FBA%2Fapi%2FGitee%2FBuilds?projName=bootstrapadmin-9m1jm)](https://ci.appveyor.com/project/ArgoZhang/bootstrapadmin-9m1jm)
[![Build Status](https://img.shields.io/appveyor/ci/ArgoZhang/bootstrapadmin-9m1jm/master.svg?logo=appveyor&label=maser)](https://ci.appveyor.com/project/ArgoZhang/bootstrapadmin-9m1jm)
[![Test](https://img.shields.io/appveyor/tests/ArgoZhang/bootstrapadmin-9m1jm/master.svg?logo=appveyor&)](https://ci.appveyor.com/project/ArgoZhang/bootstrapadmin-9m1jm/build/tests)
[![Issue Status](https://img.shields.io/endpoint.svg?logo=Groupon&logoColor=critical&label=issues&url=https%3A%2F%2Fargo.zylweb.cn%2FBA%2Fapi%2FGitee%2FIssues)](https://gitee.com/LongbowEnterprise/BootstrapAdmin/issues)
[![Pull Status](https://img.shields.io/endpoint.svg?logo=Groupon&logoColor=green&color=success&label=pulls&url=https%3A%2F%2Fargo.zylweb.cn%2FBA%2Fapi%2FGitee%2FPulls)](https://gitee.com/LongbowEnterprise/BootstrapAdmin/pulls)

##### GitHub
[![Appveyor build](https://img.shields.io/endpoint.svg?logo=appveyor&label=build&color=blueviolet&url=https%3A%2F%2Fargo.zylweb.cn%2FBA%2Fapi%2FGitee%2FBuilds?projName=bootstrapadmin)](https://ci.appveyor.com/project/ArgoZhang/bootstrapadmin)
[![dev status](https://img.shields.io/appveyor/ci/ArgoZhang/bootstrapadmin/dev.svg?logo=appveyor&label=dev)](https://ci.appveyor.com/project/ArgoZhang/bootstrapadmin/branch/dev)
[![master status](https://img.shields.io/appveyor/ci/ArgoZhang/bootstrapadmin/master.svg?logo=appveyor&label=master)](https://ci.appveyor.com/project/ArgoZhang/bootstrapadmin/branch/master)
[![Test](https://img.shields.io/appveyor/tests/argozhang/bootstrapadmin/master.svg?logo=appveyor&)](https://ci.appveyor.com/project/ArgoZhang/bootstrapadmin/branch/master/tests)
[![Repo Size](https://img.shields.io/github/repo-size/ArgoZhang/BootstrapAdmin.svg?logo=github&logoColor=green&label=repo)](https://github.com/ArgoZhang/BootstrapAdmin)
[![Commit Date](https://img.shields.io/github/last-commit/ArgoZhang/BootstrapAdmin/master.svg?logo=github&logoColor=green&label=commit)](https://github.com/ArgoZhang/BootstrapAdmin)

## Introduce
Because the dependent on Bootstrap v4, so it is called **Bootstrap Admin**. This system can be integrated with asp.net and asp.net core applications. The database supports multiple databases at the same time. The detailed list is shown in the following **database** detailed list. Switching the data source only needs to change the configuration file without restarting the application. The configuration is simple and flexible. The UI front-end uses the popular Bootstrap framework layout, which is very compatible with mobile devices and adapts to almost all terminal devices in the current market. The system also has the feature of single background supporting multi-front desk, and provides the ability of **single sign-on (SSO)**.  

### Features  
1. Integration with Front-end Website through Configuration
2. Constructing Hierarchical Menu of Front-end System
3. Provide a single background to support multiple front-end application configurations
4. Provide single sign-on(SSO)
5. Integrated System Authentication and Authorization Module
6. Provide role, department, user, menu, foreground application authorization
Role Authorization to Users  
Role-to-Menu Authorization  
Role Authorization to Departments  
Role-to-application authorization (multiple front-end applications share a back-end privilege management system)  
Departments Authorize Users
7. Provide dictionary tables for personalized configuration of front-end websites
8. Fully responsive layout (supporting all mainstream devices such as computers, tablets, mobile phones, etc.)
9. Built-in multi-data source support, simple configuration and immediate effect without restart
10. Built-in data memory caching mechanism, page fast response
11. Built-in Data **Operation Log** and User **Log on**  

#### Advantage
1. The front-end system does not need to write login, authorization and authentication modules; it is only responsible for writing business modules.
2. Background system can be used directly without any secondary development.
3. The foreground and background systems are separated without any dependence.

For more information, please click [wiki](https://gitee.com/LongbowEnterprise/BootstrapAdmin/wikis/项目介绍)  

### Database 
**MSSQL/Oracle/SQLite/MySql/MariaDB/Postgresql/Firebird/MsAccess/MongoDB**  

### Browser
![chrome](https://img.shields.io/badge/chrome->%3D4.5-success.svg?logo=google%20chrome&logoColor=red)
![firefox](https://img.shields.io/badge/firefox->38-success.svg?logo=mozilla%20firefox&logoColor=red)
![edge](https://img.shields.io/badge/edge->%3D12-success.svg?logo=microsoft%20edge&logoColor=blue)
![ie](https://img.shields.io/badge/ie->%3D11-success.svg?logo=internet%20explorer&logoColor=blue)
![Safari](https://img.shields.io/badge/safari->%3D9-success.svg?logo=safari&logoColor=blue)
![Andriod](https://img.shields.io/badge/andriod->%3D4.4-success.svg?logo=android)
![oper](https://img.shields.io/badge/opera->%3D3.0-success.svg?logo=opera&logoColor=red)

```json
"browserslist": [
  "Chrome >= 45",
  "Firefox >= 38",
  "Edge >= 12",
  "Explorer >= 11",
  "iOS >= 9",
  "Safari >= 9",
  "Android >= 4.4",
  "Opera >= 30"
]
```  

### Mobile 
![ios](https://img.shields.io/badge/ios-supported-success.svg?logo=apple&logoColor=white)
![Andriod](https://img.shields.io/badge/andriod-suported-success.svg?logo=android)
![windows](https://img.shields.io/badge/windows-suported-success.svg?logo=windows&logoColor=blue)

|                        |  **Chrome**  |  **Firefox**  |  **Safari**  |  **Android Browser & WebView**  |  **Microsoft Edge**  |
| -------                | ---------    | ---------     | ------       | -------------------------       | --------------       |
|  **iOS**               | Supported    | Supported     | Supported    | N/A                             | Supported            |
|  **Android**           | Supported    | Supported     | N/A          | Android v5.0+ supported         | Supported            |
|  **Windows 10 Mobile** | N/A          | N/A           | N/A          | N/A                             | Supported            |

### Desktop
![macOS](https://img.shields.io/badge/macOS-supported-success.svg?logo=apple&logoColor=white)
![linux](https://img.shields.io/badge/linux-suported-success.svg?logo=linux&logoColor=white)
![windows](https://img.shields.io/badge/windows-suported-success.svg?logo=windows)

|         | Chrome    | Firefox   | Internet Explorer | Microsoft Edge | Opera     | Safari        |
| ------- | --------- | --------- | ----------------- | -------------- | --------- | ------------- |
| Mac     | Supported | Supported | N/A               | N/A            | Supported | Supported     |
| Linux   | Supported | Supported | N/A               | N/A            | N/A       | N/A           |
| Windows | Supported | Supported | Supported, IE10+  | Supported      | Supported | Not supported |

## QQ Group
[![QQ](https://img.shields.io/badge/QQ-795206915-green.svg?logo=tencent%20qq&logoColor=red)](https://shang.qq.com/wpa/qunwpa?idkey=d381355e50ff91db410c3da3eadb081ba859f64c2877e86343f4709b171f28b8)

## Installation
1. Install .net core sdk [Offical website](http://u.720life.cn/g/43d8d3d99c8fd8af6c240816f866ce0c8b13eb7d4d18ef7e176fe2d01e91feca623f97614f43c51b207b842a033b3b54)
2. Install Visual Studio IDE 2017 lastest [Offical website](http://u.720life.cn/g/820904a611da240c9864c98b312d88b8c07726139b7dc45e0ef6d2903f520b6f50e1dffe58ee320520982acba69e56be25357d31c73393d8bcc9176de3a03310)
3. Git clone `git clone https://github.com/ArgoZhang/BootstrapAdmin.git`
4. Copy file `copy ./Scripts/Longbow.lic ./Bootstrap.Admin/bin/debug/netcoreap2.2/longbow.lic`
5. Login as Admin/123789  

## Branchs  
 **dev** env: windows + SQLite  
 **master** Synchronized with Online Demo

## Online Demonstration   
[![website1](https://img.shields.io/badge/website-https://argo.zylweb.cn-success.svg?logo=buzzfeed&logoColor=green)](https://argo.zylweb.cn)
[![website2](https://img.shields.io/badge/website-http://ba.sdgxgz.com-success.svg?logo=buzzfeed&logoColor=green)](http://ba.sdgxgz.com)  

### Login  
Administrator: Admin/123789  
User: User/123789

## Docker Images
[![Docker](https://img.shields.io/docker/cloud/automated/argozhang/ba.svg?logo=docker&logoColor=success)](https://hub.docker.com/r/argozhang/ba)
[![Docker](https://img.shields.io/docker/cloud/build/argozhang/ba.svg?logo=docker&logoColor=success)](https://hub.docker.com/r/argozhang/ba/builds)

### Docker Hub 
Mirror [Portal](http://u.720life.cn/g/ce46a7789a867c84732a8edd85365bef7a57e0b90c60cec536e12a347151755d97ea5b13cae70172eb4c85ef96e01d05)
```bash
docker pull argozhang/ba
```
### Qiniu Cloud:  
Mirror [Portal](http://u.720life.cn/g/fe516d6c0da7b74c799fb3061bc1a5057f214ddbd115e29c53739c23171aec92cbe9e019fd206d7a096a84c7de68adac)
```bash
docker pull reg.qiniu.com/argozhang/ba
```

## Configurations
Detailed configuration instructions please click [wikis](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e57ea0884cbb37ee2cbb0c5aa7c340d74e053c450f6dfab45eaccf03604238a363b83b60ed1d6555c9594670f930e9478)

## Q&A
Please click [wikis](https://gitee.com/LongbowEnterprise/BootstrapAdmin/wikis/常见问题Q&A)  

## License
[![Gitee license](https://img.shields.io/github/license/argozhang/bootstrapadmin.svg?logo=git&logoColor=red)](https://gitee.com/LongbowEnterprise/BootstrapAdmin/blob/master/LICENSE)

## GVP award
[View](http://u.720life.cn/g/419fcd939867f011a773f7d4a924add9a2699c306a78c06cc02641dde4b0c2e0f846131cf64452ad963c49f60e098a95c9bf542db04acdd4d579bfc7be40c7a7091e43ab1773d6268606880e83241a04 "GiteeGVP.png")

## Screenshots

Home

![Home](https://gitee.com/LongbowEnterprise/Pictures/raw/master/BootstrapAdmin/BA02-01.png "BAHome-01.png")

For more screenshots, Click [wiki](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e57ea0884cbb37ee2cbb0c5aa7c340d74e053c450f6dfab45eaccf03604238a363b83b60ed1d6555c9594670f930e9478)

## Contribution

1. Fork
2. Create Feat_xxx branch
3. Commit
4. Create Pull Request



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee5a78262f75e8184a24fc04acc7818ad166f5e01f639981b5a7a09d64b6069e5b048f3f3f487c8a3065a9e9c4f7ca0f470d99105a83ae211a9ce18a603c9abcf)