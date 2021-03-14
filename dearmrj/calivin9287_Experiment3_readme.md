# 《JAVA EE企业级架构》课程实验报告
院（系）名称：网络空间安全学院  
专业班级： 17软卓2班  
学号： 201741412208  
姓名： 吴永满     
实验题目：  实验3 JavaBean                       
实验日期：2019.4.27
实验（上机）学时： 2  
成绩：

## 一、实验内容、要求
*实现一个用户注册/登录模块，大致功能如下：
>1、	启动首页为用户登录页，本地账号登录或莞工中央认证登录成功后，返回用户中心。  
2、	如果用户还没有用户名和密码，则请他/她先进行注册，注册信息写入一个文本文件中，注册成功后直接回到用户中心。  
3、	把存取用户名/密码及验证用户名/密码都放在一个JavaBean中，在bean中对用户的合法性进行验证。  
4、	登录不成功则返回登录页面，提示用户名不存在或密码错误。  
5、	如果用户选择莞工中央认证登录，则使用“工号”自动创建一个本地账号，密码预设为“123456”，并把莞工中央认证与本地账号关联。  
6、	任何页面发生错误时，请导向error.jsp。  
7、	使用JavaBean，实现下面的业务功能：  
a.	上传自己的照片。（照片保存在本地文件系统）  
b.	查看用户信息
>
## 二、所采用的Java EE技术规范
1. JSP的基础语法  
2. Filter配置
3. Serlet配置
4. HttpClient组件
5. IO流的读取与写入
6. web.xml的配置
7. jsonbean
8. html，css，js

## 三、实验的主要模块及其功能
### loginservlet.java
获取前端网页post请求中的信息，读取txt文件中的用户信息，然后一一检验账号，密码是否符合  
若正确则存入session中
>
                    HttpSession session = request.getSession(true);
                    Map  map = new HashMap ();
                    map.put("用户名",personDTO.getUsername());
                    map.put("密码",personDTO.getPassword());
                    map.put("手机号码",personDTO.getPhonenumber());
                    map.put("电子邮箱",personDTO.getEmail());
                    //HttpSession session = request.getSession(true);
                    session.setAttribute("userName", map);
                    session.setAttribute("token", "not null");
>
错误则提示用户账号或者密码错误
### registerservlet.java
获取前端网页post请求中的注册信息，使用jsonbean完成json的转化，接着判断该用户是否已存在，再转成字符串的形式存入txt文件中
 ````
 
 while ((line = br.readLine()) != null) {
            userinformation personDTO = jsonb.fromJson(line, userinformation.class);
            if(personDTO.getUsername().equals(username))
            {
                request.setCharacterEncoding("UTF-8");
                response.setContentType("text/html;charset=UTF-8");
                response.getWriter().println("用户已存在！！请退回上一步继续操作");
                break;
            }
            }

        BufferedWriter out = null;
        try {
            out = new BufferedWriter(new OutputStreamWriter(
                    new FileOutputStream("src/main/LOGIN.txt", true)));
            out.write(str+"\n");
        } catch (Exception e) {
            response.sendRedirect("/error.html");
        } finally {
            try {
                out.close();
            } catch (IOException e) {
                response.sendRedirect("/error.html");
            }
        }
        request.setAttribute("msg","用户注册成功");
        response.sendRedirect("/index.html");
    }
 ````
 ### joinmessage.java
 将莞工登录的账号和本地账号关联起来
 ````
 while ((line = bufferedReader.readLine()) != null)
         {
             userinformation personDTO = jsonb.fromJson(line, userinformation.class);
             if(personDTO.getStu_number().equals(dataDTO3.getUsername()))
             {
                 check_flag = 0;
                 HttpSession session = request.getSession(true);
                 Map  map = new HashMap ();
                 map.put("用户名",personDTO.getUsername());
                 map.put("密码",personDTO.getPassword());
                 map.put("学号",personDTO.getStu_number());
                 map.put("手机号码",personDTO.getPhonenumber());
                 map.put("电子邮箱",personDTO.getEmail());
                 //HttpSession session = request.getSession(true);
                 session.setAttribute("userName", map);
                 session.setAttribute("token", "not null");
             }
             buf.append(line + '\n');
         }
 ````
### ALLFilter.java
该过滤器通过request.getSession()得到一个HttpSession对象，用于判断用户是否处于登录状态，如果是就重定向到index.jsp,如果不是就直接登出。
### DataDTO1.java
定义发送POST请求的对象对应的java类
### DataDTO2.java
定义接收第一个POST请求返回的JSON数据对应的java类
### DataDTO3.java
定义接收第一个POST请求返回的学生信息JSON数据对应的java类
### dgut.java
接受token，生成一个dataDTO1类的对象，并通过QuickStart.postJson发送到https://cas.dgut.edu.cn/ssoapi/v2/checkToken  
```java
  String token = request.getParameter("token");

  String userip = request.getLocalAddr();
  DataDTO1 dataDTO1 = new DataDTO1(token, "javaee", "b3b52e43ccfd", userip);
```
将返回的JSON字符串保存在S1中
通过Jsonb类方法.fromJson将s1转化为DataDTO2类的实体对象  
```java
  Jsonb jsonb = JsonbBuilder.create();
  DataDTO2 dataDTO2 = jsonb.fromJson(s1, DataDTO2.class);
```
接下来判断是否成功返回，如果成功则新建一个链表，将"access_token"的属性值和"openid"的属性值添加到其中，并通过QuickStart.post的方法发送到 https://cas.dgut.edu.cn/oauth/getUserInfo中，同样的，将返回的json字符串转化成DataDTO3的实体对象
最终将对象dataDTO3的所有属性值保存到Session中
```java
if (dataDTO2.getMessage()!=null&&dataDTO2.getMessage().equals("success")) {
   List  list = new ArrayList<>();
   list.add(new BasicNameValuePair("access_token", dataDTO2.getAccess_token()));
   list.add(new BasicNameValuePair("openid", dataDTO2.getOpenid()));
   String s2 = QuickStart.post("https://cas.dgut.edu.cn/oauth/getUserInfo", list);

    if(s2!=null&&s2=="{\n" +
           "\"error\":1,\n" +
           "\"message\":\"access-token不存在或已过期\"\n" +
           "}")
   {
    System.out.println("access-token不存在或已过期");
   }
   else {
    DataDTO3 dataDTO3 = jsonb.fromJson(s2, DataDTO3.class);

    HttpSession httpSession = request.getSession();
    httpSession.setAttribute("username", dataDTO3.getUsername());
    httpSession.setAttribute("name", dataDTO3.getName());
    httpSession.setAttribute("group", dataDTO3.getGroup());
    httpSession.setAttribute("openid", dataDTO3.getOpenid());
    httpSession.setAttribute("wx_openid", dataDTO3.getWx_openid());

    response.sendRedirect("http://localhost:8080/index.jsp");
   }
}
```
## 四、程序运行时的输入数据/输出结果
### 登陆界面
![avatar](src/image/1.jpg)
### 注册界面
![avatar](src/image/2.png)
### 登陆失败
![avatar](src/image/3.png)
### 上传头像
![avatar](src/image/4.png)
### 成功上传头像
![avatar](src/image/5.png)
### 错误界面
![avatar](src/image/6.png)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1a3691310f86dda39b0e73da14737e7dfc3c4e51effe9226c0c65fcce52dfa83245412f45df052a3e305f8af7f12f4eb)