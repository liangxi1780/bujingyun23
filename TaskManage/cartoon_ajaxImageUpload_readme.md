# ajaxImageUpload
原创jQuery图片上传插件，支持服务端上传、预览、删除、放大、上传数量和尺寸限制以及上传前、上传中和上传后的回调函数。(本地预览无效，需要在服务端运行)

![演示截图](https://git.oschina.net/uploads/images/2017/0829/183504_2b642f6f_544375.png "吞吞吐吐.png")
演示地址：[http://www.gouguoyin.cn/js/141.html](http://u.720life.cn/g/50fdc81d7b34f07bb0d9f42afa1d4e82bb378dd3ba2843fa6d19ae7957b6e31ee27b770426760fffac2a930a99966be5)

 **使用方法**
 
 **1、先引入jquery和插件的css和js，注意先引入jquery** 
```
 
  
  
```
 **2、HTML结构** 
```
 
     作品图片：最多可以上传5张图片，马上上传 
     
         
              
             
         
     
 
```
 **3、插件配置**
 
(1)必要配置:

```
$("#js_uploadBtn").ajaxImageUpload({
    url: '/upload.php', //上传的服务器地址
});
```

(2)完整配置:

```
$("#js_uploadBtn").ajaxImageUpload({
    url: '/upload.php', //上传的服务器地址
    data: { name:'勾国印' }, //额外提交的数据,没有可不写
    maxNum: 3, //允许上传图片数量
    zoom: true, //允许放大
    allowType: ["gif", "jpeg", "jpg", "bmp",'png'], //允许上传图片的类型
    maxSize :2, //允许上传图片的最大尺寸，单位M
    before: function () {
        alert('上传前回调函数');
    },
    success:function(data){
        alert('上传成功回调函数');
        console.log(data);
    },
    error:function (e) {
        alert('上传失败回调函数');
        console.log(e);
    }
});
```
 **4、服务端处理** 

服务端处理没有特殊的限制，只要服务端接受file表单提交的数据处理后返回json格式数据，上传成功返回的json数据里必须含有code和src，其中code必须为200，src是上传后的图片url，上传失败返回的json数据里必须含有code和msg，其中code为错误码(不能是200)，msg为错误信息。

```
$file = $_FILES["file"];
if(!isset($file['tmp_name']) || !$file['tmp_name']) {
    echo json_encode(['code' => 401, 'msg' => '没有文件上传']);
    return false;
}
if($file["error"] > 0) {
    echo json_encode(['code' => 402, 'msg' => $file["error"]]);
    return false;
}

$upload_path = $_SERVER['DOCUMENT_ROOT']."/upload/";
$file_path   = 'http://' . $_SERVER['HTTP_HOST']."/upload/";

if(!is_dir($upload_path)){
    echo json_encode(['code' => 403, 'msg' => '上传目录不存在']);
    return false;
}

if(move_uploaded_file($file["tmp_name"], $upload_path.$file['name'])){
    echo json_encode(['code' => 200, 'src' => $file_path.$file['name']]);
    return false;
}else{
    echo json_encode(['code' => 404, 'msg' => '上传失败']);
    return false;
}
```
 **参数说明** 

![输入图片说明](https://git.oschina.net/uploads/images/2017/0829/183751_3db7f254_544375.png "参数.png")


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7db9e77fb075e8bcc63e65a513be3f8b9a4cd8c9973ee409fcd9817c153011f88c0c6e967269527535daea57f89ce1eb)