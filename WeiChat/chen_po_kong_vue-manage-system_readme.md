# vue-manage-system

 
     
   
   
     
   
   
     
   
   
     
   
   
     
   

基于 Vue + Element UI 的后台管理系统解决方案。[线上地址](http://u.720life.cn/g/8b2cc2a70fff81585a5fc8c347fc6c902d17d1f9e68d5117b1a7b077387ba31938f882588a8bdeaaa1375d1332cff14f)

> React + Ant Design 的版本正在开发中，仓库地址：[react-manage-system](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304605f9b1e71b0f94c1070388ce97c12d4b6560b7f2a537dcb6c7909be5200c13b2)

[English document](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304687164aeaa5a428faf00dba31b0e564adbaab341df646a69bc5e77cc50b84cf2d6041f3c7e78d820a848faa4421aef8a59a64c1d86f9d19e6edf431310aca6629)

## 项目截图

### 登录

![Image text](https://github.com/lin-xin/manage-system/raw/master/screenshots/wms3.png)

### 默认皮肤

![Image text](https://github.com/lin-xin/manage-system/raw/master/screenshots/wms1.png)

### 浅绿色皮肤

![Image text](https://github.com/lin-xin/manage-system/raw/master/screenshots/wms2.png)

## 赞赏

请作者喝杯咖啡吧！(微信号：linxin_20)

![微信扫一扫](https://lin-xin.gitee.io/images/weixin.jpg)

## 特别鸣谢

- [实验楼](http://u.720life.cn/g/5548c6c8eb0c0de8c16249cde4dfa3ef22643d6b29b53ce7cd7fc2a917c96a91b1cd0d452e9f57bb55034e32fd33c693abf52ac12b39c75e21127969e2645853)

## 前言

该方案作为一套多功能的后台框架模板，适用于绝大部分的后台管理系统（Web Management System）开发。基于 vue.js，使用 vue-cli3 脚手架，引用 Element UI 组件库，方便开发快速简洁好看的组件。分离颜色样式，支持手动切换主题色，而且很方便使用自定义主题色。

## 功能

-   [x] Element UI
-   [x] 登录/注销
-   [x] Dashboard
-   [x] 表格
-   [x] Tab 选项卡
-   [x] 表单
-   [x] 图表 :bar_chart:
-   [x] 富文本编辑器
-   [x] markdown 编辑器
-   [x] 图片拖拽/裁剪上传
-   [x] 支持切换主题色 :sparkles:
-   [x] 列表拖拽排序
-   [x] 权限测试
-   [x] 404 / 403
-   [x] 三级菜单
-   [x] 自定义图标
-   [x] 可拖拽弹窗
-   [x] 国际化

## 安装步骤

```
git clone https://github.com/lin-xin/vue-manage-system.git      // 把模板下载到本地
cd vue-manage-system    // 进入模板目录
npm install         // 安装项目依赖，等待安装完成之后，安装失败可用 cnpm 或 yarn

// 开启服务器，浏览器访问 http://localhost:8080
npm run serve

// 执行构建命令，生成的dist文件夹放在服务器下即可访问
npm run build
```

## 组件使用说明与演示

### vue-schart

vue.js 封装 sChart.js 的图表组件。访问地址：[vue-schart](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c37976dc5332da01b74029fc1ea45e580d0c298c56ee3841cd650eeb2edbb1c)

     

```html
 
     
          
     
 

 
    import Schart from 'vue-schart'; // 导入Schart组件
    export default {
        data() {
            return {
                options: {
                    type: 'bar',
                    title: {
                        text: '最近一周各品类销售图'
                    },
                    labels: ['周一', '周二', '周三', '周四', '周五'],
                    datasets: [
                        {
                            label: '家电',
                            data: [234, 278, 270, 190, 230]
                        },
                        {
                            label: '百货',
                            data: [164, 178, 190, 135, 160]
                        },
                        {
                            label: '食品',
                            data: [144, 198, 150, 235, 120]
                        }
                    ]
                }
            };
        },
        components: {
            Schart
        }
    };
 
 
    .wrapper {
        width: 7rem;
        height: 5rem;
    }
 
```

## 其他注意事项

### 一、如果我不想用到上面的某些组件呢，那我怎么在模板中删除掉不影响到其他功能呢？

举个栗子，我不想用 Vue-Quill-Editor 这个组件，那我需要分四步走。

第一步：删除该组件的路由，在目录 src/router/index.js 中，找到引入改组件的路由，删除下面这段代码。

```JavaScript
{
    // 富文本编辑器组件
    path: '/editor',
    component: resolve => require(['../components/page/VueEditor.vue'], resolve)
},
```

第二步：删除引入该组件的文件。在目录 src/components/page/ 删除 VueEditor.vue 文件。

第三步：删除该页面的入口。在目录 src/components/common/Sidebar.vue 中，找到该入口，删除下面这段代码。

```js
{
	index: 'editor',
	title: '富文本编辑器'
},
```

第四步：卸载该组件。执行以下命令：
npm un vue-quill-editor -S

完成。

### 二、如何切换主题色呢？

第一步：打开 src/main.js 文件，找到引入 element 样式的地方，换成浅绿色主题。

```javascript
import 'element-ui/lib/theme-default/index.css'; // 默认主题
// import './assets/css/theme-green/index.css';       // 浅绿色主题
```

第二步：打开 src/App.vue 文件，找到 style 标签引入样式的地方，切换成浅绿色主题。

```javascript
@import "./assets/css/main.css";
@import "./assets/css/color-dark.css";     /*深色主题*/
/*@import "./assets/css/theme-green/color-green.css";   !*浅绿色主题*!*/
```

第三步：打开 src/components/common/Sidebar.vue 文件，找到 el-menu 标签，把 background-color/text-color/active-text-color 属性去掉即可。

## License

[MIT](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304618a3aff891ac88b934431de793b153d32b21e2b15c6ed1cd799666340a72cecf08df42c24a28f4e02d54b9ad71bc4382)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecbf9b467f42e11085fc1ba1471b6ea87de6fa08776804bd8e2844eb6a9ad573b5dbef2bf542455db7964353a081ecebf214e60c733f25578ee50aee6a83aea1a)