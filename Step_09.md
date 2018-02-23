## Adding static resource in your application

You will not be able to add the static resources as CSS, JS and Images in your jsp pages directly. Because all the jsp pages are inside
WEB-INF. All the static resources can not access the Internal resource directly. 
Spring provides a way to configure static resources using spring tag library. for this you will have to configure **<mvc:resource>** tag
in dispatcher servlet. 

### Find the below changes in the **dispatcher-servelt.xml** file for the static resource configuration

>  <!-- reading static resource like css, js or images -->	
	 <mvc:resources location="/static/" mapping="/static/**"/>
  
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
