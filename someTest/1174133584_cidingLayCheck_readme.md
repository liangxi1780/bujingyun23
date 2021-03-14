# cidingLayCheck

#### 介绍
layui 版本check多级复选框弹窗组件

#### 软件架构
依赖layui


#### 安装教程

1. 仍在服务下启动即可

#### 使用说明


![image](https://gitee.com/1174133584/cidingLayCheck/raw/master/img/1.png)
![image](https://gitee.com/1174133584/cidingLayCheck/raw/master/img/2.png)

face[good] 一个基于layui封装的checkbox复选组件。
/**
 * 复选框组件2.1 by Ciding
 * 2019-06-13
 * 参数dom 传入按钮id|class
 * 参数title 弹窗标题
 * 参数confObj 数组例如：[
		{url:'querydaibiaoxinbyidorname2',type:'POST',fieldId:'rdSparefield21',fieldName:'按区县',showFieldName:'rdSparefield4',hideFieldId:'rdId'},
		{url:'querydaibiaoxinbyidorname2',type:'POST',fieldId:'rdSparefield20',fieldName:'按职务',showFieldName:'rdSparefield4',hideFieldId:'rdId'},
		{url:'querydaibiaoxinbyidorname2',type:'POST',fieldId:'rdSparefield2',fieldName:'按界别',showFieldName:'rdSparefield4',hideFieldId:'rdId'},
		{url:'querydaibiaoxinbyidorname2',type:'POST',fieldId:'rdSparefield16',fieldName:'按学历',showFieldName:'rdSparefield4',hideFieldId:'rdId'}
	]
	url：数据源url
	type：请求方式
	fieldId：组件要存取的id
	fieldName：要存取或显示的name
	showFieldName：显示的分类name
	hideFieldId：模板要使用的唯一id
 * 参数checkedIds 传入选中数组的ids逗号分割即可 (与下面顺序可以不用对应)
 * 参数checkedNames 传入选中数组的names逗号分割即可 (与上面顺序可以不用对应)
 * fn callback
 * return 选中数组对象
 * 请慎重修改，需考虑扩展性和维护性进行合理修改。
 * @param exports
 * @returns
 */

DEMO：
layui.config({
  base: '../../../layui_exts/cidingLayCheck/'
}).extend({
  regionSelect: 'cidingLayCheck'
}).use(['cidingLayCheck'], function(){
       //引入模块
  	var cidingLayCheck = layui.cidingLayCheck;
       //自定义分组配置
  	var selectConf=[
		{url:'data.json',type:'GET',fieldId:'rdSparefield21',fieldName:'按区县',showFieldName:'rdSparefield4',hideFieldId:'rdId'},
		{url:'data.json',type:'GET',fieldId:'rdSparefield20',fieldName:'按职务',showFieldName:'rdSparefield4',hideFieldId:'rdId'},
		{url:'data.json',type:'GET',fieldId:'rdSparefield2',fieldName:'按界别',showFieldName:'rdSparefield4',hideFieldId:'rdId'},
		{url:'data.json',type:'GET',fieldId:'rdSparefield16',fieldName:'按学历',showFieldName:'rdSparefield4',hideFieldId:'rdId'}
	];
        //初始化组件
	cidingLayCheck.initCheck('#checkBtn','请选出席人员',selectConf,'','',function(users){
		//这是回调
	});
  
});

看demo的话把文件丢到服务器或者本地localhost访问即可食用！




#### 参与贡献

1. Fork 本仓库
2. 新建 Feat_xxx 分支
3. 提交代码
4. 新建 Pull Request


#### 码云特技

1. 使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2. 码云官方博客 [blog.gitee.com](http://u.720life.cn/g/4d9d51ba66eeb41dfb9759648c593bf554785fd0e6ab49d2f13e98afcb69bbc7)
3. 你可以 [https://gitee.com/explore](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed27d15edf43aa40a6d37a2a10b263e5a) 这个地址来了解码云上的优秀开源项目
4. [GVP](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb5ad9b84ebe402667383e4a11c785b2d) 全称是码云最有价值开源项目，是码云综合评定出的优秀开源项目
5. 码云官方提供的使用手册 [https://gitee.com/help](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ebbaab544314b1a4bd89bdd984a12bd00)
6. 码云封面人物是一档用来展示码云会员风采的栏目 [https://gitee.com/gitee-stars/](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e43c4696b881f436e3c9d0b3d64c264cb)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eff724db33fad41284511f6e3505d89c74242e4c7b992e14830dcf990f9aaa443dc6b63782fd59bdac05f258bd826cd7cfcd515b475991caca4e7f91ee4c53a05)