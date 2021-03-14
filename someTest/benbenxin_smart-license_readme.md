# smart-license

smart-license 是一款用于安全加固的开源项目。
主要服务于非开源产品、商业软件、具备试用功能的付费软件等，为软件提供授权制的使用方式。

适用场景：

- 非开源产品、商业软件、收费软件。
- 限制产品的传播性，每个客户拥有专属 License。
- 同一款软件发行包根据 License 的不同提供不同的服务能力。
- 限定软件授权时效

如果喜欢该作品，欢迎底下捐赠一杯3.8折的瑞幸咖啡。
#### License运行流程

![](images/smart-license.png)
   
- License申请流程

    ![](images/license_apply.png)

- 找回License

    ![](images/license_forget.png)


#### 使用方式
##### 生成License
1. 下载[smart-license.tar.gz](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed58d661652530124bc457132b64b3143164805bd4f8b6a85b9c59acdf1b1219bf9c6ba895e2d9220d3f5ea83b446ddca)包，解压。
2. 进入bin目录执行以下命令，例如：`./license.sh 1d HelloWorld`。
![](images/demo.gif)
    - 1d：表示授权效期1天，即一天后该License便过期。支持的效期格式包括:
        - h，1h:1小时; 2h:2小时
        - d，1d:1天; 10d:10天
        - y，1y:1年; 2y:2年
    - HelloWorld：表示待加密的license内容。

    实际场景下可以通过license授权不同的产品功能和有效期，例如：`./license.sh 1y features_1:on;features_2:off;`
    如果待授权的license内容为文件，可以采用同样的命令，例如：`./license.sh 1y config.properties` 

3. 执行成功后，会在当前目录下生成 License:`license.txt`以及 License源文件:`source.txt`。
**注意：license.txt是提供给客户的授权文件；而source.txt是由软件提供方持有，其中包含加密私钥，需要妥善保管**
![](images/demo_result.png)

#### 使用License
1. 引入Maven依赖

    ```xml
    
         org.smartboot.license 
         license-client 
         1.0.0 
     
    ```
2. 载入License。如若License已过期，则会触发异常。

    ```java
    public class LicenseTest {
        public static void main(String[] args) throws Exception {
            File file=new File("license.txt");
            License license = new License();
            LicenseConfig licenseConfig=license.loadLicense(file);
            System.out.println(licenseConfig.getOriginal());
        }
    }
    ```
3. 获取licenseData并以此配置启动软件。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e134d60c7b83a32cad5e3d672b7c523d0ef9a229921630d0fc4e52e60607ee0c0d529cf2847908879ad8cdbb6208284ad)