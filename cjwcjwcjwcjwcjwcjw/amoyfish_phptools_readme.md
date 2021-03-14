### - php常用方法

1. alert function
```
function alert($title){
  echo " alert('$title'); ";
}
```

2. href link
```
function href($url){
  echo " window.location.href='$url' ";
}
```

3. println 
```
function println($string){
    echo $string." ";
}
```

4. print red line
```
function printline(){
    echo " ";
}
```

### - php去掉字符串的最后一个字符

#### 原字符串1,2,3,4,5,6, 
#### 去掉最后一个字符","，最终结果为1,2,3,4,5,6 

### 代码如下： 
```
$str = "1,2,3,4,5,6,"; 
$newstr = substr($str,0,strlen($str)-1); 
echo $newstr; 
//echo 1,2,3,4,5,6
```
###  系统自带的函数即可实现这样的效果，两种方法： 
### 函数1
```
substr($str, 0, -1)
```
### 函数2
```
rtrim($str, ",")
```
### 还有一种方法
```
substr_replace($string ,"",-1);
```
### - php截取中文字符串不乱码
```
 ";

echo "mb_strcut:" . mb_strcut($str, 0, 6, 'utf-8');
//结果：这样
?> 
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e49297edc984259226f3f1f098d9961a9ed8a6fb0e51475d6aa419c2a52b5344e32c874b170f0058f3e9006f8c4f824ad)