# vue3_base
#### 基于vue-cli3 基础框架

##### 1. 通过不同的指令配置切换环境
``` 
dev环境:
npm run dev 

生产环境
npm run build

第三方库单独打包
npm run dll

简单的eslint自动修复指令（譬如空格，一些简单的语法错误）
npm run lint

```
##### 2. 第三方库单独打包

```
第三方库比如vue,vuex,axios,vue-router,等等不需要经常修改的，打包一次就行，只需要编译业务逻辑代码
1、在webpack.dll.conf.js entry里增加第三方库文件配置文件

2、npm run dll 将所有的第三库都打包到vendor.dll.js 会自动注入到index.html
```
##### 3.接口
```
apiUrl.js 定义接口url

  const api = {
    'login': 'XXX'
  }

api.js 

  export async function handleLogin (params = {}{
    const res = await fetchPost(api.login, params)
    return res
  }
```

##### 4.store
公用到方法，变量可以放store




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e31a42238eea822fb9e5dd3dfec13c08959cf25226826f4067ea94087b7459a78236f51189c3f9c542f548c2e673fc5a4)