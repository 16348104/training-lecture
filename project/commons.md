# 通用组件

1. 加密

  > [Jasypt](http://www.jasypt.org/)

  ```gradle
  // build.gradle
  compile 'org.jasypt:jasypt:1.9.2'
  ```
  - 密码

    ```java
    // 加密
    StrongPasswordEncryptor encryptor = new StrongPasswordEncryptor();
    password = encryptor.encryptPassword(password);
    // 验证
   StrongPasswordEncryptor encryptor = new StrongPasswordEncryptor();
   if (encryptor.checkPassword(password, encryptedPassword)) {
         // ...
   } else {
         // ...
   }
   ```
 - 文本

2. 文件上传

  > [Apache Commons FileUpload](http://commons.apache.org/proper/commons-fileupload/)

  > [quick use](http://commons.apache.org/proper/commons-fileupload/using.html)

  ```gradle
  // build.gradle
  compile 'commons-fileupload:commons-fileupload:1.3.1'
  ```
  - 表单

    ```html
    <form action="your_action_url" method="post" enctype="multipart/form-data">
        <input type="file" name="upload">
    </form>
  ```
  
  - Servlet
  
    ```java
    
    ```
    
3. Lombok

  > [Project Lombok](https://projectlombok.org/)

  > [Lobmok Plugin](https://github.com/mplushnikov/lombok-intellij-plugin)

  - bulid.gradle
  ```gradle
  compile 'org.projectlombok:lombok:1.16.8'
  ```
  
  - IDEA
      - install Lombok plugin
        - [Lombok Plugin](http://plugins.jetbrains.com/plugin/6317?pr=idea)
      - File > Settings > Build, Execution, Deployment > Compiler > Annotation Processors
        - Enable annotation processing

  - Model class
  
    ```java

    ```
