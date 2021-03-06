
爬虫IP代理池
=======
[![Build Status](https://travis-ci.org/jhao104/proxy_pool.svg?branch=master)](https://travis-ci.org/jhao104/proxy_pool)
[![](https://img.shields.io/badge/Powered%20by-@j_hao104-green.svg)](http://www.spiderpy.cn/blog/)
[![Requirements Status](https://requires.io/github/jhao104/proxy_pool/requirements.svg?branch=master)](https://requires.io/github/jhao104/proxy_pool/requirements/?branch=master)
[![Packagist](https://img.shields.io/packagist/l/doctrine/orm.svg)](https://github.com/jhao104/proxy_pool/blob/master/LICENSE)
[![GitHub contributors](https://img.shields.io/github/contributors/jhao104/proxy_pool.svg)](https://github.com/jhao104/proxy_pool/graphs/contributors)
[![](https://img.shields.io/badge/language-Python-green.svg)](https://github.com/jhao104/proxy_pool)

    ______                        ______             _
    | ___ \_                      | ___ \           | |
    | |_/ / \__ __   __  _ __   _ | |_/ /___   ___  | |
    |  __/|  _// _ \ \ \/ /| | | ||  __// _ \ / _ \ | |
    | |   | | | (_) | >   >>python main.py

# 如果运行成功你应该看到有4个main.py进程

# 你也可以分别运行他们,
# 依次到Api下启动ProxyApi.py,Schedule下启动ProxyRefreshSchedule.py和ProxyValidSchedule.py即可.
```

### 使用

　　启动过几分钟后就能看到抓取到的代理IP，你可以直接到数据库中查看，推荐一个[SSDB可视化工具](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d4e58666369dd969df34b3c1b4c8b6daac8989769b3f4fbf7b6e2140918792c9)。

　　也可以通过api访问http://127.0.0.1:5010 查看。

* Api

| api | method | Description | arg|
| ----| ---- | ---- | ----|
| / | GET | api介绍 | None |
| /get | GET | 随机获取一个代理 | None|
| /get_all | GET | 获取所有代理 |None|
| /get_status | GET | 查看代理数量 |None|
| /delete | GET | 删除代理  |proxy=host:ip|

* 爬虫使用

　　如果要在爬虫代码中使用的话， 可以将此api封装成函数直接使用，例如：

```python
import requests

def get_proxy():
    return requests.get("http://127.0.0.1:5010/get/").content

def delete_proxy(proxy):
    requests.get("http://127.0.0.1:5010/delete/?proxy={}".format(proxy))

# your spider code

def getHtml():
    # ....
    retry_count = 5
    proxy = get_proxy()
    while retry_count > 0:
        try:
            html = requests.get('https://www.example.com', proxies={"http": "http://{}".format(proxy)})
            # 使用代理访问
            return html
        except Exception:
            retry_count -= 1
    # 出错5次, 删除代理池中代理
    delete_proxy(proxy)
    return None
```

### 扩展代理

　　项目默认包含几个免费的代理获取方法，但是免费的毕竟质量不好，所以如果直接运行可能拿到的代理质量不理想。所以，提供了代理获取的扩展方法。

　　添加一个新的代理获取方法如下:

* 1、首先在[GetFreeProxy](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046101ce246e87f2541c868c283a3952c466c26f9beb6144319815825963ffd1838f18f78ea69ccce04e13e957e10653e4bd08d6e0bd3a2c1a5fd9e6e88e542b6d69798bc2f7a19d7bb3bbb322b65eb28cecea273a3de3bb52f006752fa4019d99c293fd52f9228705db0b0e9b0f243cd9e)类中添加你的获取代理的静态方法，
该方法需要以生成器(yield)形式返回`host:ip`格式的代理，例如:

```python

class GetFreeProxy(object):
    # ....

    # 你自己的方法
    @staticmethod
    def freeProxyCustom():  # 命名不和已有重复即可

        # 通过某网站或者某接口或某数据库获取代理 任意你喜欢的姿势都行
        # 假设你拿到了一个代理列表
        proxies = ["139.129.166.68:3128", "139.129.166.61:3128", ...]
        for proxy in proxies:
            yield proxy
        # 确保每个proxy都是 host:ip正确的格式就行
```

* 2、添加好方法后，修改Config.ini文件中的`[ProxyGetter]`项：

　　在`Config.ini`的`[ProxyGetter]`下添加自定义的方法的名字:

```shell

[ProxyGetter]
;register the proxy getter function
freeProxyFirst  = 0  # 如果要取消某个方法，将其删除或赋为0即可
....
freeProxyCustom  = 1  # 确保名字和你添加方法名字一致

```


　　`ProxyRefreshSchedule`会每隔一段时间抓取一次代理，下次抓取时会自动识别调用你定义的方法。

### 问题反馈

　　任何问题欢迎在[Issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046101ce246e87f2541c868c283a3952c46a988db5d0b36367ac4fd4556fd585b20) 中反馈，如果没有账号可以去 我的[博客](http://u.720life.cn/g/cb6f59fb74694e1730cc424cb8b0ef5977568875363ecc392d0582f9510d4eced232709f8ad35fb70abd34aa2b25a26d)中留言。

　　你的反馈会让此项目变得更加完美。

### 贡献代码

　　本项目仅作为基本的通用的代理池架构，不接收特有功能(当然,不限于特别好的idea)。

　　本项目依然不够完善，如果发现bug或有新的功能添加，请在[Issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046101ce246e87f2541c868c283a3952c46a988db5d0b36367ac4fd4556fd585b20)中提交bug或新功能

　　这里感谢以下contributor的无私奉献：

　　[@kangnwh](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e01e30170be838693f6b174dc791fce3)| [@bobobo80](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468a20a7ddc7928d52d4b107215099406a)| [@halleywj](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464a875e9799fc1d8613aace93c6c1f55a)| [@newlyedward](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046133bf75eb686a32039e432e1186e8270)| [@wang-ye](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d7847f4287c78468c9432841862e3405)| [@gladmo](https://github.com/gladmo)| [@bernieyangmh](https://github.com/bernieyangmh)| [@PythonYXY](https://github.com/PythonYXY)| [@zuijiawoniu](https://github.com/zuijiawoniu)







 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ece81228708e210be82fd58039787421bbc7efc662b6f5c9ce34403051971ca8c5222d160823ca2e67c49c884760bc44a)