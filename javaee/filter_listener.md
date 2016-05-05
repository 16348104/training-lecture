# Chapter 5 Filter & Listener

1. `Filter`
    - 过滤器
    - `javax.servlet.Filter`
    - 注解式配置
        
        ```java
        @WebFilter(
            urlPatterns="your_pattern", 
            initParams=@WebInitParam=(name="your_key", value="your_value"))
        ```
    - 统一编码过滤器

     ```java
     public class EncodingFilter extends Filter {
     
     }
     ```
     
2. `Listener`
    - 监听器
    - 注解式配置
        
        ```java
        @WebListener
        ```
        
    - `request` 相关监听器接口
        1. ServletRequestListener
        2. ServletRequestAttributeListener
    - `session` 相关监听器接口
        1. HttpSessionListener
        2. HttpSessionActivationListener
        3. HttpSessionAttributeListener
        4. HttpSessionBindingListener
        5. HttpSessionIdListener
    - `application` 相关监听器接口
        1. ServletContextListener
        2. ServletContextAttributeListener