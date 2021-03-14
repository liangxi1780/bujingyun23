### AliYun Open API SDK for C++ developers
This SDK aimed to provide an Object-Oriented and full stack solution for you to build applications 
on AliYun, supporting aas, ace, ace-ops, alert, batchcompute, aas, ace, ace-ops, alert, batchcompute, bss, 
cdn, cms, crm, drds, dts, ecs, emr, ess, ocs, oms, ons, ossadmin, ots, otsfinance, otsshihua, pts, push, ram, rds, 
rds-region, r-kvstore, slb, sts, ubsms and yundun.

### Requirements
VS2015, G++ 4.6
	
### Dependence
This SDK depends on the following third-party library - **libcurl openssl**. If you want to parse the raw response 
from the AliYun, you can use **libxml2** to parse the XML response or use **jsoncpp** to parse the JSON response. 
I recommend using the latter. The SDK does not include these third-party library, so your have to download 
and install them by yourself.

### Quick Start

	#include  
	#include  
	#include  
	#include "aliyun-cpp-sdk-core/DefaultProfile.h"
	#include "aliyun-cpp-sdk-ecs/EcsService.h"
	int main() {
		AliYunCore::DefaultProfile profile( "cn-hangzhou", "AccessKeyId", "AccessKeySecret" );
		AliYunEcs::EcsClient client( profile );
		AliYunEcs::EcsDescribeRegionsRequest req;
		std::string response = client.getResponse( req );
		std::cout << response << std::endl;
		return EXIT_SUCCESS;
	}

response as below:

	{
		"RequestId": "091465F4-A31F-419E-8FAE-E63AF0073B58",
		"Regions": {
			"Region": [{
				"RegionId": "ap-southeast-1",
				"LocalName": "亚太（新加坡）"
			},
			{
				"RegionId": "cn-shenzhen",
				"LocalName": "深圳"
			},
			{
				"RegionId": "cn-qingdao",
				"LocalName": "青岛"
			},
			{
				"RegionId": "cn-beijing",
				"LocalName": "北京"
			},
			{
				"RegionId": "cn-shanghai",
				"LocalName": "上海"
			},
			{
				"RegionId": "cn-hongkong",
				"LocalName": "香港"
			},
			{
				"RegionId": "cn-hangzhou",
				"LocalName": "杭州"
			},
			{
				"RegionId": "us-west-1",
				"LocalName": "美国硅谷"
			}]
		}
	}
	
	
This SDK has two kinds of namespace - AliYunCore and AliYun{servicename} (e.g. AliYunEcs, AliYunRds). If you
want to use the ecs service, you have to include these files:

	"aliyun-cpp-sdk-core/DefaultProfile.h"
	"aliyun-cpp-sdk-ecs/EcsService.h" 

The "DefaultProfile.h" is implemented in the AliYunCore namespace and the "EcsService.h" is implemented in the AliYunEcs
namespace. There are two kinds of classes in the namespace of AliYunEcs, one is EcsClient and another is api request.
If you want to call the api of "DescribeRegions", you have to instantiate an object of the class "EcsDescribeRegionsRequest".
The last step is to trigger the function of "getResponse" with the request object. The default reponse is JSON, 
but if you prefer XML, you can set the property of request just like this:

	AliYunEcs::EcsDescribeRegionsRequest req;
	req.Format = "XML";
	std::string response = client.getResponse( req );
	
In many apis, you have to supply some important parameters, you can do as follows:

	AliYunEcs::EcsStartInstanceRequest req;
	req.addParameter("InstanceId", "instance-1", "Query");
	req.Format = "XML";
	std::string response = client.getResponse( req );

"InstanceId" is the name of the parameter; "instance-1" is the value, and "Query" is the position, whoes  
default value is "Query", but also can be "Query", "Body", "Path", "Domain" or "Header" according to the 
official API document.

**Note: you don't have to supply the "Action" parameter, because the request knows its Action and will send it 
to AliYun server automatically.**

### License
licensed under the [Apache License 2.0](http://u.720life.cn/g/9504ecfd7de2b26345fb4a78087ff8e39017fae1e889f3875d0fa1b09af9991c)





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1192ba8bafa779e810aa0eb811f3a22e431e794d0f818f5c73e8223785c8ec667e514566ed6171eb50b5a5901cbeb99ef2ffc5366a1759451933081f425101b4)