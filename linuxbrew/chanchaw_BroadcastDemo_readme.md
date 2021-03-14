#### 概述

本文介绍两种注册方式的广播：动态注册（ ``JAVA代码``）、静态（ 在清单文件``AndroidManifest.xml`` 中注册）

#### 动态注册广播接收器

达到的效果：在 ``app`` 的 ``MainActivity`` 中发送广播消息的按钮点击后给出下面几个反馈：

1. 向 ``MainActivity`` 中的 ``EditText`` 中写入文字
2. 弹出 ``Toast``
3. 打印 ``Logcat``

创建项目的操作就略过了，下面开始每个模块的制作以及代码：

1. 制作 ``MainActivity`` 的布局文件 ``acitvity_main``，其完整代码如下：

   ```xml
    
    
   
        
       
        
       
        
    
   ```

2. 制作 ``MainActivity`` ，其完整代码如下：

   ```java
   package com.ccsoft.broadcastdemo;
   
   import android.app.Activity;
   import android.content.Intent;
   import android.content.IntentFilter;
   import android.os.Bundle;
   import android.view.View;
   import android.widget.Button;
   import android.widget.EditText;
   
   
   public class MainActivity extends Activity implements View.OnClickListener {
       MyReceiver myReceiver;
       IntentFilter intentFilter;
       EditText etReceivedBroadcast;
       Button btnSendBroadcast;
       @Override
       protected void onCreate(Bundle savedInstanceState) {
           super.onCreate(savedInstanceState);
           setContentView(R.layout.activit_main);
   
           etReceivedBroadcast = (EditText) findViewById(R.id.etReceivedBroadcast);
           btnSendBroadcast = (Button) findViewById(R.id.btnSendBroadcast);
   
           //keep reference to Activity context
           MyApplication myApplication = (MyApplication) this.getApplicationContext();
           myApplication.mainActivity = this;
   
           btnSendBroadcast.setOnClickListener(this);
   
           myReceiver = new MyReceiver();
           intentFilter = new IntentFilter("chanchawReceiver");
       }
   
       @Override
       protected void onResume() {
           super.onResume();
           registerReceiver(myReceiver, intentFilter);
   
       }
       @Override
       protected void onPause() {
           super.onPause();
           unregisterReceiver(myReceiver);
       }
   
   
       @Override
       public void onClick(View view) {
   
           Intent intent = new Intent("chanchawReceiver");
           sendBroadcast(intent);
   
       }
   }
   ```

3. 上面步骤贴到项目中后会有些类、对象不存在造成报错，先别着急，布置完全部代码后即可正常运行。步骤2中用到的 ``MyApplication`` 的完整代码如下

   ```java
   package com.ccsoft.broadcastdemo;
   
   import android.app.Application;
   
   public class MyApplication extends Application {
       @Override
       public void onCreate() {
           super.onCreate();
       }
   
       MainActivity mainActivity;
   }
   ```

4. 接收器 ``MyReceiver`` 的完整代码如下：

   ```java
   package com.ccsoft.broadcastdemo;
   
   import android.content.BroadcastReceiver;
   import android.content.Context;
   import android.content.Intent;
   import android.util.Log;
   import android.widget.Toast;
   
   public class MyReceiver extends BroadcastReceiver {
       private static final String TAG = "chanchaw";
   
       @Override
       public void onReceive(Context context, Intent intent) {
           MainActivity mainActivity = ((MyApplication) context.getApplicationContext()).mainActivity;
           mainActivity.etReceivedBroadcast.append("broadcast: "+intent.getAction()+"\n");
           String msg = intent.getStringExtra("msg");
   
           Toast.makeText(context, "接收到了！", Toast.LENGTH_LONG).show();
           Log.i(TAG,"接收到广播的消息了！");
       }
   }
   ```

5. 项目的清单文件 ``AndroidManifest.xml`` 的完整代码如下：

   ```xml
    
   
        
   
            
                
                    
                    
                
            
   
            
                
                    
                
            
   
        
    
   ```

6. 最终形成的项目结构如下图：
   ![](https://user-images.githubusercontent.com/29369287/66265479-d7114280-e849-11e9-99d4-bca340ac817b.png)

#### 代码解释

执行完上面的步骤，所有代码就都贴完了，下面来介绍下必要的知识点。类 ``MyApplication`` 用来绑定整个应用的实例，所以要在清单文件 ``AndroidManifest.xml`` 的 ``application`` 标签中设置属性 ``android:name=".MyApplication"``，该类中声明了 ``MainActivity`` 类型的一个变量，并且在该页面的 ``onCreate`` 事件中绑定该变量：

```java
MyApplication myApplication = (MyApplication) this.getApplicationContext();
myApplication.mainActivity = this;
```

有了上面的准备工作才能在接收器类 ``MyReceiver`` 中使用它进而给 ``MainActivity`` 中的控件赋值，那么本方法也就是实现 “控制反转” - 我自己这么叫 - 在接收器的逻辑中可以修改其他 ``Activity`` 中的数据。

#### 静态注册方式

这里还是要吐槽下的，看的资料年代久远，导致一开始静态注册方式一直测试不通过，后来才发现原来 ``Android 8`` 之后修改了静态注册方式的使用方法，上面的 ``MainActivity`` 中点击按钮发送广播的代码中要设置接收器的包名，之后接收器才能接受到广播，即按钮点击事件的完整代码应该是：

```java
    @Override
    public void onClick(View view) {
        Intent intent = new Intent("chanchawReceiver");
        intent.setPackage("com.ccsoft.broadcastdemo");
        sendBroadcast(intent);
    }
```

同时记得将 ``MainActivity`` 中的重载方法 ``onResume``、``onPause`` 注释掉 - 这两个方法是动态注册时才用到。简单修改后即将 “ 动态注册方式 ” 修改为 “ 静态注册方式 ” 了。

#### 源码

源码地址：https://gitee.com/chanchaw/BroadcastDemo

仓库地址：https://gitee.com/chanchaw/BroadcastDemo.git


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1c6c82105d9b6dd884e5e8a470804df1fe5c2d14ffb3b794fb9eaffca1264ac35857a6a473acf31e0f5a15739cef63a2)