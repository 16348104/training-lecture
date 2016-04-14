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

## 集合框架

> The `Java Collections Framework` is a collection of interfaces and classes which helps in storing and processing the data efficiently.

### Main Interfaces
- `Iterable`
- `Collection`
  - `List`
  
  ![List](../image/javase/diagram/List.png)
  
  - `Set`
  
  ![Set](../image/javase/diagram/Set.png)
  
- `Map`

### List

> 有序集合（序列）

> 可重复元素

- `Vector`
  
  ![Vector](../image/javase/diagram/Vector.png)
  
- `ArrayList`
  
  ![ArrayList](../image/javase/diagram/ArrayList.png)
  
- `LinkedList`
  
  ![LinkedList](../image/javase/diagram/LinkedList.png)
  
### Set

> 不可重复元素

- `HashSet`

> 使用 `Hashtable` 存储元素

> 无序

> 效率高
  
  ![HashSet](../image/javase/diagram/HashSet.png)
  
- `LinkedHashSet`

> 使用 `Hashtable` 实现

> 按元素添加顺序排序
  
  ![LinkedHashSet](../image/javase/diagram/LinkedHashSet.png)
  
- `TreeSet`

> 使用 `红-黑 树` 存储元素

> 按元素值排序
  
  ![TreeSet](../image/javase/diagram/TreeSet.png)
  
  
### Map

> `Key - Value` 对结构
  
- `Hashtable`
  
  ![Hashtable](../image/javase/diagram/Hashtable.png)
  
- `HashMap`

> 无序
  
  ![HashMap](../image/javase/diagram/HashMap.png)
  
- `LinkedHashMap`

> 使用 `Hashtable` 实现

> 按元素添加顺序排序
  
  ![LinkedHashMap](../image/javase/diagram/LinkedHashMap.png)
  
- `TreeMap`

> 使用 `红-黑 树` 存储元素

> 按元素值排序
  
  ![TreeMap](../image/javase/diagram/TreeMap.png)
  
- ~~`WeakHashMap`~~
  
  ![WeakHashMap](../image/javase/diagram/WeakHashMap.png)
  
- ~~`IdentityHashMap`~~
  
  ![IdentityHashMap](../image/javase/diagram/IdentityHashMap.png)

### Iterator / ListIterator

- `Iterator`
- `ListIterator`

  ![ListIterator](../image/javase/diagram/ListIterator.png)

### Utils
- `Collections`
- `Arrays`