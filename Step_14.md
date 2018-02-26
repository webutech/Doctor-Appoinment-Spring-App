## JDBC Configuration

Here we will be using the Spring JDBC template along with BasicDataSource. we will be creating a separate xml file for configuring jdbc properties using properties file. 

### Steps
- Create **resources** package in src/main/java
- Create jdbc.properties file inside resources package
- add below code in jdbc.properties file
```
### Author : Pankaj Sharma ########
### JDBC Configuration ########
jdbc.driverClassName=com.mysql.jdbc.Driver
jdbc.url=jdbc:mysql://localhost/dams_db
jdbc.username=root
jdbc.password=root
```
- Create **jdbc.xml** in WEB-INF folder and add below code
```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
       ">

	<bean
		class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer">
		<property name="locations" value="classpath:resources/jdbc.properties" />
	</bean>
	<!-- DataSource configuration -->
	<bean id="dataSource" class="org.apache.commons.dbcp2.BasicDataSource">
		<property name="driverClassName" value="${jdbc.driverClassName}" />
		<property name="url" value="${jdbc.url}" />
		<property name="username" value="${jdbc.username}" />
		<property name="password" value="${jdbc.password}" />
		<property name="initialSize" value="3" />
		<property name="maxIdle" value="10" />
	</bean>

</beans>

```
- import **jdbc.xml** in dispatcher-servlet.xml file.
- follow the below code
```
<import resource="jdbc.xml"/>
```
