## 一、项目描述

- 一个基于 vue、datav、Echart 框架的 " **数据大屏项目** "，通过 vue 组件实现数据动态刷新渲染，内部图表可实现自由替换。部分图表使用 DataV 自带组件，可进行更改，详情请点击下方 DataV 文档。
- 项目需要全屏展示（按F11）。
- 项目部分区域使用了全局注册方式，增加了打包体积，在实际运用中请使用**按需引入**。
- 拉取项目之后，建议按照自己的功能区域重命名文件，现以简单的位置进行区分。
- 项目环境：vue-cli-3.0、webpack-4.0、npm-6.13、node-v12.16。

友情链接：

1.  [DataV 官方文档（建议使用之前先浏览）](http://u.720life.cn/g/30ae9c4bd22743a10cf81874711aee157b613bbc7ecdfa9119a72cc39401b9b4bd3759efc09ea5995e30e92ff752bfe1)
2.  [echarts 实例](http://u.720life.cn/g/f989f483b7470966b008e44ccf371b7ed02d908690fd6cdc4fb718c39ee37a93abd03471e0c5a8d19aa1b4193fd3e308)，[echarts 官方文档](http://u.720life.cn/g/f989f483b7470966b008e44ccf371b7ec7aa4ad87bc2933acfb2ad3ad58dd11717d78e322b87b4be5be3c1647edee748)
3.  [Vue 官方文档](http://u.720life.cn/g/1eea7f654038e3466b5f7afd82540e026fb743de569442ae210ad68342f4d930c1e91d6de165dd074d224b7eae25e459)
4.  [项目 gitee 地址（国内速度快）](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5bc3e852a46772938153194aa6a123a2abb1af0d6d60161779fb098bba460e38)

项目展示
![项目展示](https://images.gitee.com/uploads/images/2020/0411/221307_0f8af2e7_4964818.gif "20200411_221020.gif")

## 二、主要文件介绍

| 文件                | 作用/功能                                           |
| ------------------- | --------------------------------------------------- |
| mian.js             | 主目录文件，全局引入了引入 vue-awesome              |
| views/ index.vue    | 项目主结构                                          |
| views/其余文件      | 界面各个区域组件（按照位置来命名）ajax 接口请求位置 |
| assets              | 静态资源目录，放置 logo 与背景图片                  |
| assets / style.scss | 通用 CSS 文件，全局项目快捷样式调节                 |
| assets / index.scss | Index 界面的 CSS 文件                               |
| components/echart   | 所有 echart 图表（按照位置来命名）                  |

## 三、使用介绍

1. **如何请求数据**
   现在的项目未使用前后端数据请求，建议使用 axios 进行数据请求，在 main.js 位置进行全局配置，在 views/xx.vue 文件里进行前后端数据请求。

- axios 的 main.js 配置参考范例（因人而异）

```js
import axios from "axios";

//把方法放到vue的原型上，这样就可以全局使用了
Vue.prototype.$http = axios.create({
  //设置20秒超时时间
  timeout: 20000,
  baseURL: "http://172.0.0.1:80080" //这里写后端地址
});
```

- 在 vue 页面中调用 axios 方法并通过 props 传给 echarts 图表子组件

```js
export default {
  data() {
  	ListDataSelf:[]
  },
  mounted() {
   this.fetchList(); //获取数据
  },
  methods: {
	async fetchList(){
	  const { code,listData }= await this.$http.get("xx/xx/xx"x);
	  if(code === 200){
		 this.ListDataSelf= listData;
	  }
	}
  }
 }
```

2. **如何动态渲染图表**
   在`components/echart`下的文件，比如`drawPie()`是渲染函数，`echartData`是需要动态渲染的数据，当外界通过`props`传入新数据，我们可以使用`watch()`方法去监听，一但数据变化就调用`this.drawPie()`并触发内部的`.setOption`函数，重新渲染一次图表。

```js
//这里是子组件内部

props: ["listData"],
watch: {
  listData(newValue) {
     this.echartData= newValue;
     this.drawPie();
   },
  },
methods: {
  drawPie() {
  	.....
  	'渲染节点名称'.setOption(option);
  }
 }
```

3. **如何更换边框**
   边框是使用了 DataV 自带的组件，如：

```html
  
```

只需要去 views 目录下去寻找对应的位置去查找并替换就可以，具体的种类请去 DavaV 官网查看

4. **如何更换图表**
   直接进入 components/echart 下的文件修改成你要的 echarts 模样，可以去[echarts 官方社区](http://u.720life.cn/g/844c3c0219f411acdf3934ffcbaa9dba1fdcb4759b8e5b140b8979173111507136a397d76234752914076e20fe17c33502934678f1b1bb5c9f27f4b31ccf46936e53fb38f4fb87f8ab237d4758da1c71)里面查看案例。

## 四、更新情况

如果大家有意见请进行评论，我也会尽力去更新，自己也在前端学习的路上，欢迎交流，非常感谢！



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e23129ded72cefe8e80bd0089f097cc5d88414f49fc0275c9a1fa91a9b3c5d016272f951d47f8963d08c7ff3ab23da969a800b3891445f7a879cdb5f7e0f4a4c9)