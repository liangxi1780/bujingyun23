
**ByteTCC** is an implementation of Distributed Transaction Manager, based on Try-Confirm-Cancel (TCC) mechanism. 

**ByteTCC** is comptible with JTA and could be seamlessly integrated with Spring and other Java containers.


## 1. Quick Start

#### 1.1 Add maven depenency
###### 1.1.1. Spring Cloud
```xml
 
	 org.bytesoft 
	 bytetcc-supports-springcloud 
	 0.5.7 
 
```
###### 1.1.2. dubbo
```xml
 
	 org.bytesoft 
	 bytetcc-supports-dubbo 
	 0.5.7 
 
```

#### 1.2 Compose a business service
```java
@Service("accountService")
@Compensable(
  interfaceClass = IAccountService.class 
, confirmableKey = "accountServiceConfirm"
, cancellableKey = "accountServiceCancel"
)
public class AccountServiceImpl implements IAccountService {

	@Resource(name = "jdbcTemplate")
	private JdbcTemplate jdbcTemplate;

	@Transactional
	public void increaseAmount(String accountId, double amount) throws ServiceException {
	    this.jdbcTemplate.update("update tb_account set frozen = frozen + ? where acct_id = ?", amount, acctId);
	}

}
```


#### 1.3 Compose a confirm service
```java
@Service("accountServiceConfirm")
public class AccountServiceConfirm implements IAccountService {

	@Resource(name = "jdbcTemplate")
	private JdbcTemplate jdbcTemplate;

	@Transactional
	public void increaseAmount(String accountId, double amount) throws ServiceException {
	    this.jdbcTemplate.update("update tb_account set amount = amount + ?, frozen = frozen - ? where acct_id = ?", amount, amount, acctId);
	}

}
```


#### 1.4 Compose a cancel service
```java
@Service("accountServiceCancel")
public class AccountServiceCancel implements IAccountService {

	@Resource(name = "jdbcTemplate")
	private JdbcTemplate jdbcTemplate;

	@Transactional
	public void increaseAmount(String accountId, double amount) throws ServiceException {
	    this.jdbcTemplate.update("update tb_account set frozen = frozen - ? where acct_id = ?", amount, acctId);
	}

}
```


## 2. Documentation & Samples
* [Document](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046610ad6b73857792371813d09a522f4bec03a789956332de02b0fc5dbd04a83cb)
* [Sample](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046610ad6b73857792371813d09a522f4be89eea5e15394ba5e278ab22b8161d720)



## 3. Features
* support declarative transaction management
* support normal transaction, TCC transaction, compensating service transaction
* support distributed transaction scenarios. e.g. multi-datasource, cross-applications and cross-servers transaction
* support long live transaction
* support Dubbo framework
* support Spring Cloud
* provide solutions for service idempotence in framework layer


## 4. Contact Me
If you have any questions or comments regarding this project, please feel free to contact me at:

1. send mail to _[bytefox#126.com](bytefox@126.com)_
~OR~
2. add Tecent QQ group 537445956/606453172/383515467

We will review all the suggestions and implement good ones in future release.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9f6b57e26f78bd9941147af918e1ecc4589839c9582603919e260f3df9c5fb73c5725bcba8835c4982eb0b5e8367a930)