# Chapter 2 核心组件

> Mapper / Configuration / Mapper Interface / SqlSessionFactory / SqlSession / Service

1. Create database and table

    ```sql
    DROP DATABASE IF EXISTS test;
    CREATE DATABASE test;
    
    # user
    DROP TABLE IF EXISTS test.user;
    CREATE TABLE test.user
    (
      id       INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
      username VARCHAR(255),
      password VARCHAR(255)
    );
    ```
    
2. Update build.gradle

    ```
    compile 'org.mybatis:mybatis:3.3.0'
    ```
    
3. Create model class

    ```java
    public class User implements Seriable {
        private Integer id;
        private String username;
        private String password;
        
        // setters and getters
    }
    ```

4. Create mapper.xml

    > 注意：在使用 `Mapper` 接口时， `namespace` 的取值是 `Mapper` 接口的全限定名

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE mapper
            PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
            "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
    <mapper namespace="mapper.UserMapper">
        <insert id="create" parameterType="model.User" useGeneratedKeys="true" keyProperty="id">
            INSERT INTO user VALUES (NULL, #{username}, #{password})
        </insert>
    </mapper>
    ```
    
5. Create mybatis-config.xml

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE configuration
            PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
            "http://mybatis.org/dtd/mybatis-3-config.dtd">
    <configuration>
        <properties resource="jdbc.properties"/>
        <environments default="dev">
            <environment id="dev">
                <transactionManager type="JDBC"/>
                <dataSource type="POOLED">
                    <property name="driver" value="${driver}"/>
                    <property name="url" value="${url}"/>
                    <property name="username" value="${username}"/>
                    <property name="password" value="${password}"/>
                </dataSource>
            </environment>
        </environments>
        <mappers>
            <mapper resource="user-mapper.xml"/>
        </mappers>
    </configuration>
    ```
    
    ```
    # jdbc.properties
    driver = com.mysql.jdbc.Driver
    url = jdbc:mysql:///test
    username = your_username
    password = your_password
    ```
    
6. Create MyBatisSession sigleton class             

    ```java
    public class MyBatisSqlSession { 
        private static SqlSessionFactory sqlSessionFactory;
     
        private static SqlSessionFactory getSqlSessionFactory() { 
            if (sqlSessionFactory == null) {
                try { 
                    sqlSessionFactory = new SqlSessionFactoryBuilder().build(Resources.getResourceAsStream("mybatis-config.xml"));
                } catch (IOException e) {
                    e.printStackTrace();
                } 
            } 
            return sqlSessionFactory;
        } 
     
        public static SqlSession getSqlSession(boolean autoCommit) {
            return getSqlSessionFactory().openSession(autoCommit);
        } 
    } 
    ```
    
7. Create mapper interface

    ```java
    public interface UserMapper { 
    
        int create(User user);
    }  
    ```
    
8. Create service class

    ```java
    public class UserService {
    
        // create record by XML configuration
        private static int createUserViaXML() {
            try (SqlSession sqlSession = MyBatisSqlSession.getSqlSession(true)) {
                return sqlSession.insert("mapper.UserMapper.create", new User{"Tester1", "password1"});
            }
        }
    
        // create record by Mapper interface
        private static int createUser() {
            try (SqlSession sqlSession = MyBatisSqlSession.getSqlSession(true)) {
                UserMapper userMapper = sqlSession.getMapper(UserMapper.class);
                return userMapper.create(new User{"Tester2", "password2"});
            }
        }
        
        public static void main(String[] args) {
            createUserviaXML(); // MyBatis method 1
            createUser(); // MyBatis method 2: Type Safer
        }
    }
    ```
    
9. Create JUnit test class

    ```java
        // ...
    ```
    