plotGrav
=========
Matlab GUI tool for processing & visualization of various time series.  
The toolbox was developed for processing of gravimeter time series but can be used for arbitrary input.  

### Features
* load 4 different data files at once in diverse formats such as [TSoft](http://u.720life.cn/g/5b6237a02cceec628dd91e2925b181fd072d24102cf5a01183d7c75635241b3f8680a91f54451fc932940f8f7c560d62), Campbell Logger, or [Dygraphs](http://u.720life.cn/g/32f56708fd6a2ab52bc7632fe8ce6bae45469dd7ad038dbfc44461435a711cbe03382dc05afbb585058f56af77f6f4f6) csv
* export & print time series
* use scripts (instead of GUI)
* compute statistics such as correlation
* apply ML methods such as regression or principle component analysis
* apply corrections (e.g., steps, gaps)
* filter time series
* compute spectral analysis
* do some algebra on all input series (e.g., add, subtract, divide time series)
* download & process [Atmacs](http://u.720life.cn/g/2c4f829a1e6ec8fae41e48a2cfba410b517359ca2e423ef502093d0ee5840a15) atmospheric model data
* compute polar motion and length of day gravity effect
* introduce time shifts and re-sample the data (new temporal resolution)
* automatically fill missing data (interpolate or set to constant)
* estimate gravimeter calibration parameters
* superimpose plots with latest Earthquake records
* stack multiple files into one (for gravimeter records)

### Usage
* Run `plotGrav.m` or see `plotGrav_TestScript.plg` for scripting

### Dependency
* Tested and developed under Matlab R2015b
  * Some functions use statistics, curve fitting, and signal processing toolboxes
* The GUI appearance depends on Matlab version and screen resolution (optimized for 1920x1080)

### GUI
![](aux_files/gui.png)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9bb6eab638428deaf4b7e47f86a5d91f8931c88b6946f447d7d52e24197f1d0d62cf972c0ff46f48d9f8b638dcfcca09)