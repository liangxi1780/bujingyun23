[PHPRAP，是一个PHP轻量级开源API接口文档管理系统，致力于减少前后端沟通成本，提高团队协作开发效率，打造PHP版的RAP。](http://u.720life.cn/g/ba9734e5b67a4f1c8a127330668c82eecf7d1f67223e8ba82ca96bafa7174da1)

 >版本说明
 - master：演示版本，和[apidoc.gouguoyin.cn](http://u.720life.cn/g/2749c20c002cf3334f42b242ba1f6d68e62babab516d2743cfd9d322de62a3fc)看到的效果一致，请不要下载安装 
 - demo：最新版本，功能最新，但不稳定，不建议下载安装 
 - stable：稳定版本，建议下载安装，下载[源码](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b7360d65513d5453396e134c13e7b0f440e229ef16c0d8694eacf914f91c64eabd2598b28de1295214f8882964223458)
 
## 相关
 - 官方网站：[phprap.gouguoyin.cn](http://u.720life.cn/g/ba9734e5b67a4f1c8a127330668c82eecf7d1f67223e8ba82ca96bafa7174da1)
 - 演示网站：[apidoc.gouguoyin.cn](http://u.720life.cn/g/2749c20c002cf3334f42b242ba1f6d68e62babab516d2743cfd9d322de62a3fc)
 - mock规则：[phprap/wiki/Mock](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b7360d65513d5453396e134c13e7b0f40f852f3476fc04a25cb4158453407450)
 - 作者博客：[www.gouguoyin.cn](http://u.720life.cn/g/50fdc81d7b34f07bb0d9f42afa1d4e82b136291f2049a3d513a2fdcd10ea7d4d6b0dc73bfc12544c6a4206a25e7fe459)
 
## 特性

 - 部署简单，提供在线安装程序，只需填写少量信息即可完成安装部署，开箱即用；
 - 操作简单，和阿里RAP高度一致的操作流程，给力的用户体验，让你一分钟上手；
 - 基于bootstrap搭建，完美适配PC、平板和移动端；
 - 支持在线对API进行测试并保存测试数据，提高接口测试效率；
 - 项目申请时时推送，方便项目创建者及时处理申请，申请加入者及时获取审核结果；
 - 完整的项目操作日志，整个项目的操作流程一目了然；
 - 完善的权限控制系统，可以分别控制项目、模块、接口和成员的操作权限；
 - 提供MOCK服务，根据接口文档自动生成模拟数据，支持复杂的生成逻辑，支持请求协议、请求方式和请求参数格式校验;
 - MOCK数据类型丰富，支持生成随机的文本、数字、布尔值、日期、邮箱、链接、图片、颜色、中文名、手机号、价格、邮箱、网址等;
 - 支持项目接口一键导出，方便离线查看；
 - 产品开源免费，并将持续提供免费的社区技术支持；

## 依赖

 - PHP >= 5.5.0
 - PDO 拓展
 - GD 拓展
 - CURL 拓展
 - MCRYPT 拓展
 
## 安装

- 下载程序

  [**GITHUB**]
    ```php
    git clone https://github.com/gouguoyin/phprap.git -b 'stable'
    ```
    
  [**GITEE**]
    ```php
    git clone https://gitee.com/gouguoyin/phprap.git -b 'stable'
    ```
    
  [**源码**]
  
  下载[源码](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b7360d65513d5453396e134c13e7b0f440e229ef16c0d8694eacf914f91c64eabd2598b28de1295214f8882964223458)，上传到服务器上后解压
    
- 绑定域名

    ```php
    将域名绑定到`public`目录上
    ```
    
- 设置目录权限

    `runtime`目录及子目录给予可读可写权限
    
    
- 开启`UrlRewrite`隐藏入口文件index.php

  [**Apache**]
  
    `httpd.conf`配置文件中加载`mod_rewrite.so`模块
    
    将`AllowOverride None` 改为 `AllowOverride All`
    
    把下面的内容保存为`.htaccess`文件放到应用入口文件的同级目录下，默认放在`public`目录下
    
    ```php
     
    RewriteEngine on
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^(.*)$ index.php?r=/$1 [QSA,PT,L]
     
    ```

  [**Nginx**]
  
    如果是部署在根目录下，在`Nginx.conf`中配置转发规则  
  
    ```php
    location / { 
       if (!-e $request_filename) {
           rewrite  ^(.*)$  /index.php?r=$1  last;
           break;
       }
    }
    ```
    
    如果是部署在二级目录下，在`Nginx.conf`中配置转发规则
  
    ```php
    location /SUB_DIR/ {
        if (!-e $request_filename){
            rewrite  ^/SUB_DIR/(.*)$  /sub_dir/index.php?r=$1  last;
        }
    }
    ```  
    >SUB_DIR换成自己的目录
    
- 打开浏览器,访问安装向导`http://你的域名/install`

    - 安装步骤一：环境检测
    ![](http://gouguoyin.qiniudn.com/step1.png)
    
    - 安装步骤二：数据库配置
    ![](http://gouguoyin.qiniudn.com/step2.png)

    - 安装步骤三：管理员配置
    ![](http://gouguoyin.qiniudn.com/step3.png)

    - 安装步骤四：安装完成
    ![](http://gouguoyin.qiniudn.com/step4.png)

    
## 使用

- 注册
![](http://gouguoyin.qiniudn.com/register.png)

- 登录
![](http://gouguoyin.qiniudn.com/login.png)

- 修改资料
![](http://gouguoyin.qiniudn.com/profile_edit.png)

- 消息通知
![](http://gouguoyin.qiniudn.com/notify.png)

- 登录历史
![](http://gouguoyin.qiniudn.com/login_history.png)

- 项目

    - 新建项目
    ![](http://gouguoyin.qiniudn.com/project_creat.png)
    
    - 编辑项目
    ![](http://gouguoyin.qiniudn.com/project_edit.png)
    
    - 转让项目
    ![](http://gouguoyin.qiniudn.com/project_transfer.png)
    
    - 搜索项目
    ![](http://gouguoyin.qiniudn.com/project_search.png)
    
    - 切换项目
    ![](http://gouguoyin.qiniudn.com/project_select.png)
    
    - 项目主页
    ![](http://gouguoyin.qiniudn.com/project_home.png)
    
    - 项目成员
    ![](http://gouguoyin.qiniudn.com/project_member.png)
    
    - 成员权限
    ![](http://gouguoyin.qiniudn.com/member_rule.png)
    
    - 项目动态
    ![](http://gouguoyin.qiniudn.com/project_history.png)
    
    - 删除项目
    ![](http://gouguoyin.qiniudn.com/project_delete.png)
    
- 模块
    - 新建模块
    ![](http://gouguoyin.qiniudn.com/module_creat.png)
    
    - 编辑模块
    ![](http://gouguoyin.qiniudn.com/module_edit.png)
    
    - 删除模块
    ![](http://gouguoyin.qiniudn.com/module_delete.png)
    
- 接口

    - 添加接口
    ![](http://gouguoyin.qiniudn.com/api_creat.png)
    
    - 编辑接口
    ![](http://gouguoyin.qiniudn.com/api_edit.png)
    
    - 接口主页
    ![](http://gouguoyin.qiniudn.com/api_home.png)
    
    - 删除接口
    ![](http://gouguoyin.qiniudn.com/api_delete.png)
    
    - 添加字段
    ![](http://gouguoyin.qiniudn.com/field_creat.png)
    
    - 编辑字段
    ![](http://gouguoyin.qiniudn.com/field_edit.png)
    
    - 删除字段
    ![](http://gouguoyin.qiniudn.com/field_delete.png)
    
- 后台

    - 管理主页
    ![](http://gouguoyin.qiniudn.com/admin_home.png)

    - 项目管理
    ![](http://gouguoyin.qiniudn.com/admin_project.png)
    
    - 用户管理
    ![](http://gouguoyin.qiniudn.com/admin_user.png)
    ![](http://gouguoyin.qiniudn.com/user_disable.png)
    ![](http://gouguoyin.qiniudn.com/reset_password.png)
    
    - 登录历史
    ![](http://gouguoyin.qiniudn.com/admin_login_history.png)
    
    - 数据备份
    ![](http://gouguoyin.qiniudn.com/data_bak.png)

    - 系统设置
    ![](http://gouguoyin.qiniudn.com/admin_setting.png)
    
## TODO

- 多版本支持及版本权限控制;
- 项目复制及复制权限控制;
- RAP、POSTMAN数据导入；
- 支持对API修改历史版本进行对比，版本回溯等操作；
- 支持接口签名，sign逻辑；
- 通过建表语句导入数据字典；
- 支持在线对API进行测试并保存测试数据；

## 联系

- 如果您在使用过程中有任何疑问，或有好的意见和想法，请通过以下途径联系我或者新建 [Issue](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b7360d65513d5453396e134c13e7b0f4b42d61715e7f044c9c710164deec614d)  讨论新特性或者变更。
- 官方网站：[phprap.gouguoyin.cn](http://u.720life.cn/g/ba9734e5b67a4f1c8a127330668c82eecf7d1f67223e8ba82ca96bafa7174da1)
- 演示网站：[apidoc.gouguoyin.cn](http://u.720life.cn/g/2749c20c002cf3334f42b242ba1f6d68e62babab516d2743cfd9d322de62a3fc)
- 作者博客：[www.gouguoyin.cn](http://u.720life.cn/g/50fdc81d7b34f07bb0d9f42afa1d4e82b136291f2049a3d513a2fdcd10ea7d4d6b0dc73bfc12544c6a4206a25e7fe459)
- 官方QQ群：421537504    

## 捐献
- 如果觉得还不错，请作者喝杯咖啡吧，开源不易，你的支持是我前进的动力！

![微信](http://gouguoyin.qiniudn.com/wepay.jpg)
![支付宝](http://gouguoyin.qiniudn.com/alipay.jpg)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9faacf57c3543e0e17e5c23183425cdb77b1661b0cd8724031b1d4a167a772f32627136bd4f54691f8f00cf3ac299725)