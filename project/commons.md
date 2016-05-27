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
    DiskFileItemFactory diskFileItemFactory = new DiskFileItemFactory();
    ServletContext servletContext = request.getServletContext();
    String attribute= "javax.servlet.context.tempdir";
    File repository = (File) servletContext.getAttribute(attribute);
    diskFileItemFactory.setRepository(repository);

    ServletFileUpload servletFileUpload = new ServletFileUpload(diskFileItemFactory);

    try {
        List<FileItem> fileItems = servletFileUpload.parseRequest(request);
        for (FileItem fileItem : fileItems) {
            if (fileItem.isFormField()) {
                System.out.print(fileItem.getFieldName());
                System.out.print(" : ");
                System.out.println(fileItem.getString());
            } else {
                // FILE
                System.out.println(fileItem.getFieldName());
                System.out.println(fileItem.getName());
                System.out.println(fileItem.getContentType());
                System.out.println(fileItem.isInMemory());
                System.out.println(fileItem.getSize());

                File file = new File("d:/" + fileItem.getName());
                fileItem.write(file);
            }
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
    ```
    
3. Lombok

  > [Project Lombok](https://projectlombok.org/)

  > [Lobmok Plugin on Github](https://github.com/mplushnikov/lombok-intellij-plugin)

  - bulid.gradle
  ```gradle
  compile 'org.projectlombok:lombok:1.16.8'
  ```
  
  - IDEA
      - install Lombok plugin
        - [Lombok Plugin](http://plugins.jetbrains.com/plugin/6317?pr=idea)
      - File > Settings > Build, Execution, Deployment > Compiler > Annotation Processors
        - check "Enable annotation processing"

  - Model class
  
    ```java
    import lombok.Data;
    import lombok.EqualsAndHashCode;

    @Data
    @EqualsAndHashCode(callSuper = true)
    public class Admin extends BaseModel {
        private Integer id;
        private String email;
        private String username;
        private String password;
    }
    ```

4. 日志处理

1. SLF4J

  > Simple Logging Facade `[fə'sɑːd]` for Java

  - `Logger` interface
  - `LoggerFactory` class

2. Log4j

  > Log For Java

    - 配置 rootLogger
    - 配置日志信息输出目的地 `Appender`
    - 配置日志信息的输出格式 `Layout`
  
    ```java
    public class Log4jTest {
          private static Logger logger = LoggerFactory.getLogger(Log4jTest.class);
          public static void main(String[] args) {
              logger.trace("trace...");
              logger.debug("debug...");
              logger.info("info...");
              logger.warn("warn....");
              logger.error("error...");
          }
      }
    ```
    
3. Logback

  > [Logback Project](http://logback.qos.ch/)

  > Based on our previous work on log4j, logback internals have been re-written to perform about ten times faster on certain critical execution paths. Not only are logback components faster, they have a smaller memory footprint as well.