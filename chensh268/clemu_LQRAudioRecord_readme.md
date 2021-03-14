# LQRAudioRecord
本库集成录音与播音功能，使用简单方便，让IM集成语音不再是难题。


## 一、简述
该库可进行语音录制及播放，方便IM项目集成语音功能。

1. 录音可获取分贝，并默认回传10秒倒计时。
1. 播放时贴耳自动转为听筒播放，离耳时转公放。


以下是Demo效果：

![image](/screenshots/1.gif)

[DemoApp下载](app-debug.apk)



## 二、引用初始化
### 1、依赖

	compile 'com.lqr.audio:library:1.0.0'

### 2、权限

     
     
     
     
     
     

## 三、集成

### 1、常规设置
#### 1)设置最大时长：

	//默认时长60秒
	AudioRecordManager.getInstance(this).setMaxVoiceDuration(120);


#### 2)设置语音位置：

	//该库内不对文件夹是否存在进行判断，所以请在你的项目中自行判断
    mAudioDir = new File(Environment.getExternalStorageDirectory(), "LQR_AUDIO");
    if (!mAudioDir.exists()) {
        mAudioDir.mkdirs();
    }

    AudioRecordManager.getInstance(this).setAudioSavePath(mAudioDir.getAbsolutePath());

### 2、录音

录音使用的是 AudioRecordManager 类。

#### 1)基本方法：

	//开始录音
	AudioRecordManager.getInstance(MainActivity.this).startRecord();
	
	//将要取消录音（参与微信手指上滑）
	AudioRecordManager.getInstance(MainActivity.this).willCancelRecord();
	
	//继续录音（参与微信手指上滑后加下滑回到原位）
	AudioRecordManager.getInstance(MainActivity.this).continueRecord();
	
	//停止录音
	AudioRecordManager.getInstance(MainActivity.this).stopRecord();
	
	//销毁录音
	AudioRecordManager.getInstance(MainActivity.this).destroyRecord();

#### 2)录音监听：
该库提供IAudioRecordListener接口，方便用户对录音中不同事件进行处理，具体使用请参考DEMO代码（代码较多，请根据自己的项目修改），接口描述：

	public interface IAudioRecordListener {
	
	    /**
	     * 初始化提示视图
	     */
	    void initTipView();
	
	    /**
	     * 设置倒计时提示视图
	     *
	     * @param counter 10秒倒计时
	     */
	    void setTimeoutTipView(int counter);
	
	    /**
	     * 设置正在录制提示视图
	     */
	    void setRecordingTipView();
	
	    /**
	     * 设置语音长度太短提示视图
	     */
	    void setAudioShortTipView();
	
	    /**
	     * 设置取消提示视图
	     */
	    void setCancelTipView();
	
	    /**
	     * 销毁提示视图
	     */
	    void destroyTipView();
	
	    /**
	     * 开始录制
	     * 如果是做IM的话，这里可以发送一个消息，如：对方正在讲话
	     */
	    void onStartRecord();
	
	    /**
	     * 录制结束
	     *
	     * @param audioPath 语音文件路径
	     * @param duration  语音文件时长
	     */
	    void onFinish(Uri audioPath, int duration);
	
	    /**
	     * 分贝改变
	     *
	     * @param db 分贝
	     */
	    void onAudioDBChanged(int db);
	
	}


### 2、播音

播音使用的是 AudioPlayManager 类。

#### 1)开始播放：

	AudioPlayManager.getInstance().startPlay(MainActivity.this, audioUri, new IAudioPlayListener() {
	    @Override
	    public void onStart(Uri var1) {
	        //开播（一般是开始语音消息动画）
	    }
	
	    @Override
	    public void onStop(Uri var1) {
	        //停播（一般是停止语音消息动画）
	    }
	
	    @Override
	    public void onComplete(Uri var1) {
	        //播完（一般是停止语音消息动画）
	    }
	});

#### 2)结束播放：

	AudioPlayManager.getInstance().stopPlay();



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7b5b358fd3762bb8afde634778238f90c12cca945634345959be8c3a71cf50d7d3614a221f3efa76928f0fda6cc4e3b7)