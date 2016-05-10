# Serializable 序列化和反序列化

1. `java.io.Serializable` `标识接口`
  - 类通过实现 `java.io.Serializable` 接口以启用其序列化功能
  - 未实现此接口的类将无法使其任何状态序列化或反序列化
  - 可序列化类的所有子类型本身都是可序列化的
  - 序列化接口没有方法或字段，仅用于标识可序列化的语义
2. `java.io.ObjectOutputStream` 类
  - 将 `Java` 对象写入 `OutputStream`
    
    ```java
    ```
  
3. `java.io.ObjectInputStream` 类
  - 重构 `Java` 对象

    ```java
    ```
