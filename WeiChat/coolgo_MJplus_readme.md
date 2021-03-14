## Jplus-core说明 ##  

### 声明 ###
jplus 是一个java框架，web只是他的一个模块，他并非重复造轮子，初衷是希望把所有好的合适的框架集合到一起，能发挥出对开发者更大的作用。
框架思想主要学习黄勇 的smart，推荐大家去看看；

### 关于Jplus ###
1. 支持零配置，所有配置可由.properties或代码管理。
2. 提供可以媲美Spring的 IOC、AOP、MVC，及各种强大的第三方定制插件。
3. 快速开发，框架~200Kb,所有插件可插拔。

### jplus 简介 ###
![](http://static.oschina.net/uploads/space/2016/0829/093408_qw7n_224195.png)
> **项目启动顺序：**
> 初始化 -->CoreLoader -->BeanHandle -->ActionHandle -->PluginHandle -->AopHandle -->IocHandle -->完成
>
> **关于Bean管理**
> 项目启动后CoreLoader 加载 BeanHandle,同时BeanHandle 初始化ConfigHandle， 获取一系列相应的用户配置信息properties。
> 然后扫描 ${app.scan.pkg} 包中所有带@Component注解的class,完成bean的发现。
> *PS:在项目中运行时获取 bean 对象可以使用：BeanHandle.getBean(Classcls);*

----------


### 1. 快速创建一个jplusMvc项目 ###

1. 首先我们创建一个simple Maven Project
   然后第一步创建一个**HelloAction.java**用于接收用户请求： 

   ```java
   package com.demo.mvc.action;
   import com.jplus.core.mvc.WebUtil;
   import com.jplus.core.mvc.annotation.Controller;
   import com.jplus.core.mvc.annotation.Request;

   @Controller
   public class HelloAction {

		@Request.All("{msg}")
		public void index(String msg) {
			System.err.println("== This is Restful Action ===========");
			WebUtil.writeHTML(msg);
		}
   }
   ```
2. 然后我们看见，包名是com.demo开始的，现在配置注解扫描配置，在project的classpath目录下，添加文件：**app.properties**
   ```java
	app.scan.pkg=com.demo
   ```
3. [附加]其实到第二步，项目就可以启动了，但为了debug方便，添加日志配置,在classpath目录下，添加：**log4j.xml**
   ```xml
      
    
    
      
      
        
        
          
        
      
      
        
      
    
   ```
4. 最后添加Tomcat容器，启动访问：[localhost:8080/hello](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad14af5866d9207d84085c275f6acc186781)试试吧~



### 2. 关于JplusMvc的相关配置 ###

1. 关于MVC注解
   - 注解：**@Controller**
       使用说明：用于定义Action配置。类上加上此注解，该类将被定义为Action处理的接收类。
       使用方式：直接在请求处理类上加上此注解即可。

   - 注解：**@Request**
      使用说明：用于定义请求的UrlMapping,对用户的请求根据路径做路由分发。
      使用方式：见下方代码，默认提供六种配置方式，对应于不同的http请求:
      @Request("xxx")	=> 用于公共请求前缀,作用于类上
      @Request.All("xxx")=> 用于接受所有匹配的请求，作用于方法上
      @Request.Get("xxx")=> 用于接受Http get请求，作用于方法上
      @Request.Post("xxx")=> 用于接受Http post请求，作用于方法上
      @Request.Put("xxx")=> 用于接受Http put请求，作用于方法上
      @Request.Delete("xxx")=> 用于接受Http delete请求，作用于方法上

     ```java
     package com.demo.mvc.action;
     import com.jplus.core.mvc.WebUtil;
     import com.jplus.core.mvc.annotation.Controller;
     import com.jplus.core.mvc.annotation.Request;
     @Controller
     @Request("user/")
     public class UserAction {

       @Request.All("info")
         private void info() {
         WebUtil.writeHTML("This is Page info");
       }

       @Request.Get("{id}")
         private void getUser(int id) {
         WebUtil.writeHTML("This is a get user info by id,id:"+id);
       }

       @Request.Post("add")
         private void addUser() {
         WebUtil.writeHTML("This is add Page");
       }

       @Request.Put("edit")
         private void editUser() {
         WebUtil.writeHTML("This is edit Page");
       }

       @Request.Delete("{id}")
         private void delUser(int id) {
         WebUtil.writeHTML("This is del Page,user id is :" + id);
       }
     }
     ```

   - 注解：**@Param**
     使用说明：用于设置请求入参，通过入参名称，获取restful/get/post形式的参数。
     使用方式：见下方代码：    
     ```java
     /**
     * 发现和上面getUser的方法的区别了么，
     * 上面直接取值，使用的下标取值，取的restful请求中的占位符{xx}中的值，然后按下标依次取，支持类型：int/long/Double/BigDecimal/String
     * 下面通过@Param取值，使用名称key取值，可以取restful/get/post...等各种方式提交的值，支持类型：int/long/Double/BigDecimal/String
     */
     @Request.Get("{id}")
     private void getUser2(@Param("id") int userId) {
     	WebUtil.writeHTML("This is a get user info by id,id:"+userId);
     }
     ```

   - 注解：**@Form**
     使用说明：用于标示POJO实体对象的请求入参，作用于实体类上。
     使用方式：当一个pojo实体对象为入参时（form表单提交），框架会自动将入参填充到对象中去。见下方代码：       
     ```java
     ==>UserForm.java
     @Form
     public class User {
       private int id;
       private String name;
       private String age;
       /** ... omit get/set/toString method ... */
     }
     --------------------------------------------------------------
     ==> UserAction.java
     @Request.Post("add")
     private void addUser(User user) {
       System.err.println("I can get form param:"+ user.toString());
       WebUtil.writeHTML("This is add Page");
     }
     ```

   - 注解：**@Service**
     使用说明：用于标记实现类，供框架扫描，作为IOC注入到其他类中，作用于类上，一般用于Service层。又一个默认参数[名称]，非必填。
     使用方式：@Service用于标记扫描，等待其他类使用@Autowired 注入，
     @Service可以添加参数名 @Service("xxx"),然后注入的地方使用@Autowired("xxx")进行注入，见下方代码：       
     ```java
     ==> UserService.java
     @Service
     public class UserService {

     public Result add(User form) {
       Result res = new Result().OK();
       System.err.println("Add Service :" + form.toString());
       return res;
       }
     }

     --------------------------------------------------------------
     ==> UserAction.java

     @Controller
     @Request("user/")
     public class UserAction {
     private @Autowired UserService userService;

     @Request.Post("add")
     private Result addUser(User form) {
       return userService.add(form);
       }
     }
     ```

2. 关于MVC上下文
   - **DataContext.java**			
     DataContext为整个MVC的上下文容器，生产周期为当前请求。
     里面封装了**Cookie,HttpServletRequest,HttpServletResponse,ServletContext,Session**等相关对象的处理。

   - **WebUtil.java**
     Web 操作工具类,依赖于DataContext，提供了取参，输出，转发请求等实用功能。

   - **视图输出：View.java**
     视图输出，将请求执行完毕，返回到JSP页面进行渲染，然后返回也客户端页面。
     默认视图地址[在properties中配置]：*app.view.path=/WEB-INF/jsp/*

     ```java
     @Controller
     @Request("hello/")
     public class HelloAction {
       @Request.All("page")
       public View page() {
         System.err.println("== This is page Action ===========");
         //跳转到 : /WEB-INF/jsp/hello/page.jsp
         return new View();
       }
     }
     ```

   - **JSON输出：Result.java**
      JSON输出，将请求执行完毕，返回到前端JSON字符串。
      推荐使用Result作为方法返回值。用户也可以**自定义任何对象**输出，默认都为JSON格式。

     ```java
     @Request.Get("JSON")
     public Result getJSON() {
       System.err.println("== This is page Action ===========");
       // 返回JSON : {"code":1,"obj":"请求成功"}
       return new Result().OK().DATA("请求成功");
     }
     ```


### 3. 关于JplusAop的相关配置 ###
> 说明：使用jdk，Cglib动态代理技术实现，采用责任链模式，递归代理。
> 默认AOP提供三种代理：

1. **AspectProxy.java** 切面代理，提供6种切点方法：

   ```java
   //开始
   public void begin() 
   //拦截[根据boolean判断是否继续执行方法]
   public boolean intercept(Class  cls, Method method, Object[] params)  
   //方法执行前
   public void before(Class  cls, Method method, Object[] params) throws Throwable 
   //方法执行后
   public void after(Class  cls, Method method, Object[] params, Object result)  
   //抛出异常
   public void error(Class  cls, Method method, Object[] params, Throwable e) 
   //结束
   public void end()
   ```


-  **使用方式：**
         对自定义切面类继承AspectProxy抽象类，并重写目标方法， 然后对该类添加@Aspect注解。

   -  **注解:@Aspect** *（该注解有三个属性值：）*：
            **pkg**：想要被代理类所在的包名。 
            **cls**：想要被代理的具体类，和pkg二选一。
            **annotation**：想要被代理的类是有指定注解的类

   -  **注解:@AspectOrder** ：
            该注解是@Aspect的补充，对链式AOP做排序，若有@AspectOrder注解，则优先比较（序号的值越小越靠前）

   -  **代码示例：**
		```java
		package com.demo.mvc.aop;
		import java.lang.reflect.Method;
		
		import org.slf4j.Logger;
		import org.slf4j.LoggerFactory;
		import com.jplus.core.aop.AspectProxy;
		import com.jplus.core.aop.annotation.Aspect;
		import com.jplus.core.mvc.DataContext;
		import com.jplus.core.mvc.annotation.Controller;
		
		/**
		* AOP拦截器演示 
		* 测试拦截指定包名下所有的Action
		* @author Yuanqy
		*/
		@Aspect(pkg = "com.demo.mvc.action", annotation = Controller.class)
		public class ActionInterceptor extends AspectProxy {
		  private Logger logger = LoggerFactory.getLogger(getClass());
		
		  ThreadLocal  curTimes = new ThreadLocal ();
		
		  @Override
		  public void before(Class  cls, Method method, Object[] params) throws Throwable {
		    curTimes.set(System.currentTimeMillis());
		    logger.info("===Is new RequestURI：" + DataContext.getRequest().getRequestURI());
		    logger.info("===Action:{}.{}", cls.getName(), method.getName());
		  }
		
		  @Override
		  public void after(Class  cls, Method method, Object[] params, Object result) throws Throwable {
		    logger.info("===Action is complete,time：{}ms \n", (System.currentTimeMillis() - curTimes.get()));
		    curTimes.remove();
		  }
		}
		```

1. **TransactionProxy.java** 事务代理： 
   - **使用方式：**
     在想要被事务代理的类、或类的方法上添加注解：**@Transaction**即可。

   - **注解:@Transaction**：
     类似于Spring的事务，支持事务传播，支持配置事务隔离级别（默认level=4）
     作用于类上，表示当前类中所有方法开启事务。						
     作用于方法上，表示当前方法开启事务。								

   - **代码示例：**

     ```java
     @Service
     public class UserService {

     	@Transaction
     	public Result add(User form) {
     		Result res = new Result().OK();
     		// TODO something...
     		return res;
     	}
     }
     ```


1. **PluginProxy.java** 插件代理： 
   -  **使用方式：**	
		他是对于上诉两种代理的补充，可以用于扩展任意规则、任意场景代理实现。
		该类仅有一个获取代理链方法：
      ```java
		/**
		* 具体代理被执行时，会执行实现了Proxy接口的doProxy()方法. 
		* 使用方式：请参考：com.jplus.j2cache.proxy.J2CachePluginProxy
		* 原理：
		* 项目启动时，先扫描缓存bean，当AopHandle运行时，执行插件代理的getTargetClassList方法。
		* 该方法由开发人员自己定义筛选规则，将满足条件的对象bean集合返回，做AOP代理；
		* 在项目运行期，代理的对象执行时，通过链式代理，找到当前类，执行doProxy()方法，完成代理操作。
		*/
		public abstract List getTargetClassList()
      ```

### 4. 关于JplusIOC的相关配置 ###

> 框架中，ioc初始化位于项目启动最后阶段。 之前的MVC，AOP，Plugin 已经是创建了所有项目中所需的bean对象， 在最后要做的就是把这些 对象 互相关联起来，建立原本的依赖关系。


- **注解:@Autowired**：
  - **使用方式：**	

    ```java
    //通过接口注入，框架会找到容器中的第一个接口实现类进行注入，实现类必须>=1，否则异常
    private @Autowired IIocDemo demo;// 通过接口注入

    //通过指定接口实现注入，实现类上必须标明当前名称@Service("xxx")才能注入成功
    private @Autowired("xxx") IIocDemo demo;// 通过指定接口实现注入

    //这个没什么好说的，直接注入目标类即可
    //PS.只要是bean容器管理了的对象，都可通过@Autowired注入。
    private @Autowired IocDemoImpl demo;// 通过指定对象注入
    ```


-   **注解:@Value**：
    - **使用方式：**

      ```java
      //方式1：@Value("xxx")
      //方式2：@Value("${xxx}") 两种方式效果一致
      private @Value("app.scan.pkg") String scanPkg;// 注入配置文件
      ```

-   **注解:@Component**：
            @Component注解是其他注解的元注解。jplus的扫描规则是扫描所有继承或使用Component注解的类，然后加入bean管理。
    -  **使用方式：**
       ```java
       /**
       * 属于Bean扫描注解，任何需要加入IOC的组件类，都 可以添加该注解。
       * 该注解提供两个参数[都非必填项]：
       * initMethod：填入当前类的方法名，项目启动后会执行该方法
       * destroyMethod：填入当前类的方法名，项目注销前会执行该方法
       */
       @Component(initMethod = "init", destroyMethod = "destroy")
       public class InitComponent {
         public void init() {
           System.err.println("== 项目启动后会执行该方法 ==");
         }

         public void destroy() {
           System.err.println("== 项目注销前会执行该方法 ==");
         }
       }
       ```

-   **代码示例：**

    ```java
      /**
      * 接口类
      */
      public interface IIocDemo {
      Result addUser(User user);
      Result getUser(int id);
      }
    ```

   	---------


    ```java
      /**
      * 实现类
      */
      //@Service
      @Service("iocDemoImpl")
      public class IocDemoImpl implements IIocDemo {

        private Map  map = new HashMap<>();

        @Override
        public Result addUser(User user) {
          map.put(user.getId(), user);
          return new Result().OK().DATA("新增成功");
        }

        @Override
        public Result getUser(int id) {
          if (map.containsKey(id))
          return new Result().OK().DATA(map.get(id));
          else
          return new Result().FAIL().DATA("数据不存在");
        }
      }
    ```

	 ---------
    ```java
      /**
      * 在Action中注入
      */
      @Controller
      @Request("ioc/")
      public class IocAction {

        private @Autowired IIocDemo ioc1;			// 通过接口注入
        private @Autowired("iocDemoImpl") IIocDemo ioc2;	// 通过指定接口实现注入
        private @Autowired IocDemoImpl ioc3;		// 通过指定对象注入

        private @Value("app.scan.pkg") String scanPkg;

        @Request.Get("test")
        private void iocTest() {
          System.out.println(ioc1.addUser(new User(1, "张三")));
          System.out.println(ioc2.getUser(1));
          System.out.println(ioc3.getUser(1));

          WebUtil.writeTEXT("OK");
        }
      }
    ```

### 5. 关于Jplus Junit的相关配置 ###

> jplus框架默认集成 **Junit4** 单元测试框架。

- **使用方式：**	

  测试类添加两个注解：@RunWith [Junit框架注解]、@ContextConfiguration [Jplus框架注解] 即可。
  RunWith注解大家可以百度下使用方式，现在说明下ContextConfiguration注解。

  - **注解：@ContextConfiguration**
    ContextConfiguration用于配置配置文件路径。通过参数locations配置，说明如下：

    	"file:/app.properties"			//系统根目录 
    	"app.properties"			//项目根目录 
    	"/app.properties"			//项目WEB-INF下 
    	"classpath:app.properties"		//项目ClassPath下
    	
    	//如果有多个配置文件，可以用 ; 分号分割，如下：
    	"file:/db.properties;classpath:app.properties"	//多个配置文件.一个文件目录下;一个classpath目录

  - **代码示例：**

    ```java
    /**
    * JplusJunit4 测试框架IOC功能
    */
    @RunWith(JplusJunit4Runner.class)
    @ContextConfiguration(locations = "classpath:app.properties")
    public class JunitIOC {

      private @Autowired("iocDemoImpl") IIocDemo ioc3;
      private @Autowired IocDemoImpl ioc2;

      private @Value("app.scan.pkg") String scanPkg;

      @Test
      public void test() throws InterruptedException {
        System.out.println("添加用户：" + ioc3.addUser(new User(1001, "Jplus")));
        System.out.println("获取用户：" + ioc2.getUser(1001));
        System.out.println("app.scan.pkg=" + scanPkg);

        Thread.currentThread().join();
      }
    }
    ```

### 6. 关于JplusMVC的后端参数验证 ###

> 对于请求入参，JPlus可以通过拦截器做公共参数校验，对于form表单对象，可以使用工具类进行校验。

- **使用方式：**	
	对于form表单对象（可以理解为添加了@Form注解的pojo类），当该对象作为请求入参时，正常情况参数的校验都是固定的字段，固定的规则。而且开发人员也不想在业务代码里面进行入参判断。这时候就可以使用：**Result res= VerifyUtil.doVerify(form)；**通过返回Result判断校验结果。
	原理:对入参对象的字段进行处理，判断是否有@V注解，对@V注解的字段进行判断处理。

- **注解 @V：**	
 
	注解名|默认表达式|默认返回描述|是否可为空
	:----|:-----|:-----|:-----:
	IsNotNull|\\w+|字段{}不能为空|FALSE
	IsCN|^[\u4e00-\u9fa5]+$|字段{}不是汉字|TRUE
	IsDigits|^[0-9]*$|字段{}不是纯数字|TRUE
	IsFloat|^[0-9]*$|字段{}不是小数|TRUE
	IsEmail|^\\w+([-+.]\\w+)*@\\w+([-.]\\w+)*\\.\\w+([-.]\\w+)*$|邮箱格式不正确|TRUE
	IsIdCardNo|^(\\d{6})()?(\\d{4})(\\d{2})(\\d{2})(\\d{3})(\\w)$|身份证号不正确|TRUE
	IsPhone|^[1][0-9]{10}$|手机号码不正确|TRUE
	IsPwd|^(?![0-9]+$)(?![a-zA-Z]+$)[0-9A-Za-z]{6,16}$|密码格式不正确|TRUE
	IsTel|^(0\\d{2}-\\d{8}(-\\d{1,4})?)\|(0\\d{3}-\\d{7,8}(-\\d{1,4})?)$|电话号码不正确|TRUE
	IsZipCode|^[0-9]{6}$|邮政编码不正确|TRUE
	Custom| |未定义|TRUE

	*PS：@V.Custom()用于给用户自定义校验规则及返回说明。还支持JPEL表达式。*
	
- **代码示例：**	
	```java
	/**
	* Form入参表单
	*/
	@Form 
	public class User {
		@V.IsNotNull
		@V.IsDigits
		private int id;			//表示id必须为数字，不能为空
		private String name;
	
		@V.Custom(regex = "el:{}>=18 && {} 15倍,后续会逐渐优化,支持特性：**
	- 算数运算表达式:
		加(+)、减(-)、乘(*)、除(/)、求余（%）、幂（^）运算 
	- 关系表达式:
		等于（==）、不等于(!=)、大于(>)、大于等于(>=)、小于( -1+2*3";
	System.err.println("中缀表达式：" + calc);
	// == 逆波兰 ========================
	long t = System.currentTimeMillis();
	System.out.println("逆波兰=" + excute(calc) + "\ttime:" + (System.currentTimeMillis() - t));
	// == JS引擎==========================
	t = System.currentTimeMillis();
	System.out.println("JS引擎=" + getSE().eval(calc) + "\ttime:" + (System.currentTimeMillis() - t));
	```

### 8. 附加：关于Jplus多数据源的配置 ###
> 多数据源可以支持**申明式配置**和**编程式配置**两种，具体方法参考jplus-orm说明文档。
- **编程式配置 实例：**
	```java
	/**
	 * JplusJunit4 测试Jplus-core编程式多数据源切换
	 */
	@RunWith(JplusJunit4Runner.class)
	@ContextConfiguration(locations = "classpath:app.properties")
	public class JplusDDS {
	
		@Test
		public void test() {
			JdbcTemplate jt = null;
			try {
				// 1.创建N个数据源，可选用C3p0，Druid...都可以
				DataSource ds1 = new C3p0Plugin("jdbc:mysql://139.196.18.60:3306", "root", "password", "com.mysql.jdbc.Driver").getDataSource();
				DataSource ds2 = new C3p0Plugin("jdbc:mysql://192.168.1.16:3306", "root", "password", "com.mysql.jdbc.Driver").getDataSource();
				// 2.将N个数据源放入DynamicDataSource中，并定义key名称
				Map  map = new HashMap ();
				map.put("readone", ds1);
				map.put("readtwo", ds2);
				DynamicDataSource dds = new DynamicDataSource(map);
				// 3.创建一个JdbcTemplate，使用数据源为DynamicDataSource
				jt = new JdbcTemplate(dds);
	
				// 4.循环测试数据源切换[ps.我事先准备了两个不同版本的mysql]
				for (int i = 0; i < 3; i++) {
					if (i == 2)
						jt.openTransaction(); // 最后一次开启事务
					DataSourceHolder.setDbType("readone");
					System.err.println("[切换1]:" + JSON.toJSONString(jt.query("SHOW VARIABLES LIKE 'version';", new Object[] {})));
					DataSourceHolder.setDbType("readtwo");
					System.err.println("[切换2]:" + JSON.toJSONString(jt.query("SHOW VARIABLES LIKE 'version';", new Object[] {})));
					if (i == 2)
						jt.commit(); // 提交事务
				}
			} catch (Exception e) {
				e.printStackTrace();
				if (jt != null)
					jt.rollback(); // 回滚事务
			}
	
		}
	}
	```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6efc75edc2e942b108d76c735b84da234c671e786b7afc36ad3aeb33120d7a654e60bcd92e43415bc0279dfed9362ae157)