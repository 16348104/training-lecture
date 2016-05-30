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

  - SLF4J

    > Simple Logging Facade `[fə'sɑːd]` for Java

    - `Logger` interface
    - `LoggerFactory` class

  2. Log4j

    > Log For Javaw

    - build.gradle

      ```gradle
      compile 'org.slf4j:slf4j-log4j12:1.7.21'
      ```

    - 在类路径根目录下创建 `log4j.properties` 文件

    - 配置 `rootLogger`

      ```properties
      # rootLogger: all trace debug info warn error fatal off
      log4j.rootLogger = error, console
      ```

      - 日志级别
        - `all`
        - `trace` 
        - &#10003; `debug`
        - &#10003; `info`
        - &#10003; `warn`
        - &#10003; `error`
        - `fetal`
        - `off`

    - 指定具体类的日志输出级别，覆盖 `rootLogger` 级别

      ```properties
      log4j.logger.demo = trace
      ```

    - 配置日志信息输出目的地 `Appender`

      ```properties
      # console appender
      log4j.appender.console=org.apache.log4j.ConsoleAppender
      ```

        - `log4j.ConsoleAppender` `控制台`
        - `log4j.FileAppender` `文件`
        - `log4j.DailyRollingFileAppender` `每天产生一个日志文件`
        - `log4j.RollingFileAppender` `文件到达指定尺寸时产生一个新的文件`
        - `log4j.WriterAppender` `以流格式发送到任意指定的地方`
        - `log4j.appender.MAIL` `发送邮件`

    - 配置日志信息的输出格式 `Layout`

      ```properties
      # console layout
      log4j.appender.console.layout=org.apache.log4j.PatternLayout
      log4j.appender.console.layout.ConversionPattern=%m%n
      ```

      - 布局方式
        - `org.apache.log4j.HTMLLayout` `HTML 表格形式布局`
        - `org.apache.log4j.PatternLayout` `灵活地指定布局模式`
        - `org.apache.log4j.SimpleLayout` `日志信息的级别和信息字符串`
        - `org.apache.log4j.TTCCLayout` `日志产生的时间、线程、类别等等信息`
      - 输出格式
        - `%m` 输出代码中指定的消息
        - `%p` 输出优先级，即 `DEBUG`，`INFO`，`WARN`，`ERROR`，`FATAL`
        - `%r` 输出自应用启动到输出该 log 信息耗费的毫秒数
        - `%c` 输出所属的类目，通常就是所在类的全名
        - `%t` 输出产生该日志事件的线程名
        - `%n` 输出一个回车换行符，Windows 平台为 `\r\n`，Unix 平台为 `\n`
        - `%d` 输出日志时间点的日期或时间，默认格式为 `ISO8601`，也可以在其后指定格式
            - 举例：`%d{yyy MMM dd HH:mm:ss,SSS}`
            - 输出类似：2016年05月27日 12:10:28,921
        - `%l` 输出日志事件的发生位置，包括类目名、发生的线程，以及在代码中的行数
          - 举例：`Log4jTest.main(Log4jTest.java:10)`

    - Log4j Test

      ```java
      package demo.test;

      import org.slf4j.Logger;
      import org.slf4j.LoggerFactory;

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

      /*

      output:

      trace...
      debug...
      info...
      warn....
      error...

      */
      ```

  3. Logback

    > [Logback Project](http://logback.qos.ch/)

    > Based on our previous work on log4j, logback internals have been re-written to perform about ten times faster on certain critical execution paths. Not only are logback components faster, they have a smaller memory footprint as well.

    - build.gradle
    
    ```gradle
    compile 'ch.qos.logback:logback-access:1.1.3'
    compile 'ch.qos.logback:logback-site:1.1.3'
    compile 'org.slf4j:slf4j-simple:1.7.21'
    ```