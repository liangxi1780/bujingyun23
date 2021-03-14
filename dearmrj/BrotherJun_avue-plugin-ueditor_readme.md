# avue-plugin-ueditor

## avue 富文本编辑器

## Avue官网
[https://avuejs.com](http://u.720life.cn/g/92a435aed1de8a1a05a3bdec07fd0a4eb08baf395e0990b52d0bb8f7e0f7b1ae)

## 介绍
[avue-plugin-ueditor](http://u.720life.cn/g/92a435aed1de8a1a05a3bdec07fd0a4e29f280b68919cc425009c78b45faa0d131f9544b82b6be4bd2ccdb9f6d5fe029)

## npm
[avue-plugin-ueditor](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c96b269d82f8e7d4e292dc135232f271dee2b9e588138620b36ab3d0b5cf3a1f7662b91c7223d5bbfb408df3a9003c8e145)

## git
[avue-plugin-ueditor](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9a45ea68dd78dd93ab4ce0a12f91adcfb82e8b33e1f00d45dbadba75feb55e47bb40a737d1b9ca0b420c634d3bf5745d)

## demo
 
   
 

## use
```
1.安装
npm install avue-plugin-ueditor --save

2.导入
import AvueUeditor from 'avue-plugin-ueditor'
Vue.use(AvueUeditor);

3.使用(双击图片可改变大小)
...
column:[
  ...
    {
      label:'test',
      prop:'test',
      component: "avueUeditor",
      options:{
        //普通图片上传
        action: "https://avuejs.com/upload",
        props: {
          res: "data",
          url:'url'
        },
        //七牛云oss配置
        qiniu: {
          AK: "",
          SK: "",
          scope: "test",
          url: "http://pm7cc17lu.bkt.clouddn.com/",
          deadline: 1
        },
        //阿里云oss配置
        ali: {
          region: "oss-cn-beijing",
          endpoint: "oss-cn-beijing.aliyuncs.com",
          accessKeyId: "",
          accessKeySecret: "",
          bucket: "avue"
        }
      }
    }
  ...
]
或者直接
  

4.图片上传配置————(支持oss,支持ctrl+v粘贴图片)
具体用法参考https://avuex.avue.top/#/doc/form-upload
upload: {
  //普通图片上传
  action: "https://avuejs.com/upload",
  props: {
    res: "data",
    url:'url'
  },
  //七牛云oss配置
  qiniu: {
    AK: "",
    SK: "",
    scope: "test",
    url: "http://pm7cc17lu.bkt.clouddn.com/",
    deadline: 1
  },
  //阿里云oss配置
  ali: {
    region: "oss-cn-beijing",
    endpoint: "oss-cn-beijing.aliyuncs.com",
    accessKeyId: "",
    accessKeySecret: "",
    bucket: "avue"
  }
}
...
```




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e88c8edd63a99d18fdb0d2b3a944f123f3bc345475e8ade924e02d514281ba9bc32599fc8bffc3e908214d31007a08d46fdf156afd9eeafa3063090bed35fd4ba)