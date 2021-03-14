  

 v-region 

  

   

 
  A simple region selector for  Vue2 , provide Chinese administrative division data
 

 
     
     
     
 
     

## Demo、Document、Changelog
Explorer on

- [English site](http://u.720life.cn/g/123c34d3274be70aa487f42c1f6cf8e28d0fdef1e38de31fc014ba2f99c80de0119f3a6c4cc2b21f03ff9f1bd88cfd6e)
- [国内站点](http://u.720life.cn/g/123c34d3274be70aa487f42c1f6cf8e26c43760d0b486aa38f0f9d4a7f953007275e986e251172822f7be9e3f33e81e2)


  

## Vue plugin series

| Plugin | Status | Description |
| :---------------- | :-- | :-- |
| [v-page](https://github.com/TerryZ/v-page) | [![npm version](https://img.shields.io/npm/v/v-page.svg)](https://www.npmjs.com/package/v-page) | A simple pagination bar, including length Menu, i18n support |
| [v-dialogs](https://github.com/TerryZ/v-dialogs) | [![npm version](https://img.shields.io/npm/v/v-dialogs.svg)](https://www.npmjs.com/package/v-dialogs) | A simple and powerful dialog, including Modal, Alert, Mask and Toast modes |
| [v-tablegrid](https://github.com/TerryZ/v-tablegrid) | [![npm version](https://img.shields.io/npm/v/v-tablegrid.svg)](https://www.npmjs.com/package/v-tablegrid) | A simpler to use and practical datatable |
| [v-uploader](https://github.com/TerryZ/v-uploader) | [![npm version](https://img.shields.io/npm/v/v-uploader.svg)](https://www.npmjs.com/package/v-uploader) | A Vue2 plugin to make files upload simple and easier,  you can drag files or select file in dialog to upload |
| [v-ztree](https://github.com/TerryZ/v-ztree) | [![npm version](https://img.shields.io/npm/v/v-ztree.svg)](https://www.npmjs.com/package/v-ztree) | A simple tree for Vue2, support single or multiple(check) select tree,  and support server side data |
| [v-gallery](https://github.com/TerryZ/v-gallery) | [![npm version](https://img.shields.io/npm/v/v-gallery.svg)](https://www.npmjs.com/package/v-gallery) | A Vue2 plugin make browsing images in gallery |
| [v-region](https://github.com/TerryZ/v-region) | [![npm version](https://img.shields.io/npm/v/v-region.svg)](https://www.npmjs.com/package/v-region) | A simple region selector, provide Chinese administrative division data |
| [v-selectpage](https://github.com/TerryZ/v-selectpage) | [![npm version](https://img.shields.io/npm/v/v-selectpage.svg)](https://www.npmjs.com/package/v-selectpage) | A powerful selector for Vue2, list or table view of pagination,  use tags for multiple selection, i18n and server side resources supports |

  


## Plugin preview

*form element mode*

![base](https://terryz.github.io/image/v-region/v-region-base.png)

*dropdown selector mode*

![ui](https://terryz.github.io/image/v-region/v-region-ui.png)

  

## Install

``` bash
npm install v-region --save
```

Include plugin in your `main.js` file.

```js
import Vue from 'vue'
import vRegion from 'v-region';
Vue.use(vRegion);
```

## Deploy on your component(base mode)

template code

```html
 
      
 
```

script code

```js
export default {
    methods:{
        //receive selected region data
        regionChange(data){
            console.log(data);
        }
    }
};
```

## Data Source

region data come from repo: [mumuy/data_location](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046243fde6ddd9286b2d0f20b26cdcbc52e0e85ff05846462b127fdc5754d9af1fb)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4e68527d3533b49e285203600f77f59a23207c43c883fce47cd3c226afc836696c423f17d91f71b95b9ad8e4f641d260)