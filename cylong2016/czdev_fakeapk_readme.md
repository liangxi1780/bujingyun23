# fakeapk

功能强大的android hook 工具，全部开源，配合 xposed 神器使用  



可配合盘古后台系统,  lua脚本 等工具使用。

|工具名称| 下载链接|备注|
|----|-----|---|
|盘古后台系统|https://gitee.com/kuangyufei/pangu|盘古系统后台|
|lua|https://gitee.com/kuangyufei/luaforad|可刷多种广告SDK 脚本工具|
|盘古VPN系统|https://gitee.com/kuangyufei/pangu_vpn|vpn自动选择，切换工具|
|盘古管理系统|https://gitee.com/kuangyufei/pangu_manage|实时查看各广告平台刷量数据，包括留存比例，水军量，转化率等等|

### 联系作者
QQ群 720098517  微信：15817321796  验证注明：fakeapk 
```

/**
 * Created by turingkuang on 2017/1/9.
 */
public class SystemPropertiesHook extends XC_MethodHook {
    public SystemPropertiesHook() {
        super();
    }

    protected void beforeHookedMethod(MethodHookParam param) throws Throwable {
        String methodName = param.method.getName();
        if (methodName.startsWith("get")) {
            if (!TextUtils.isEmpty(SharedPref.getXValue("Build.HARDWARE"))) {
                KernelLogUtil.LogXposed("SystemPropertiesHook -Build.HARDWARE- " + SharedPref.getXValue("Build.HARDWARE"));
                XposedHelpers.setStaticObjectField(android.os.Build.class, "HARDWARE", SharedPref.getXValue("Build.HARDWARE"));
            }

            if (!TextUtils.isEmpty(SharedPref.getXValue("Build.PRODUCT"))) {
                KernelLogUtil.LogXposed("SystemPropertiesHook -Build.PRODUCT- " + SharedPref.getXValue("Build.PRODUCT"));
                XposedHelpers.setStaticObjectField(android.os.Build.class, "PRODUCT", SharedPref.getXValue("Build.PRODUCT"));
            }

            if (!TextUtils.isEmpty(SharedPref.getXValue("Build.DEVICE"))) {
                KernelLogUtil.LogXposed("SystemPropertiesHook -Build.DEVICE- " + SharedPref.getXValue("Build.DEVICE"));
                XposedHelpers.setStaticObjectField(android.os.Build.class, "DEVICE", SharedPref.getXValue("Build.DEVICE"));
            }

            if (!TextUtils.isEmpty(SharedPref.getXValue("Build.CPU_ABI"))) {
                KernelLogUtil.LogXposed("SystemPropertiesHook -Build.CPU_ABI- " + SharedPref.getXValue("Build.CPU_ABI"));
                XposedHelpers.setStaticObjectField(android.os.Build.class, "CPU_ABI", SharedPref.getXValue("Build.CPU_ABI"));
            }


            if (!TextUtils.isEmpty(SharedPref.getXValue("Build.MODEL"))) {
                KernelLogUtil.LogXposed("SystemPropertiesHook -Build.MODEL- " + SharedPref.getXValue("Build.MODEL"));
                XposedHelpers.setStaticObjectField(android.os.Build.class, "MODEL", SharedPref.getXValue("Build.MODEL"));
            }

            if (!TextUtils.isEmpty(SharedPref.getXValue("Build.MANUFACTURER"))) {
                KernelLogUtil.LogXposed("SystemPropertiesHook -Build.MANUFACTURER- " + SharedPref.getXValue("Build.MANUFACTURER"));
                XposedHelpers.setStaticObjectField(android.os.Build.class, "MANUFACTURER", SharedPref.getXValue("Build.MANUFACTURER"));
            }

				
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb517862345b8f76c201b1d41d4676fd8ca8cb50fe04a6905e71d51df01d1364c7b749ba2ad233027d1eb8d8b3e131a81)