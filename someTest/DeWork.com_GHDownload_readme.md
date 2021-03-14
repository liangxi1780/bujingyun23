# GHDownload
## 一、How to use?
**Step1:**
```java 
String url = "http://gh-game.oss-cn-hangzhou.aliyuncs.com/1434794302961350.apk";
DownloadEntry entry = new DownloadEntry(url);
entry.name = "x三国.apk";
```
**Step2:**
*To start a downloading task:*
```java 
DownloadManager.getInstance(MainActivity.this).add(entry);
```
*To pausea downloading task:*
```java 
DownloadManager.getInstance(MainActivity.this).pause(entry);
```
*To resume downloading task:*
```java 
DownloadManager.getInstance(MainActivity.this).resume(entry);
```
*To resume cencel task:*
```java 
DownloadManager.getInstance(MainActivity.this).cancel(entry);
```
**Step3:**
    If you want to receive process information of downloading task, you should add observer in current Class,for example, in MainActivity:
    
*(1)Create a datawatcher to receive notification.*
```java 
       private DataWatcher dataWatcher = new DataWatcher() {

		@Override
		public void onDataChanged(DownloadEntry data) {
			entry = data;
			showText.setText(entry.toString());
		}
	};
```
*(2)Add observer.*
```java 
    @Override
    protected void onResume() {
        super.onResume();
		DownloadManager.getInstance(this).addObserver(dataWatcher);
    }
```
*(3)Remove observer.*
```java 
    @Override
    protected void onPause() {
        super.onPause();
        DownloadManager.getInstance(this).removeObserver(dataWatcher);
    }
```
## 二、Set download config
In DownloadConfig.java
You can set max downloading task and max downloading threads.

If you set max_download_threads to 1,it will use FileOutputStream instead of RandomAccessFile, which is faster. Otherwise, it will use RandomAccessFile.


```java 
private int max_download_tasks = 3;
private int max_download_threads = 3;
public static String DOWNLOAD_PATH = Environment.getExternalStorageDirectory() + File.separator +
    		"gh-download" + File.separator;
```
##备注：
（1）该下载框架使用了ormlite框架

（2）如果使用生成的ghdownloadv1.2.jar作为引用的jar包，注意要把ormlite的jar包也一起引用

（3）在AndroidManifest.xml中要添加如下service：
```java
 
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e13b918ade265d509c24d3bae1bd4004c3dfacabdd0ce9b1c409775e2e1c7ad7f8fb3f0357d20abfee4b31f798661223a)