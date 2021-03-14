# dubboDoc

[中文](./README_ch.md)

Dubbo api documents, test tools, generate documents according to annotations, and provide test functions

Only some annotations are needed to generate documents similar to swagger, without turning a non web's dubbo project into a web project.

Welcome everyone to make complaints about it~

At present, the function of the first version is relatively rough (the interface is also rough), and the user experience is not very good. It will be gradually optimized later, and all kinds of PR are welcome~



```
When testing Dubbo providers, I always thought that if Dubbo had a document + testing 
tool similar to swagger
I've also found that several of them are based on springfox, and will add some restful 
interfaces to Dubbo project,if your Dubbo service itself is started through a web container 
or mixed with web projects, that's fine.
But my Dubbo projects are all non web projects. For those with obsessive-compulsive disorder, 
it is a little unacceptable to turn the project into a web project for the purpose of documentation,
so I have the idea of doing it myself...
```
## Version planning
### First edition
* Parsing annotations and generating UI
* Unfriendly user interface (without handling some exceptions)
### Second edition
* Replace the JSON text area with a proper JSON editor, and verify the JSON format
* Add tabs
* It can save the test and facilitate the next direct loading test
* Some exceptions are handled as friendly text prompts
* Add remark.md and show it in the front end
* Add changelog.md and show it in the front end
### Follow up edition
* Demand  based on own use and issue planning
* Planning according to Dubbo upgrading
## Registry center suppor
* In theory, all registries supported by Dubbo support

## How to use?
1. Dubbo doc annotation added to method parameters of Dubbo project
   * Dubbo provider project introduces Dubbo doc core
   * If Dubbo's interface and parameters are a separate jar package project, introduce Dubbo doc annotations
```
 
    top.klw8.alita.dubbodoc 
    dubbo-doc-annotations 
    1.0.1 
 

 
    top.klw8.alita.dubbodoc 
    dubbo-doc-core 
    1.0.1 
 
```
2.Download dubbo-doc-ui-server [Download](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a0d648aeebfa378987dda7d1f1dd43671f7736fc6cbaba5c8b70775c65512f45)

3. Start dubbo-doc-ui-server

4. Visit: http:// localhost:8888
   * Port can be modified in application.yml
   * swagger-ui http:// localhost:8888/swagger-ui.html
### Annotation use
* @DubboApiModule class annotation: dubbo API module information, used to mark the purpose of an interface class module
    * value: module name
    * apiInterface: Provider implemented interface
    * version: module version
* @DubboApi method annotation: dubbo API information, used to mark the purpose of an dubbo API
    * value: API name
    * description: API description(HTML tags available)
    * version: API version
    * responseClassDescription: response class description
* @RequestParam class property/method Parameter annotation: mark request parameters
    * value: parameter name
    * required: true/false required parameter
    * description: parameter description
    * example: parameter example
    * defaultValue: parameter default value
    * allowableValues: Allowed values. After setting this property, a drop-down list will be generated for the parameter
        * Note: a drop-down selection box will be generated after using this property
        * Parameters of boolean type do not need to be set with this property. A drop-down list of true / false will be generated by default
        * Parameters of enumeration type will automatically generate a drop-down list. If you do not want to open all enumeration values, you can set this property separately.
* @ResponseProperty Class attribute annotation: mark response parameters
    * value: parameter name
    * example: example
### dubbo-doc-ui
* Get API list direct connection: 
> Because Dubbo services with different functions may be registered in the same registration center, 
> but the name of the interface used by Dubbo doc is the same, so the interface of Dubbo doc uses direct 
connection to obtain the list of different interfaces of different functions.

* The test can be connected directly or through the registration center
### swagger-ui TODO

### Use note
* The response bean (the return type of the interface) supports custom generics, but only one generic placeholder.
* About the use of Map: the key of map can only use the basic data type. If the key of map is not the basic data type, the generated key is not in the standard JSON format, and an exception will occur
* The API's synchronous / asynchronous is from org.apache.dubbo.config.annotation.Service.async

## Project structure
* dubbo-doc-annotations: Document generation annotation project
* dubbo-doc-core: Responsible for annotation analysis and document information acquisition interface (Dubbo API)
* dubbo-doc-ui-server: Web service, responsible for displaying doc and providing testing function
* dubbo-doc-console: The front-end project will be packaged into Dubbo doc UI server project when it is published
* dubbo-doc-examples: Use example
* readmeImgs: Pictures used by README.md

## Major dependent version
* spring-boot: 2.1.12.RELEASE
* dubbo: apache dubbo 2.7.5
* icework in front(iceworks 4.0)

## What did Dubbo Doc do ?
### Annotations
* Define annotations to describe interfaces and parameters
### In Dubbo projects that need to generate documentation and tests
* Parsing annotations and caching
* Add Dubbo API used by Dubbo doc to obtain interface information
###  dubbo-doc-ui-server
* Web service
* Restful API used by front-end UI to obtain interface information (interface list, information of specified interface)
* Request the restful API of the Dubbo service (using the method of Dubbo generalization call)
* Save the test and display it next time (implemented in the Second Edition)
### dubbo-doc-console(Package to dubbo-doc-ui-server when publishing)
* Get the interface list and display it according to the specified Dubbo service IP and port (direct connection Dubbo service)
* Get the interface information according to the specified interface and generate the form with DOC (similar to swagger)
* Show API request response


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecb0cba13d2318ae7e96b4455e82ba9a1ee33dbe78be03bc802ee057c7e1c06a363ca1cf1bbb52878099cff3860da0a93)