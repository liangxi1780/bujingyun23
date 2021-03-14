# poi-el
excel导出与导入神器，poi-el。  
* poi-el支持强大的excel模板导出功能  
* poi-el支持方便的excel导入API

## excel模板导出
使用poi + spEl，支持各种普通模板和复杂模板的导出功能
### Quick Start:
参考：  
com.kvn.poi.export_test.ForeachTest.java  
com.kvn.poi.export_test.MixTemplateTest.java  
com.kvn.poi.export_test.MultiPoiForeachTest.java  
  
**API:**  
>
	PoiExporter.export2Destination(InputStream templateInputStream, Map  rootObjectMap, OutputStream des)
**模板示例**  

## 普通模板：  
![foreach](img/foreach.png)  

## 复杂模板——多个foreach模板：  
![多个foreach](img/多个foreach.jpg)  
  
## 复杂模板——混合模板：  
![混合模板](img/混合模板.jpg)  
  
## excel模板导入
支持简洁易用的excel导入API  
### Quick Start:
参考:  
com.kvn.poi.import_test.ImportRawTest.java  
com.kvn.poi.import_test.ImportGenericTest.java  
  
**API**
>
	PoiSheetVo sheetVo = PoiImporter.importFirstSheetFrom(is);

>
	PoiGenericSheetVo  genericSheetVo = PoiImporter.importFirstSheetFrom(is, OrderImportVo.class);

# 计划  
1. 后续可以考虑使用MyBatis解析动态SQL的思想，来扩展属性占位符（${}、#{}等）和数据来源（rootObjectMap，可以有多来源），将属性占位符和数据来源解耦




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8a7b90cbd964c0b4d6615dae18f3428b649629f216060ab9fee98ba9f3647dff7d1e38843d518d107443715e0b912f8c)