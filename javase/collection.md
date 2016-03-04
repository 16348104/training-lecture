# Chapter 4 集合

> `集合` 或 `容器` 是 Java 中存放数据的重要数据结构

> 要掌握不同集合类型的 `CRUD` `Create Retrieve Update Delete` 操作和时空复杂度

1. 数组
    - 同一种类型的值的集合
    - 数组是静态的
    
    > 数组初始化之后，元素的个数不变

    - 声明和初始化
    ```java
    数据类型[] 数组名 = new 数据类型[元素的个数];// {元素1, 元素2, ... };
    ```
    - 下标（索引） `index`
    - 二维数组
        
        > 注意每行列数不同的二维数组
        
    - 多维数组
    - 数组循环时，推荐使用 `length`
    
2. 字符串 `java.lang.String`
    
    > 字符串初始化后，其值不能改变

    - `String` 的重要方法
        - 构造方法
        - charAt
        - concact
        - contains
        - endsWith
        - equals
        - equalsIgnoreCase
        - format
        - getBytes
        - indexOf
        - isEmpty
        - lastIndexOf
        - length
        - matches
        - replace
        - replaceAll
        - replaceFirst
        - split
        - startWith
        - subString
        - toCharArray
        - toLowerCase
        - toUpperCase
        - valueOf
    - 字符串缓冲区 `java.lang.StringBuffer`
        - append
        - delete
        - insert
        - reverse
    - `StringBuilder`
3. 向量 `java.util.Vector`
    - `Vector` 的重要方法
        - add
        - get
        - size
        - clear
4. 哈希表 `java.util.Hashtable`
    - `Hashtable` 中 `key` 是唯一的
    - `for-each` 循环 `iter + Tab`
    - `Hashtable` 的重要方法
        - put
        - get
        - size
        - clear
        - keySet
5. *`集合框架`*