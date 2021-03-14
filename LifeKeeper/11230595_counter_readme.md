### 分布式环境下的原子计数器和API每天调用次数限制

    利用Zookeeper来实现分布式环境下的原子计数器和API每天调用次数限制

### 如何设置和获取API调用次数限额

    String apiType = "1";
    
    指定新的限制值:
    CountLimit.setLimit(apiType, 1000000);
    
    获取现有限制值:
    CountLimit.getLimit(apiType);
    
### 如何获取API调用次数

    String apiType = "1";
    // 调用API没有响应的情况
    AtomicCounter.getNoResponseCount(apiType);
    // 调用API有响应, 但是内容错误的情况
    AtomicCounter.getWrongContentCount(apiType);
    // 调用API出现异常的情况, 比如网络中断, 服务中断等等
    AtomicCounter.getExceptionCount(apiType);
    // 成功的情况
    AtomicCounter.getResponseSuccessCount(apiType);
    // 假设限额为一百万, 客户端请求了两百万, 那么这里的beyond的值就是一百万
    AtomicCounter.getBeyondCount(apiType);
    
    以上方法调用的是调用当日的情况, 如果想查看具体某一天的情况, 则指定某一天即可, 如:
    AtomicCounter.getNoResponseCount("20161118", apiType);
    AtomicCounter.getWrongContentCount("20161118", apiType);
    AtomicCounter.getExceptionCount("20161118", apiType);
    AtomicCounter.getResponseSuccessCount("20161118", apiType);
    AtomicCounter.getBeyondCount("20161118", apiType);
    
### 如何使用
    
    String apiType = "1";
    // 检查请求是否超配额
    if (AtomicCounter.getResponseSuccessCount(apiType) < CountLimit.getLimit(apiType)) {
        // 没有超过配额, 继续调用
        callApi(request, apiType);
    } else {
        // 超过配额, 忽略调用请求
        AtomicCounter.beyond(1, apiType);
    }

[https://travis-ci.org/ysc/counter](http://u.720life.cn/g/41730a1a7cf811a1831a38c04993d30b9a9ae5c4a09c95a5e45f6d23010e7d00878a253b8ce303af43fe9612531aaf29)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4278163e032b13dd4d9276a709bda64ab2b70ec05ef3d60f7e86dce15090519d620035685b749fd82abe140fe63bef64)