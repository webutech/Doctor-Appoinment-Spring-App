## Creating Maven project and add required dependencies in pom.xml

### Project Creation Steps

- Go on File >  New > Other...
- Write maven in the filter text box
- Select Maven Project
- Let default setting as it is and click on next
- Write web in filter text box
- Select org.apache.maven.archtypes 1.0 version option
- Click on next
- provide the package in group id
- provide the project name in artifact id
- Click on finish

### Creating src/main/java and src/test/java source folders

- Go on src > main (folder)
- press Ctrl + n
- Write folder in filter text box
- give it a name as java

- Go on src (folder)
- Press Ctrl + n
- Write folder in filter text box
- give it a name as test
- repeat the steps for creating java folder inside test folder



### Add the targeted runtime in project (Adding tomcat server)
- select project and press Alt + Enter
- from the project properties window select targetted runtime option and choose tomcat server.
- click on ok button

### Add below dependencies in pom.xml

```
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.yash</groupId>
  <artifactId>dams</artifactId>
  <packaging>war</packaging>
  <version>0.0.1-SNAPSHOT</version>
  <name>dams Maven Webapp</name>
  <url>http://maven.apache.org</url>
  <dependencies>
     <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.12</version>
      <scope>test</scope>
    </dependency>
     <!-- https://mvnrepository.com/artifact/org.springframework/spring-context -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-context</artifactId>
    <version>4.3.7.RELEASE</version>
</dependency>    
    <!-- https://mvnrepository.com/artifact/org.springframework/spring-webmvc -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-webmvc</artifactId>
    <version>4.3.7.RELEASE</version>
</dependency>   
    <!-- https://mvnrepository.com/artifact/org.springframework/spring-jdbc -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-jdbc</artifactId>
    <version>4.3.7.RELEASE</version>
</dependency>
    <!-- https://mvnrepository.com/artifact/org.apache.commons/commons-dbcp2 -->
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-dbcp2</artifactId>
    <version>2.1.1</version>
</dependency>
    <!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>5.1.6</version>
</dependency>

<!-- Logging support jars -->
		<dependency>
			<groupId>log4j</groupId>
			<artifactId>log4j</artifactId>
			<version>1.2.16</version>
		</dependency>
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-log4j12</artifactId>
			<version>1.7.12</version>
		</dependency>
   <!-- https://mvnrepository.com/artifact/javax.servlet/jstl -->
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>jstl</artifactId>
    <version>1.2</version>
</dependency>
  </dependencies>
  <build>
    <finalName>dams</finalName>
  </build>
</project>

```
