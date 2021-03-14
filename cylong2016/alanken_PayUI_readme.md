# PayUI


#### 预览
![](https://user-gold-cdn.xitu.io/2017/4/24/0d7f90c1447ecf0f54180a9c76917502.gif)

#### 使用
这个弹出层是一个DialogFragment，逻辑都封装在其内部，使用起来很简单：

```
Bundle bundle = new Bundle();
bundle.putString(PayFragment.EXTRA_CONTENT, "提现：¥ " + 100.00);

PayFragment fragment = new PayFragment();
fragment.setArguments(bundle);
fragment.setPaySuccessCallBack(MainActivity.this);
fragment.show(getSupportFragmentManager(), "Pay");
```

通过InputCallBack接口回调输入的支付密码，可以在回调方法中请求判断支付密码是不是正确的，也可以在PayFragment内部自己修改判断，没有用到什么高深的技术，大家看代码自然就明白了。

博客地址: [Blog](http://u.720life.cn/g/79d96dd72e2b62e4f2e2f0525f0cdb29023d1d58bb9bf11c5049d28a76846d06)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ebdb4e354e9809e4c884d5516ccd19d81a8a6a424be78c1d4323160bdd842c0a6533352a740104fdbe38a36891b686f7a)