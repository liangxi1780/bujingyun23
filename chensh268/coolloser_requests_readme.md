

 

 
       
    
     
      
      Python 3.7.4 (default, Sep  7 2019, 18:27:02) 
      >>>  import requests  
      >>> r = requests.get('https://api.github.com/repos/psf/requests') 
      >>> r.json()["description"] 
      'A simple, yet elegant HTTP library.' 
     

     
This software has been designed for you, with much joy,
by  Kenneth Reitz  & is protected by The  Python Software Foundation .
    
 

 

 &nbsp;  &nbsp; 

  Requests  is an elegant and simple HTTP library for Python, built with ♥. 

 &nbsp; 

```pycon
>>> import requests
>>> r = requests.get('https://api.github.com/user', auth=('user', 'pass'))
>>> r.status_code
200
>>> r.headers['content-type']
'application/json; charset=utf8'
>>> r.encoding
'utf-8'
>>> r.text
'{"type":"User"...'
>>> r.json()
{'disk_usage': 368627, 'private_gists': 484, ...}
```



---------------------------------------------------------------------

 &nbsp; 

Requests allows you to send HTTP/1.1 requests extremely easily. There’s no need to manually add query strings to your URLs, or to form-encode your `PUT` & `POST` data — but nowadays, just use the `json` method!


Requests is **the most downloaded Python package today**, pulling in around `14M downloads / week`— according to GitHub, Requests is currently [depended upon](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f55b845f4f7587097d942f85786af11fd212a855b79e3cd7087bc39bd550350647f31fc454de6dc3688753d8a89e5b0947632ef482b713e54d834b2b7f8fecd0235d74d10e39f15f30b13f6729269d60) by `367_296` repositories. You may certainly put your trust in this code.


 &nbsp; 
    
   
    

 &nbsp; 

 Supported Features & Best–Practices 

Requests is ready for the demands of building robust and reliable HTTP–speak applications, for the needs of today.

 
         + International Domains and URLs       + Keep-Alive & Connection Pooling
         + Sessions with Cookie Persistence     + Browser-style SSL Verification
         + Basic & Digest Authentication        + Familiar `dict`–like Cookies
         + Automatic Decompression of Content   + Automatic Content Decoding
         + Automatic Connection Pooling         + Unicode Response Bodies * 
         + Multi-part File Uploads              + SOCKS Proxy Support
         + Connection Timeouts                  + Streaming Downloads
         + Automatic honoring of `.netrc`       + Chunked HTTP Requests

                            &, of course, rock–solid stability!
 
 

 
        ✨ 🍰 ✨&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 

 &nbsp; 

Requests Module Installation
----------------------------

The recommended way to intall the `requests` module is to simply use [`pipenv`](http://u.720life.cn/g/462b69aa3ecf25c083ed614fc348dfe733cf70317996a81a98af3f259b1afff7) (or `pip`, of
course):

```console
$ pipenv install requests
Adding requests to Pipfile's [packages]…
✔ Installation Succeeded
…
```

Requests officially supports Python 2.7 & 3.5+.

-------------------------------------

## P.S. — Documentation is available at [`requests.readthedocs.io`](http://u.720life.cn/g/9f51956d1f1b8d156e2b8ab9111df8c68aa671808c29ff38726c8df0ed97dbfc8b8e95b692eae938c19a1268ee227a99).

 
           
 


------------------


 &nbsp; 

 
           
 

 &nbsp; 

 
           
 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4f140cbc445370a9a1dc5c08f867cdd65a485068249609df079193e92a36ff242fc9c2ef06bf8643e508d5f33300ef23)