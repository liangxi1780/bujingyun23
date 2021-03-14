#介绍
stetho是facebook开发的，通过chrome的开发者工具来辅助安卓开发。
在这里介绍2个功能：

* 通过Network标签观察网络请求。
  
* 通过Resources标签查看本地数据，比如sqlite数据库，sharepreference等等。同时可以在这里执行sql语句。

#使用
1.项目添加依赖。
 
    compile 'com.facebook.stetho:stetho:1.3.1'
    compile 'com.facebook.stetho:stetho-okhttp3:1.3.1'
 

2.初始化 Stetho
 
    @Override
    public void onCreate() {
        super.onCreate();
        String processName = getProcessName(this);
        if (processName !=null ){
            if (processName.equals("com.a_sq")){//只有在住进程中才初始化数据，在com.a_sq:pushcore、com.a_sq:ipc、io.rong.push、com.a_sq:remote不做初始化
                if (getApplicationInfo().packageName.equals(getCurProcessName(getApplicationContext()))) {
                    initData();
                }
                iniX5WebView();
                initThirdPartyLogin();
            }
        }
        Stetho.initializeWithDefaults(this);
    }
 

3.添加拦截器
 
    public static OKHttpUtils getInstance(Context context) {
        if (instance == null) {
            instance = new OKHttpUtils(context);
            OkGo.getInstance().getOkHttpClientBuilder().addNetworkInterceptor(new StethoInterceptor());
        }
        return instance;
    }
 

4.运行App, 打开Chrome输入  chrome://inspect 


# 使用截图
因为发现有的时候Androd Monitor打印不完全
![unprint](ignoredPrint.png)

![使用截图](showexample.png)
![使用截图2](showexample2.png)







 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e63b7bfc097b80e1e80adf66ad011113399dbaf555cab58fc0e1df0769a2420be69811a069accb22e601d79b336781904)