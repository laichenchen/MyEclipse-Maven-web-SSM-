详细请参见http://blog.csdn.net/v123411739/article/details/50742885

1.安装maven和配置

（1）下载安装MAVEN

（2）配置环境变量  MAVEN_HOME:MAVEN的安装地址
                path:%MAVEN_HOME%\bin
                
（3）cmd 命令行输入：mvn --version 查看MAVEN版本是否安装成功

（4）MAVEN实践  命令行输入：mvn help:system的命令，执行后，会在C:\Users\Administrator\（user_home）下生成.m2文件夹就能看到本地仓库了

（5）复制 MAVEN_HOME/conf/setting.xml文件到C:/Users/Administrator/.m2/setting.xml，修改setting.xml里面的本地仓库地址

2.MyEclipse配置Maven

（1）MyEclipse的preferences里面Maven4MyEclipse下面的installations,add刚刚安装的Maven地址

（2）MyEclipse的preferences里面Maven4MyEclipse下面的user setting ,上面选择.m2文件夹内的setting，下面选择本地仓库的地址

3.创建Maven项目

  File->New->others，搜索maven，如果看到有Maven Project则代表配置成功。
  下一步。。。
  filter的时候选择 maven-archetype-webapp.继续下一步。
  继续填写group Id,artifact Id(项目名称),version。
  finish
  
4.搭建Spring+SpringMVC+Mybatis框架

(1)pom.xml

  <!-- 用来设置版本号 -->  
    <properties>  
        <srping.version>4.0.2.RELEASE</srping.version>  
        <mybatis.version>3.2.8</mybatis.version>  
        <slf4j.version>1.7.12</slf4j.version>  
        <log4j.version>1.2.17</log4j.version>  
    </properties>
     <!-- 用到的jar包 -->
     <dependencies>  
        <!-- 单元测试 -->  
        <dependency>  
            <groupId>junit</groupId>  
            <artifactId>junit</artifactId>  
            <version>4.11</version>  
            <!-- 表示开发的时候引入，发布的时候不会加载此包 -->  
            <scope>test</scope>  
        </dependency>  
        <!-- java ee包 -->  
        <dependency>  
            <groupId>javax</groupId>  
            <artifactId>javaee-api</artifactId>  
            <version>7.0</version>  
        </dependency>  
        .
        .
        .
     </dependencies> 
     
(2)在src/main/resources下添加如下配置文件

    applicationContext.xml
    jdbc.properties
    log4j.properties
    spring-dao.xml
    spring-db.xml
    spring-tx.xml
    
(3)在WEB-INF文件夹下添加/修改以下配置文件

    spring-mvc.xml
    web.xml
    
(4)在src/main/java下添加如下包和类

    com.chillax.controller------UserController.java
    com.chillax.dao------IUserDao.java
    com.chillax.dto------User.java
    com.chillax.service------IUserService.java
    com.chillax.service.Impl------UserServiceImpl.java
    com.chillax.mapper------UserMapper.xml

(5)在WEB-INF文件夹下创建jsp文件夹，并添加userList.jsp，showUser.jsp、addUser.jsp

(6)创建数据库，并创建表

（7）部署发布项目，进行测试
     



