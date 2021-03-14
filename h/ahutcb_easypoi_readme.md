===========================
EasyPoi Excel和 Word简易工具类
===========================
 easypoi功能如同名字easy,主打的功能就是容易,让一个没见接触过poi的人员
就可以方便的写出Excel导出,Excel模板导出,Excel导入,Word模板导出,通过简单的注解和模板
语言(熟悉的表达式语法),完成以前复杂的写法

	作者博客：http://blog.afterturn.cn/
	作者邮箱： qrb.jueyue@gmail.com
	QQ群:  364192721
	
	开发者:魔幻之翼 xf.key@163.com

[测试项目](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d1b7d5a7135ba2c997924dc27b5ac9a8803fd79c6d018217d56fef7770773fff1  http://git.oschina.net/jueyue/easypoi-test

[开发文档请查看DOC下面的EasyPoi教程](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d1b7d5a7135ba2c997924dc27b5ac9a889c80695979fd36eb4150eedb2bab73fab0f9328b491f5936cc06f665cf56c67b859026cdd0baa51cdd20d3d9d6422538c10668fca0965a5a9232c4802cb9bcd507ca05ef5c45cb67fd8fb9854d3f8b763f10735da706f17b797ff34d5275e58bb265b04972f416a2d4181a369e7ceb3ad4d3cf5d787234e17564b9175ab57c36bae53ecb12ced84f9bf0925411b4ff7d19077f17335725feeb622f6127c1be93e2bcf23e9f36129442a6bfe59456bc59e71b07524d4780e82840381fbe25f6379dde1a35bba6b1b9466f6cb5f7f07383) 
!!!2.1.6 版本开始和之前的版本校验不兼用,使用JSR303的校验,删除了之前的注解,请注意
!!! 2.3.0 模板导出有问题,请使用2.3.0.1修复版本

	
---------------------------
EasyPoi的主要特点
--------------------------
	1.设计精巧,使用简单
	2.接口丰富,扩展简单
	3.默认值多,write less do more
	4.AbstractView 支持,web导出可以简单明了

---------------------------
EasyPoi的几个入口工具类
---------------------------

	1.ExcelExportUtil Excel导出(
	普通导出,模板导出)
	2.ExcelImportUtil Excel导入
	3.WordExportUtil Word导出(只支持docx ,doc版本poi存在图片的bug,暂不支持)
	
---------------------------
关于Excel导出XLS和XLSX区别
---------------------------

	1.导出时间XLS比XLSX快2-3倍
	2.导出大小XLS是XLSX的2-3倍或者更多
	3.导出需要综合网速和本地速度做考虑^~^
	
---------------------------
几个工程的说明
---------------------------
	1.easypoi 父包--作用大家都懂得
	2.easypoi-annotation 基础注解包,作用与实体对象上,拆分后方便maven多工程的依赖管理
	3.easypoi-base 导入导出的工具包,可以完成Excel导出,导入,Word的导出,Excel的导出功能
	4.easypoi-web  耦合了spring-mvc 基于AbstractView,极大的简化spring-mvc下的导出功能
	5.sax 导入使用xercesImpl这个包(这个包可能造成奇怪的问题哈),word导出使用poi-scratchpad,都作为可选包了
--------------------------
maven 
--------------------------
maven库应该都可以了
SNAPSHOT 版本
https://oss.sonatype.org/content/repositories/snapshots/
```xml
		  
			 org.jeecg 
			 easypoi-base 
			 2.3.0.2 
		 
		 
			 org.jeecg 
			 easypoi-web 
			 2.3.0.2 
		 
		 
			 org.jeecg 
			 easypoi-annotation 
			 2.3.0.2 
		 
```
	
---------------------------
EasyPoi 文档
---------------------------
这几篇是旧的教程,不过和现在大同小异

[Excel 介绍篇](http://u.720life.cn/g/bad0229988d57a2cda540510fa08f745518f29e7e64bd8e441f9de0a4c141eace91b74bc75be54666af0275145614e6257c6da691a3f890f273d70601d0d6b3608494e2d33858384b86f7d35c27d172a) 
[Excel 工具类](http://u.720life.cn/g/bad0229988d57a2cda540510fa08f745518f29e7e64bd8e441f9de0a4c141eac579e442d7eeae800c0c0a0cfd0e5ec2e4028ca070903f3433d98ccf7d7a381b05f736e22165df81b7a64a1c02912ff49) 
[Excel 注解介绍.第一篇](http://u.720life.cn/g/bad0229988d57a2cda540510fa08f745518f29e7e64bd8e441f9de0a4c141eacb4a2b51bfa9e4814b051be1f2b9b7c1976bcf8c2728b284a3707543b5b1986eeb95b4d0e2beaf2cfeb7e50ba8f5ffa0b) 
[Excel 注解介绍.第二篇](http://u.720life.cn/g/bad0229988d57a2cda540510fa08f745518f29e7e64bd8e441f9de0a4c141eacb4a2b51bfa9e4814b051be1f2b9b7c1976bcf8c2728b284a3707543b5b1986eeb95b4d0e2beaf2cfeb7e50ba8f5ffa0b) 
[Excel 实体类](http://u.720life.cn/g/bad0229988d57a2cda540510fa08f745518f29e7e64bd8e441f9de0a4c141eac2e123e6e7f4b9719cd7d2984b0ed8b4fa8052fa808b85fe5211da69961cd0e015d91f1d07eb8cfbc36d609c87ac86c68) 
[Word模板导出教程](http://u.720life.cn/g/bad0229988d57a2cda540510fa08f745518f29e7e64bd8e441f9de0a4c141eac8a4fa1a3be04f431892208902f05a7911511c222a4b466b80a128debfd75f413837c335efd9c359700d970a2cc8efac3) 

后面都是新的了

[EasyPoi-在财务报表中的应用](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d1b7d5a7135ba2c997924dc27b5ac9a882a032e40df5986e4703d8c17b600a075a503851b0ba7e4f2616e667b1203a8668fab8f5cbe43f6a552a117cf029904b67732f84da898f7d5c9f771cf1ebd45cf517ff3955c611f60d7157cb8348728ad391350927fead0b418b58e1557e0e4072522f763fe2df0d75500d17d640c297e) 

[EasyPoi-如何筛选导出属性](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d1b7d5a7135ba2c997924dc27b5ac9a882a032e40df5986e4703d8c17b600a075ef1b2ee3b2f4e0143f9ecc44b12604b2cd12a22931fbbef5e4fa2beb23856959b80e89a4158becd41767bc84c3bf5631c78195f69381177c5af96b78fbbc6b760fe702e52a671992fe2185769cfc54df) 

[EasyPoi 在spring mvc中简易开发方式](http://u.720life.cn/g/bad0229988d57a2cda540510fa08f745518f29e7e64bd8e441f9de0a4c141eaca4ce9a26a92943ee6cf9a3686a273264d3fa8b9088c9f21042f4b5d2e6d1391927a30d7291fcbf3237b5e02feade7b3c) 

[EasyPoi-新版自定义导出样式类型](http://u.720life.cn/g/bad0229988d57a2cda540510fa08f745518f29e7e64bd8e441f9de0a4c141eacc054fa25a40c84469e676a51a4a1951d575874f3cc4d1a95fb1b56775fa9f4edc37d5220a885b19c052ae99c2d4de780) 

[EasyPoi-标签-模板导出的语法介绍](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4e91fc28e5fab20ba86db6e62eec4eecc7b25fbc5cac8290ffcee58c422b386bc0735f4df8bdf83ad2b39f264515a17b4) 

[EasyPoi-Excel预览(New)](http://u.720life.cn/g/afbed876939fc26a7e72a2a67c9a533a64e09a7247c9e94e5e9025f8b20bbb87) 

[EasyPoi-多行模板输出(New)](http://u.720life.cn/g/afbed876939fc26a7e72a2a67c9a533afae04e07a8a398c6f16e31fb35d4b2c4) 

[EasyPoi-校验集成](http://u.720life.cn/g/afbed876939fc26a7e72a2a67c9a533acd312226ff41dc00cf0f6d6e62c6c2ea) 


--------------------------
EasyPoi 模板 表达式支持
--------------------------
- 空格分割
- 三目运算  {{test ? obj:obj2}}
- n: 表示 这个cell是数值类型 {{n:}}
- le: 代表长度{{le:()}} 在if/else 运用{{le:() > 8 ? obj1 :  obj2}}
- fd: 格式化时间 {{fd:(obj;yyyy-MM-dd)}}
- fn: 格式化数字 {{fn:(obj;###.00)}}
- fe: 遍历数据,创建row
- !fe: 遍历数据不创建row 
- $fe: 下移插入,把当前行,下面的行全部下移.size()行,然后插入
- !if: 删除当前列 {{!if:(test)}}
- 单引号表示常量值 ''  比如'1' 那么输出的就是 1
- &NULL& 控制
- ]] 换行符


--------------------------
pom说明
--------------------------
word和sax读取的时候才使用,就不是必须的了,请手动引用,JSR303的校验也是可选的,PDF的jar也是可选的
```xml
			 
			 
				 xerces 
				 xercesImpl 
				 ${xerces.version} 
				 true 
			 
			 
				 org.apache.poi 
				 poi-scratchpad 
				 ${poi.version} 
				 true 
			 
			
			 
			 
				 org.hibernate 
				 hibernate-validator 
				 5.1.3.Final 
				 true 
			 
			
			 
				 org.apache.bval 
				 org.apache.bval.bundle 
				 1.1.0 
			 
			
			 
			 
				 com.itextpdf 
				 itextpdf 
				 5.5.6 
				 true 
			 

			 
				 com.itextpdf 
				 itext-asian 
				 5.2.0 
				 true 
			 
```

--------------------------
版本修改
--------------------------
 - 2.3.0.1 修复bug,推荐更新
 	- 提供的PDF基础的Excel导出支持
 	- 提供了Excel Charts的导出支持
 	- 升级了ＰＯＩ
 	- 提供了Word换行支持
 	- 图片提供统一缓存
 	- 增加Cell取值工具，自动分辨合并单元格和独立单元格
 	- 修复合并单元格,获取cell改为递归,之前判断有问题
 	- 修改了下,el表达式的==判断,给fe加上了样式自定义方法
 	- 修复if(),单字段的判断
 	- 修复其他一些bug
 - 2.1.6 校验规则不向下兼容,升级请自行考虑
 	- 其实不想升的,不过有必要的bug要修复,所以就先生上来吧
 	- 升级交易为hibernate校验,hibernate的maven自己配置可选
 	- WORD的Excel遍历 的Row,改为Insert Row
 	- 修复了font的数组越界
 	- 修复targetId的数组越界
 	- 修复多行模板导出的bug
 	- 增加了验证Excel的功能

 - 2.1.5 bug修复,建议升级
 	- fix指定sheetNum导入的bug
 	- add导入时候setIndex(null) 可以防止识别为集合的问题
 	- fix导入excel列数量判断有bug，导致有些列数漏掉校验
 	- update修改了getValue的方式,减少导入cell value识别错误
 - 2.1.4
 	- 模板输出自动合并单元格功能
 	- 多行模板数据导出
 	- 导出链接功能
 	- 把反射加入了缓存
 	- word和Excel语法保持了统一
 	- Excel to Html 增加了图片显示和缓存功能
 	- 导入增加一个参数startSheetIndex 用以指定sheet位置

 - 2.1.3
 	- 屏蔽了科学计数法的问题
 	- 修复了多模版记得清空记录信息
 	- 加入了map setValue的接口,用以自定义setValue,主要是可以自定义key
 	- 把合并单元格的数据提起出来,让大家都可以复用
 	- 多个sheet导出问题

 - 2.1.2
 	- groupId 改成org.jeecg,为了以后可以直接提交到中央库了
 	- 把test 那个模块删除了
 	- 提供了Excel 预览的功能
 	- type 新增一个 4类型,用于Excel是数字,但是java 是String,防止科学计数法
 	- 修复一些bug
 - 2.1.1-release -小更新/防止下一个预览功能太久不能发布更新
 	- $fe标签
 	- 几个可能影响使用的bug
 	- 导入Map的支持
 - 2.0.9-release--模板功能更新
 	- 修复了中文路径,float类型导入等bug
 	- 增加了根据CellStyler判断cell类型的功能
 	- 优化了一下代码,sort 的compare 改为类实现接口,getValue统一由public处理
 	- height和width 都改成double 可能更加准确的调整
 	- 升级到common-lang3
 	- 可以循环解析多个模板
 	- !!模板增加了多个标签功能
 - 2.0.8-release--小版本更新
 	- 分开了基础注解和base包,编译maven多模块集成
 	- 加强了Excel导入的校验功能,可以追加错误信息,过滤不合格数据
 	- 修复了spring mvc下的07版本不支持的问题
 	- 添加了@  Controller 注解,扫描org.jeecgframework.poi.excel.view路径就可以了,不用写bean了
 	- 加强了styler的自定义功能,参数改为entity,自由控制
 	- test包下面增加了几个demo
 	- 导出添加了一个冰冻列属性,可以简单执行
 	- PS: 经过这段时间项目中的测试,模板导出Excel复杂报表可以省5倍以上的时间,特别是样式复杂的完全可以在Excel中完成,不是在代码中完成了
 - 2.0.7-release--推荐更新
 	- 增加了合计的参数,便于统计合计信息
 	- 修改了样式设置,使用默认设置,提供其他设置,和样式接口
 	- 模板导出增加了插入导出的功能
 	- 模板导出重用了Excel导出的代码功能更加强劲
 	- 新增了Sax导入方式,大数据导入提供接口操作
 	- Word修改了页眉页脚不替换的bug
 	- 修改了捕获异常日志的bug
 	- 修复了模板导出,Spring View没识别版本的bug
 	- 修复了其他一些小bug
 - 2.0.6-release
 	- 修复导入的自定义格式异常
 	- 修复导入的BigDecimal不识别
 	- 导出大数据替换为SXSSFWorkbook,提高07版本Excel导出效率
 	- 根据sonar的提示,修复编码格式问题
 	- 做了更加丰富的测试
 	- word 导出的优化
 		
 - 2.0.6-SNAPSHOT
	 - 增加map的导出
	 - 增加index 列




---------------------------
EasyPoi导出实例
---------------------------
1.注解,导入导出都是基于注解的,实体上做上注解,标示导出对象,同时可以做一些操作
```Java
	@ExcelTarget("courseEntity")
	public class CourseEntity implements java.io.Serializable {
	/** 主键 */
	private String id;
	/** 课程名称 */
	@Excel(name = "课程名称", orderNum = "1", needMerge = true)
	private String name;
	/** 老师主键 */
	@ExcelEntity(id = "yuwen")
	@ExcelVerify()
	private TeacherEntity teacher;
	/** 老师主键 */
	@ExcelEntity(id = "shuxue")
	private TeacherEntity shuxueteacher;

	@ExcelCollection(name = "选课学生", orderNum = "4")
	private List  students;
```
2.基础导出
	传入导出参数,导出对象,以及对象列表即可完成导出
```Java
	HSSFWorkbook workbook = ExcelExportUtil.exportExcel(new ExportParams(
				"2412312", "测试", "测试"), CourseEntity.class, list);
```
3.基础导出,带有索引
	在到处参数设置一个值,就可以在导出列增加索引
```Java
	ExportParams params = new ExportParams("2412312", "测试", "测试");
	params.setAddIndex(true);
	HSSFWorkbook workbook = ExcelExportUtil.exportExcel(params,
			TeacherEntity.class, telist);
```			
4.导出Map
	创建类似注解的集合,即可完成Map的导出,略有麻烦
```Java
	List  entity = new ArrayList ();
	entity.add(new ExcelExportEntity("姓名", "name"));
	entity.add(new ExcelExportEntity("性别", "sex"));

	List > list = new ArrayList >();
	Map  map;
	for (int i = 0; i  ();
		map.put("name", "1" + i);
		map.put("sex", "2" + i);
		list.add(map);
	}

	HSSFWorkbook workbook = ExcelExportUtil.exportExcel(new ExportParams(
			"测试", "测试"), entity, list);	
```			
5.模板导出
	根据模板配置,完成对应导出
```Java
	TemplateExportParams params = new TemplateExportParams();
	params.setHeadingRows(2);
	params.setHeadingStartRow(2);
	Map  map = new HashMap ();
    map.put("year", "2013");
    map.put("sunCourses", list.size());
    Map  obj = new HashMap ();
    map.put("obj", obj);
    obj.put("name", list.size());
	params.setTemplateUrl("org/jeecgframework/poi/excel/doc/exportTemp.xls");
	Workbook book = ExcelExportUtil.exportExcel(params, CourseEntity.class, list,
			map);
```			
6.导入
	设置导入参数,传入文件或者流,即可获得相应的list
```Java
	ImportParams params = new ImportParams();
	params.setTitleRows(2);
	params.setHeadRows(2);
	//params.setSheetNum(9);
	params.setNeedSave(true);
	long start = new Date().getTime();
	List  list = ExcelImportUtil.importExcel(new File(
			"d:/tt.xls"), CourseEntity.class, params);
```	

7.和spring mvc的无缝融合
	简单几句话,Excel导出搞定
```Java
	@RequestMapping(params = "exportXls")
	public String exportXls(CourseEntity course,HttpServletRequest request,HttpServletResponse response
			, DataGrid dataGrid,ModelMap map) {

        CriteriaQuery cq = new CriteriaQuery(CourseEntity.class, dataGrid);
        org.jeecgframework.core.extend.hqlsearch.HqlGenerateUtil.installHql(cq, course, request.getParameterMap());
        List  courses = this.courseService.getListByCriteriaQuery(cq,false);

        map.put(NormalExcelConstants.FILE_NAME,"用户信息");
        map.put(NormalExcelConstants.CLASS,CourseEntity.class);
        map.put(NormalExcelConstants.PARAMS,new ExportParams("课程列表", "导出人:Jeecg",
                "导出信息"));
        map.put(NormalExcelConstants.DATA_LIST,courses);
        return NormalExcelConstants.JEECG_EXCEL_VIEW;

	}
```

8.Excel导入校验,过滤不符合规则的数据,追加错误信息到Excel,提供常用的校验规则,已经通用的校验接口
```Java
    @Excel(name = "Email", width = 25)
    @Max(value = 15,message = "max 最大值不能超过15")
    private int email;
    /**
     * 手机号
     */
    @Excel(name = "Mobile", width = 20)
    @NotNull
    private String mobile;
    
    ExcelImportResult  result = ExcelImportUtil.importExcelVerify(new File(
            "d:/tt.xls"), ExcelVerifyEntity.class, params);
    for (int i = 0; i  > list = ExcelImportUtil.importExcel(new File(
			"d:/tt.xls"), Map.class, params);
```	



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)