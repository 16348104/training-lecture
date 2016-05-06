# Annotation

## 元注解
1. `@Target`
  
  > 用来说明注解所修饰的对象

  - `ElementType` enum
    - `CONSTRUCTOR` 用于描述构造器
    - `FIELD` 用于描述域
    - `LOCAL_VARIABLE` 用于描述局部变量
    - `METHOD` 用于描述方法
    - `PACKAGE` 用于描述包
    - `PARAMETER` 用于描述参数
    - `TYPE` 用于描述类、接口、注解类型、enum声明

2. `@Retention`

  > 在什么级别保存该注释信息，用于描述注解的生命周期
  
  - `RetentionPoicy` enum
    - SOURCE:在源文件中有效（即源文件保留）
    - CLASS:在class文件中有效（即class保留）
    - RUNTIME:在运行时有效（即运行时保留）