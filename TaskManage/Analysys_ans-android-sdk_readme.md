
## [**易观简介**](https://www.analysys.cn) [![License](https://img.shields.io/github/license/analysys/ans-android-sdk.svg)](https://github.com/analysys/ans-android-sdk/blob/master/LICENSE)  [![GitHub release](https://img.shields.io/github/release/analysys/ans-android-sdk.svg)](https://github.com/analysys/ans-android-sdk/releases)

易观是中国领先的大数据公司，始终追求客户成功的经营宗旨。自成立以来，易观打造了以海量数字用户资产及算法模型为核心的大数据产品、平台及解决方案，可以帮助企业高效管理数字用户资产和对产品进行精细化运营，通过数据驱动营销闭环，从而实现收入增长、成本降低和效率提升，并显著规避经营风险，实现精益成长。易观的数据平台是易观方舟，产品家族包括易观千帆、易观万像以及行业解决方案。


## SDK 简介

ans-android-sdk 是一款商用级别的用户行为采集项目，目前支持代码埋点、可视化全埋点、点击热图等。使用简单，功能模块结构清晰，可按需添加。

## 一分钟上手

1.清单文件配置

``` xml
 
 
 
 
 

 

    ......
     
     
     
     
     
     
     
 
```

2.在**Application**中始化

``` java

// 初始化
AnalysysAgent.init(this, config);
// 热图功能开关
AnalysysAgent.setAutoHeatMap(false);
// 设置数据上传/更新地址
AnalysysAgent.setUploadURL(this, UPLOAD_URL);

// 初始化可视化特色功能（可选）
// 设置长连接Url
AnalysysAgent.setVisitorDebugURL(context, SOCKET_URL);
// 设置配置下发Url
AnalysysAgent.setVisitorConfigURL(context, CONFIG_URL);

```

3.可视化埋点功能

- 在项目根目录文件gradle.properties 设置 Build_Type=visual
- 运行apidemo项目，启动后进入可视化demo入口
- 打开 https://growth.analysys.cn/project-management/visual-choice 左上角选中电商Demo，选Android平台
- 在app打开的情况下摇一摇，设备连接成功后点击设备进入埋点界面
- 点击View添加事件，点击右下方部署下发配置



## [详细文档](http://u.720life.cn/g/4cd1106221deabfb62582c6570d64a543506c3652913d203b7736e21fc64082f9d63f5254f7fe3dc8ccc4823cb7f0aab749b0edbe61f56576282199454acbe46)


## 讨论
* 微信号：nlfxwz
* 钉钉群：30099866
* 邮箱：nielifeng@analysys.com.cn

## License

[gpl-3.0](http://u.720life.cn/g/80aceec34af2d650b057d93ea119d36531755f3be67676222fcefe625c76bbf5335c27ac850839d24225ee0027f9ab3f)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4163d8365d10124c9fe2fd467af08e05fbcdd96caf78fb7c1d638629346f2315b3284f16225d42ef27191f8540f91197)