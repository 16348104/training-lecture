# Chapter 5 泛型

> since Java JDK 5

> generic 泛化的，通用的，一般的

1. 类型参数列表
    ```java
    class(interface) 类名（接口名）<类型参数列表 extends 父类型 & 父类型 & ...> {...}
    ```
    
    > 类型参数的命名

        E - Element (used extensively by the Java Collections Framework)
        K - Key
        V - Value
        N - Number
        T - Type
        S,U,V etc. - 2nd, 3rd, 4th types
    
2. 泛型的类
3. 泛型的接口