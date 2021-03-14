XHTextField
===========

中文：类似微信的用户头像选择、系统信息App的手势控制键盘隐藏，还有自定义9种输入风格，比如输入Email并检查是否正确、输入密码检查是否输入正确、输入生日自动帮你选择星座、自定义textField的leftView的图标等功能，注意：还有输入错误的标识提示哦！ 


English: micro letter like avatars selection, system information App gesture keypad, and custom style 9 kinds of input, such as input Email and check whether it is right, input the password check whether correct, input automatically help you choose birthday constellation, customize the textField leftView ICONS, and other functions, note: there are input error identification tips!

![image](https://github.com/JackTeam/XHTextField/raw/master/Screenshots/TextField.gif)

##安装
##Installation

中文:      [CocosPods](http://u.720life.cn/g/e60dfcae3b7014a8d0426fa45faea75d1065e1cd79ddbaf0550b213aca9f8ff4)安装XHMediaRecorder的推荐方法,只是在Podfile添加以下行:

english:   [CocosPods](http://u.720life.cn/g/e60dfcae3b7014a8d0426fa45faea75d1065e1cd79ddbaf0550b213aca9f8ff4) is the recommended methods of installation XHMediaRecorder, just add the following line to `Profile`:

## Profile

```
pod 'XHTextField'
```

## 例子
## Example

```objective-c
- (void)_setup {
    XHTextField *emailTextField = [[XHTextField alloc] initWithFrame:CGRectMake(0, 0, 100, 35)];
    [emailTextField setFieldType:kXHEmailField];
    // diss keyboard gesture
    UIPanGestureRecognizer *pan = [[UIPanGestureRecognizer alloc] init];
    XHTextFieldScrollView *scrollView = [[XHTextFieldScrollView alloc] initWithFrame:self.view.bounds];
    [scrollView setDismissivePanGestureRecognizer:pan];
    [scrollView addSubview:emailTextField];
    [self.view addSubview:scrollView];
}

- (void)viewDidLoad {
    [self _setup];
}
```

### Thank you

[mehfuzh](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f2399e724cd5190b540eb45e1f5225a6) 

## License

中文:      XHTextField 是在MIT协议下使用的，可以在LICENSE文件里面找到相关的使用协议信息.

English:   XHTextField is acailable under the MIT license, see the LICENSE file for more information.




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed104d2935b1aecfa488c8181231302e923eeba4567cb1338faeb4325bb43722f06cbacc20a3e5287a65a643491da041b)