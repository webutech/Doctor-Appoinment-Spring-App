## Addition of Files/ Folder/ Code

### Add spring view files (jsp files in Internal Resource)
- Create view folder in WEB-INF folder
- Create a **home.jsp** page
- add below code in **home.jsp** page
```
  <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
  <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
  <title>Insert title here</title>
  </head>
  <body>
    welcome in home page
  </body>
  </html>
```

### Create controller package and add **UserController**
- Create com.yash.dams.controller package in [src/main/java]
- Create UserController Class and write below code
```
  package com.yash.dams.controller;
  import org.springframework.stereotype.Controller;
  import org.springframework.web.bind.annotation.RequestMapping;
  import org.springframework.web.bind.annotation.RequestMethod;

  /**
  * UserController is used to controls various activities related to user
  * @author sharma.pankaj
  *
  */
  @Controller
  @RequestMapping("/user")
  public class UserController {
	  @RequestMapping(value="/home.htm", method=RequestMethod.GET)
	  public String showHomePage(){
  		return "home";
	  }
  }
```

### Make changes in to **index.jsp** page
- index.jsp is our lending page that is used to redirect us on home page. this call will goes first to front controller that will check
it for .htm request, and further this will redirect the request to intended controller.
- make the below changes in your index.jsp page. Save all the changes and run your application. your application should run and "Welcome
in home page" should be displayed. 

```
<%
    String path=application.getContextPath();    
    response.sendRedirect(path+"/user/home.htm");
%>
```
