## Adding static resource in your application

You will not be able to add the static resources as CSS, JS and Images in your jsp pages directly. Because all the jsp pages are inside
WEB-INF. All the static resources can not access the Internal resource directly. 
Spring provides a way to configure static resources using spring tag library. for this you will have to configure **<mvc:resource>** tag
in dispatcher servlet. 

### Create static resource folders and add required files. 
- Create static folder in the webapp folder
- Inside static folder create css, js , images and fonts folder
- Download bootstrap library and put all the files in css and js folders respectively.

Note : we are planning to use bootstrap on our application so taking bootstrap libraries. 

### Find the below changes in the **dispatcher-servelt.xml** file for the static resource configuration

>  <!-- reading static resource like css, js or images -->	
>  <mvc:resources location="/static/" mapping="/static/**"/>
  
```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
	xmlns:context="http://www.springframework.org/schema/context"
	xmlns:mvc="http://www.springframework.org/schema/mvc"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/context
        http://www.springframework.org/schema/context/spring-context.xsd
        http://www.springframework.org/schema/mvc
        http://www.springframework.org/schema/mvc/spring-mvc.xsd">

	<!-- component scan -->
	<context:component-scan base-package="com.yash.dams.controller" />
	
  <!-- reading static resource like css, js or images -->	
	<mvc:resources location="/static/" mapping="/static/**"/>

	<!--  for annotations -->
	<mvc:annotation-driven />

	<!--  for view resolver -->
	<bean id="jspViewResolver"
		class="org.springframework.web.servlet.view.InternalResourceViewResolver">

		<property name="prefix" value="/WEB-INF/view/" />
		<property name="suffix" value=".jsp" />
	</bean>
</beans>
```

### spring link preparation for static resources
- Now you will have to prepare the static rource link with spring tag library. 
- For this we will have to add the spring tag library to jsp page and prepare the link in <head> section
- follow below code and complete code is provided as well.

> <s:url var="url_bootstrap" value="/static/css/bootstrap.min.css" />
> <link href="${url_bootstrap}" type="text/css" rel="stylesheet">

### **home.jsp**
- add spring tag library on top of the page
- in the head section prepare links and use <link> tag to add the  files from the prepared location
- add the bootstrap related code

```
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
	pageEncoding="ISO-8859-1"%>
<%@ taglib uri="http://www.springframework.org/tags" prefix="s"%>
<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
<title>DAMS-Home Page</title>

<%-- Spring link preparation --%>
<s:url var="url_bootstrap" value="/static/css/bootstrap.min.css" />
<s:url var="url_font_awesome" value="/static/css/font-awesome.min.css" />

<link href="${url_bootstrap}" type="text/css" rel="stylesheet">
<link href="${url_font_awesome}" type="text/css" rel="stylesheet">
</head>
<body>
	<div class="container">
		<header>
			<nav class="navbar navbar-expand-lg navbar-light bg-light">
				<a class="navbar-brand" href="#">Navbar</a>
				<button class="navbar-toggler" type="button" data-toggle="collapse"
					data-target="#navbarSupportedContent"
					aria-controls="navbarSupportedContent" aria-expanded="false"
					aria-label="Toggle navigation">
					<span class="navbar-toggler-icon"></span>
				</button>

				<div class="collapse navbar-collapse" id="navbarSupportedContent">
					<ul class="navbar-nav mr-auto">
						<li class="nav-item active"><a class="nav-link" href="#">Home
								<span class="sr-only">(current)</span>
						</a></li>
						<li class="nav-item"><a class="nav-link" href="#">Link</a></li>
						<li class="nav-item dropdown"><a
							class="nav-link dropdown-toggle" href="#" id="navbarDropdown"
							role="button" data-toggle="dropdown" aria-haspopup="true"
							aria-expanded="false"> Dropdown </a>
							<div class="dropdown-menu" aria-labelledby="navbarDropdown">
								<a class="dropdown-item" href="#">Action</a> <a
									class="dropdown-item" href="#">Another action</a>
								<div class="dropdown-divider"></div>
								<a class="dropdown-item" href="#">Something else here</a>
							</div></li>
						<li class="nav-item"><a class="nav-link disabled" href="#">Disabled</a>
						</li>
					</ul>
					<form class="form-inline my-2 my-lg-0">
						<input class="form-control mr-sm-2" type="search"
							placeholder="Search" aria-label="Search">
						<button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
					</form>
				</div>
			</nav>
		</header>
	</div>
</body>
</html>
```
