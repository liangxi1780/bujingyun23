Droid Plugin
======

[中文文档](readme_cn.md "中文文档")

[Fllow me at github](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465a64258a8c7af13f1692158f98b17cdd) 

DroidPlugin is a new **Plugin Framework** developed and maintained by Andy Zhang( [Fllow me at github](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465a64258a8c7af13f1692158f98b17cdd)  ).
It enables the host app run any third-party apk without installation, modification and repackage, which benefit a lot for collaborative development on Android.

-------



## Problems to be solved:
    
 1. Unable to send `Notification` with custom Resources，eg：
 
     a.  Notification with custom RemoteLayout, which means `Notification`'s `contentView`，`tickerView`，
     `bigContentView` and `headsUpContentView` must be null.

     b.  Notification with icon customized by R.drawable.XXX. The framework will transform it to Bitmap instead.

 2. Unable to define specified `Intent Filter` for the plugged app's `Service`、`Activity`、`BroadcastReceiver`
 and `ContentProvider`. So the plugged app is invisible for the outside system and app.

 3. Lack of `Hook` to the `Native` layer, thus apk (e.g. a majority of game apps) with `native` code cannot be loaded as plugin.
    
## Features：
  1. Compatible to Android 2.3 and later versions
  2. Given its .apk file, the plugged app could be run either independently or as plugin of the host, **NO** source code needed.
  3. Unnecessary to register the plugged app's `Service`、`Activity`、`BroadcastReceiver`、`ContentProvider` in the host.
  4. The plugged app are recognized as *Installed* by the host and other plugged apps
  5. Very low level of code invasion, in deed just one line code to integrate DroidPlugin into the host app.
  6. Complete code level separation between host and plugged apps, only system level message passing method provide by Android allowed.
  7. All system API supported
  8. Resources management are also completely separated between host and plugged apps.
  9. Process management for plugged apps, idle processed of the plugged app will be timely recycled to guarantee minimum memory usage.
  10. Static broadcast of plugged app will be treated as dynamic, thus the static broadcasting will never be trigger if
  the plugged app are not activated.
    
## Usage：

#### Integrate with the host apps

It is very simple integrate Droid Plugin to your proejct：

1. Import Droid Plugin project to your project as a lib.

2. Include following attributes in host's `AndroidManifest.xml`：
	
		 

           
3. Or, if you use customized `Application`，add following code in the methods `onCreate` and `attachBaseContext`:
    
		@Override
		public void onCreate() {
			super.onCreate();
			PluginHelper.getInstance().applicationOnCreate(getBaseContext()); //must be after super.onCreate()
		}
        
		@Override
		protected void attachBaseContext(Context base) {
			PluginHelper.getInstance().applicationAttachBaseContext(base);
            super.attachBaseContext(base);
		}

4. Modify the `authorityName` value in `Libraries\DroidPlugin\build.gradle` (suggested use your package name)

#### Install、Uninstall or Upgrade the plugged app：

1. **Install/Upgrade**, use this method：
 
		int PluginManager.getInstance().installPackage(String filepath, int flags);
   
	For installation, `filepath` set to path of the .apk file, and `flags` set to 0.

	For upgrade, `filepath` set to path of the .apk file, and  `flags` set to `PackageManagerCompat.INSTALL_REPLACE_EXISTING`.
        
    
2. **Uninstall**, use this method：

		int PluginManager.getInstance().deletePackage(String packageName,int flags);

	`packageName` is package name of the plugged app，`flags = 0`。

3. **Activate**

    Just use android's API, same for communication between components.
	
## FAQ
	
 [FAQ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465dead720b075b3c042d85acf65cbf169434d028b87bce739291ff22a5c6c7771ab479e3d6628b728c20d9bdb5a6e46c2  "FAQ")
	
## Remark：

Please feel free to [report bugs](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046169d4468afc3386dabfb50ed32457fe241ba3e34a6e25cffcd073b8f8cb0b84c)  or ask for help via email.
QQ Group:318901026

##Who is using Droid Plugin?
	
 [360 App Store](http://u.720life.cn/g/10ceb7466ef8f41c56bcbb670b8777f2  "360 App Store")

    
### Thanks：
    
    Translated by Ming Song（gnosoir@hotmail.com）    



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)