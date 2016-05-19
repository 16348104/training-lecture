# Mybatis + Spring

1. build.gradle

  ```gradle
  compile 'org.mybatis:mybatis-spring:1.3.0'
  compile 'org.springframework:spring-jdbc:4.2.6.RELEASE'
  ```

2. applicationContext.xml

  ```xml
  <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName" value="com.mysql.jdbc.Driver"/>
        <property name="url" value="jdbc:mysql:///db_name"/>
        <property name="username" value="your_username"/>
        <property name="password" value="your_password"/>
    </bean>

    <bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
        <property name="dataSource" ref="dataSource"/>
        <property name="mapperLocations" value="classpath:mapper/*.xml"/>
        <property name="typeAliasesPackage" value="demo.model"/>
    </bean>
  ```