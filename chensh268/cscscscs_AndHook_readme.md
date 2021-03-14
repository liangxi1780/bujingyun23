# AndHook
A dynamic instrumentation framework designed for usage within process scope.

# Support
- Android 4.x or later (with preliminary support for Android 8.1 and 9.0)
- java method instrumentation (hook java method in Java/C/C++)
- native interception (hook native C/C++ functions in C/C++)

# How to use

In `app` module, we use an android project to show how to use the hook toolkit.

## Hook with AndHook

```java
/** Define hook configuration */
public class AndHookConfig {
    /** Hook Activity's onStart() method */
    @HookHelper.Hook(clazz = Activity.class)
    private static void onStart(Activity activity) {
        Log.d(AndTest.LOG_TAG, "onStart: HookedActivity::onStart start, this is " + activity.getClass());
        HookHelper.invokeVoidOrigin(activity);// invoke the origin method
        Log.d(AndTest.LOG_TAG, "onStart: HookedActivity::onStart end, this is " + activity.getClass());
    }
}

public class MainApplication extends Application {
    @Override
    public void onCreate() {
        super.onCreate();
        // Make sure AndHook's native library is loaded first.
        AndHook.ensureNativeLibraryLoaded(null);
        // Then apply hook configuration before target method running.
        HookHelper.applyHooks(AndHookConfig.class);
    }
}

public class MainActivity extends Activity {
    @Override
    protected void onStart() {
        Log.i(TAG, "MainActivity.super::onStart: start");
        super.onStart();// the method which is hooked
        Log.i(TAG, "MainActivity.super::onStart: end");
    }
}

// After MainActivity launched, you will be able to see log in logcat like:
// AndHook_Test: MainActivity.super::onStart: start
// AndHook_Test: onStart: HookedActivity::onStart start, this is class andhook.test.ui.MainActivity
// AndHook_Test: onStart: HookedActivity::onStart end, this is class andhook.test.ui.MainActivity
// AndHook_Test: MainActivity.super::onStart: end
```

# How does AndHook work?
![AndHook](https://github.com/Rprop/AndHook/raw/master/AndHook.png)

# How the method was intercepted?
![CallFlow](https://github.com/Rprop/AndHook/raw/master/CallFlow.png)

# Special Thanks
- cly.comp
- Meow

# References
- [Cydia Substrate](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464f330fd5240fb8f81c266882f4c0fe67d19497aae739f8d2a1198bbcae70dd923ea6bf5e7210f7be96af351bf65479f8b301eee63cc5dea1c749ad65d5a9a6f981a64d4e6e872f15a7c6c6aefdaaa9efbd416f381690a83922c45c75b07e0ed0) (armeabi-v7a, x86, x86_64)
- [And64InlineHook](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461a9beaa981a71b665724532a14bc15f1fc0e9fb19d589bec12c7404a2ace4aa8) (arm64-v8a)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb3d9e58442c299d859b21c2f4d52abeb047ed57ba63d6ca914c5755e9e9aa261dc6eb017dae76bbf4e6871bbb7d6b2f4)