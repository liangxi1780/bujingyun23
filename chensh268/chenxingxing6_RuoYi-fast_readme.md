## 在线体验
> admin/admin123
演示地址：http://ruoyi.vip  

## 学习的新东西
1.BigDecimal精确的浮点数运算，工具类Arith
java的float只能用来进行科学计算或工程计算，在大多数的商业计算中，一般采用java.math.BigDecimal类来进行精确计算。
setScale(1,BigDecimal.ROUND_HALF_UP)四舍五入，2.35变成2.4
```HTML
public static void main(String[] args)
{
    System.out.println(0.2 + 0.1);
    System.out.println(add(0.2, 0.1));
    System.out.println();

    System.out.println(0.3 - 0.1);
    System.out.println(sub(0.3, 0.2));
    System.out.println();
    
    System.out.println(0.2 * 0.1);
    System.out.println(mul(0.2, 0.1));
    System.out.println();

    System.out.println(0.3 / 0.1);
    System.out.println(div(0.3, 0.1));
    System.out.println();
}


0.30000000000000004
0.3

0.19999999999999998
0.1

0.020000000000000004
0.02

2.9999999999999996
3.0
```

>BigDecimal都是不可变的（immutable）的，在进行每一步运算时，都会产生一个新的对象，所以在做加减乘除运算时千万要保存操作后的值。

---
2.BeanUtils反射实现

---
3.服务器信息
```xml
 
     com.github.oshi 
     oshi-core 
     3.5.0 
 
```


---
访问地址：http://ruoyi.vip/index

## 内置功能

1.  用户管理：用户是系统操作者，该功能主要完成系统用户配置。
2.  部门管理：配置系统组织机构（公司、部门、小组），树结构展现支持数据权限。
3.  岗位管理：配置系统用户所属担任职务。
4.  菜单管理：配置系统菜单，操作权限，按钮权限标识等。
5.  角色管理：角色菜单权限分配、设置角色按机构进行数据范围权限划分。
6.  字典管理：对系统中经常使用的一些较为固定的数据进行维护。
7.  参数管理：对系统动态配置常用参数。
8.  通知公告：系统通知公告信息发布维护。
9.  操作日志：系统正常操作日志记录和查询；系统异常信息日志记录和查询。
10. 登录日志：系统登录日志记录查询包含登录异常。
11. 在线用户：当前系统中活跃用户状态监控。
12. 定时任务：在线（添加、修改、删除)任务调度包含执行结果日志。
13. 代码生成：前后端代码的生成（java、html、xml、sql)支持CRUD下载 。
14. 系统接口：根据业务代码自动生成相关的api接口文档。
15. 在线构建器：拖动表单元素生成相应的HTML代码。
16. 连接池监视：监视当期系统数据库连接池状态，可进行分析SQL找出系统性能瓶颈。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e96f634ecfbc24a72fe629cb238ee5ef053223c95e52fc3086c62c6ec5ceddfc98232e752a6195d8753fd6ac1c9a5d504)