## Changes in dispatcher-servlet.xml for Service and Repository implementation classes scanning by Spring. 
- Create commonbeans.xml in WEB-INF folder and add below code.
```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context"
	xmlns:mvc="http://www.springframework.org/schema/mvc"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/context
        http://www.springframework.org/schema/context/spring-context.xsd
        http://www.springframework.org/schema/mvc
        http://www.springframework.org/schema/mvc/spring-mvc.xsd">

	<context:component-scan base-package="com.yash.damsapp.daoimpl" />
	<context:component-scan base-package="com.yash.damsapp.serviceimpl" />
	<mvc:annotation-driven />
</beans>
```
- Add commonbeans.xml in dispatcher-servlet.xml file
```
<import resource="commonbeans.xml"/>
```
