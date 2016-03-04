# Chapter 4 Servlet

> 服务器端小程序

1. `Servlet`

    > 扩展了 `javax.servlet.http.HttpServlet` 的类
    
2. `Servlet` 用来： 
    
    > 接收请求

    > 处理请求
    
    > 返回响应
    
3. 注解式配置

    ```java
    @WebServlet(urlPatterns="/your_pattern")
    ```
    
4. Refactoring 重构

    > 在不改变软件系统外部行为的前提下，改善其内部代码结构