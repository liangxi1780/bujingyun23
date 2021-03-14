 
      G.js  
     QQ群:248861958 
     
    	 
    	G.js是一个开源小巧的javascript框架。支持浏览器 ie6+ 
        一共包含31个方法，其中有13个是对dom原生对象的扩展 （被G.js处理过的对象才有这些扩展方法,没有污染原生对象结构） ，18个常用方法。 
         
         
        18个常用方法包含了4个插件： 
        1、自动验证表单 
        2、各种弹出框  (alert | success | error | confirm | prompt | box)   
        3、无刷新上传图片 
        4、移动设备的上下 左右 长按 手势的识别 （需要支持touch事件） 
         
         
        G.js返回的对象均为原生js对象。
         
     
     下载 
     
    	  g.js  ----------- 16KB 
          g.min.js  ----------- 11KB 
          g.css  ----------- 3KB  （各种弹出框的样式）  
     
     对dom扩展的13个方法 （均支持数组操作）  
     
    	 
             
                 方法  说明 
             
             
                 $  dom.$('css选择器',false|true = false) 选择器,作用域是当前元素 第二个参数默认是false 表示选择第一个元素,true 表示选择所有的 
             
             
                 child  dom.child(n='') 当前元素的子元素 n为空表示所有子元素 
             
             
                 css  dom.css({}) 给当前元素添加css样式 
             
             
                 rcss  dom.rcss(被替换的class名称,替换的class名称) 操作class类名 第一个参数为空表示添加 第二个参数为空表示删除 
             
             
                 del   dom.del() 删除当前元素 
             
             
                 each  dom.each(回调函数) 遍历当前对象 
             
             
                 hide  dom.hide(回调函数,淡出时间css3) 隐藏当前元素 
             
             
                 show  dom.show(回调函数,淡入时间,最终透明度) 显示当前元素 
             
             
                 next   dom.next(n=1) 当前元素的下n个元素 默认为1 
             
             
                 prev  dom.prev(n=1) 当前元素的上n个元素 默认为1 
             
             
                 offset  dom.offset() 获取当前元素的位置 返回{top:'',left:'',bottom:'',right:''} 
             
             
                 parent  dom.parent(n=1) 返回当前元素的父N级元素 
             
             
                 use  dom.use(fn) 当前所有元素执行fn函数 
             
        
     
     DEMO 
     
    	 获取1个class为.dt的元素 改变背景颜色为(#85B3DC) 
    	 G('.dt').css({'backgroundColor':'#85B3DC'}); 测试  
         获取1个class为.dt的元素内的所有信息 
    	 alert(G('.dt').innerHTML); 测试  
         获取所有class为.dt的元素 改变背景颜色为(#85B3DC) 
    	 G('.dt',true).css({'backgroundColor':'#85B3DC'}); 测试  
    	 获取所有class为.dt的元素 下面的第一个p元素 改变背景颜色为(#85B3DC) 
    	 G('.dt',true).$('p').css({'backgroundColor':'#85B3DC'}); 测试  
         获取所有class为.dt的元素 下面的所有p元素 返回的是一个二维数组 
    	 G('.dt',true).$('p',true); 
     
     18个常用方法 
     
    	 
             
                 方法  说明 
             
             
                 $$  G.$$('div')创建dom对象 
             
             
                 F  G.F() 初始化自动验证表单 在表单加载完调用 
             
             
                 TE  G.TE(对象,lr|tb|all|lclick,滑动结束函数,滑动过程中的函数?,滑动开始函数?) 手势操作 滑动结束函数发回的是1 或则 -1 或着 滑动的距离 
             
             
                 aj  ajax G.aj(url地址,POST数据,回调函数,格式?) 有防止多次提及的功能 相同的数据和地址 前一次提交没有返回 会自动屏蔽后面的提交 
             
             
                 notice  注意提示 G.alert('提示内容',是否有遮蔽层=false,回调函数=false,时间=3000) 
             
             
                 alert  警告提示 G.alert('提示内容',是否有遮蔽层=false,回调函数=false,时间=3000) 
             
             
                 success  成功提示 G.alert('提示内容',是否有遮蔽层=false,回调函数=false,时间=3000) 
             
             
                 error  错误提示 G.alert('提示内容',是否有遮蔽层=false,回调函数=false,时间=3000) 
             
             
                 box  弹出窗口 G.box('标题'|false,内容,是否有遮蔽层=false,关闭时的回调函数 = null,点击弹层是自动关闭 = false) 
             
             
                 confirm  确认提示 G.confirm('提示内容',function(r){},是否有遮蔽层) 
             
             
                 prompt  输入提示 G.prompt('提示内容',function(r){},是否有遮蔽层) 
             
             
                 move  G.move(事件作用元素的对象,需要移动元素对象) 
             
             
                 fix  G.fix(css3属性,css3值);返回一个兼容个浏览器的css对象 
             
             
                 fnr  G.fnr(from对象);返回from的所有元素的值 
             
             
                 ldimg  G.ldimg(图片url地址,回调函数);预加载图片 
             
            
             
                 on  G.on(元素,事件,函数方法);绑定事件在元素上 
             
             
                 rand  G.rand(最小数,最大数,是否是浮点数=false);产生随机数 
             
             
                 urlencode  G.urlencode(字符串);转换成url编码 
             
        
     
     DEMO 
     
    	 G.alert | G.error | G.success | G.notice 方法 
    	 
        	&lt;script type="text/javascript"&gt;
/*
 G.alert(s,c,f,t),G.error(s,c,f,t),G.success(s,c,f,t),G.notice(s,c,f,t)
 @s:提示信息; 
 @t:显示时间;默认 2000 毫秒
 @f:回调函数
 @c:是否有遮蔽层 默认true  
*/

G.alert('用户名不能空！');

//有遮蔽层
G.alert('用户名不能空！',true);

//无遮蔽层 提示完跳转到 http://www.yxsss.com
G.alert('用户名不能空！',false,function(){window.location='http://www.yxsss.com'});

&lt;/script&gt;
 测试 
         
     
     G.F() 表单自动验证 
     
   		  
             
                 属性  说明 
             
             
                 req  req="true" 表示必填项，不能为空 
             
             
                 exp  填写正则表达式，当前元素内的内容符合发回true，不符合给出警告 
             
             
                 ts  当内容不符时的提示信息 如果没有 会依次寻找placeholder,上一级上一个元素的信息 
             
             
                 fname  无刷新上传文件的的name 
             
             
                 funbak  无刷新上传文件成功后后台返回的信息 的回调函数 
             
             
                 furl  无刷新上传文件地址 当为空时 默认为当前form的action地址 
             
             
                 funstr  上传开始时执行的函数 默认为空 
             
         
      
      DEMO 
     
    	 req 属性 
    	 &lt;!--
	req="true" 表示用户名为必填项，当用户名为空是提示为：
	提示语默认是 元素的父级的上一个元素的内容。下面的提示为 用户名不能为空；
	自定义提示提示信息看 属性ts
--&gt;
&lt;form action="" method="post"&gt;
&lt;table&gt;
	&lt;tr&gt;&lt;td&gt;用户名：&lt;/td&gt;&lt;td&gt;&lt;input type="text" req="true"&gt;&lt;/td&gt;&lt;/tr&gt;
	&lt;tr&gt;&lt;td colspan="2"&gt;&lt;input type="submit" value="提交"&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;/table&gt;
&lt;/form&gt; 
    	  exp | ts 属性 
    	 &lt;!--
exp="这里填写正则表达式" 表示当内容不为空时，用正则表达式验证当前元素里面的内容
如：必填 邮箱格式 自定义提示语
--&gt;
&lt;form action="javascript:;" method="post"&gt;
&lt;table&gt;
	&lt;tr&gt;&lt;td&gt;email：&lt;/td&gt;&lt;td&gt;&lt;input type="text" ts="邮箱格式不正确" req="true" exp="^[\w\-_\.]+@[\w\-]+(\.[a-zA-Z]{2,6}){1,2}$"&gt;&lt;/td&gt;&lt;/tr&gt;
	&lt;tr&gt;&lt;td colspan="2"&gt;&lt;input type="submit" value="提交"&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;/table&gt; 
		  fname | funbak | furl | funstr  属性 
    	 &lt;!--
fname：后台接收时用的名字, 必填
funstr：开始上传执行的函数, 默认无
funbak：上传成功后的回调函数， 必填
furl：上传地址； 默认当前form的提交页面
注意：上传地址和当前地址必须为同意域名否则回调函数获取不到 上传成功发回的地址。

a.php:

$path='a.jpg';
move_uploaded_file($_FILES['uimg']['tmp_name'],$path);
exit(json_encode(array('ztai'=>true,'url'=>$path)));


--&gt;

&lt;form action=""  method="get"&gt;
&lt;input type="button" fname="uimg" funstr="function(){document.title='图片正在上传……';return false;}" funbak="ddd" furl="a.php" value="本地上传"&gt;
&lt;/form&gt;
&lt;script type="text/javascript"&gt;
function ddd(da){
	
	if(da.ztai){
		document.title='上传完成';
		G.success('上传成功保存地址为'+da.url);
	}
}
&lt;/script&gt; 

     
     
    	  其他插件  
     
 




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed1608cac52acb1d410caa85b19aa0c5c52cab2afa33863987fb664f992864afd83e923a04059a475cb9fbe9f3898433e)