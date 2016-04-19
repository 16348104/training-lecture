# Chapter 3 SQL 语言

## 基础语法

```sql
SELECT * FROM some_table;
```

1. SQL 关键字不区分大小写
2. `;` 分号是区分语句的标志
3. 常用的 SQL 语句
  
  ```sql
  SELECT - extracts data from a database
  UPDATE - updates data in a database
  DELETE - deletes data from a database
  INSERT INTO - inserts new data into a database
  CREATE DATABASE - creates a new database
  ALTER DATABASE - modifies a database
  CREATE TABLE - creates a new table
  ALTER TABLE - modifies a table
  DROP TABLE - deletes a table
  CREATE INDEX - creates an index (search key)
  DROP INDEX - deletes an index
  ```

## SQL 语句
### DDL

> Data Defination Language

- SQL Create DB
- SQL 数据类型
- SQL Create Table
- SQL Drop
- SQL Constraints
    - SQL Not Null
    - SQL Unique
    - SQL Primary Key

          id  int(11) UNSIGNED AUTO_INCREMENT PRIMARY KEY ,        

    - SQL Foreign Key
        - 主表 父表（主键所在的表） / 从表 子表（外键所在的表）

        ```
        [CONSTRAINT [symbol]] FOREIGN KEY
            [index_name] (index_col_name, ...)
            REFERENCES tbl_name (index_col_name,...)
            [ON DELETE reference_option]
            [ON UPDATE reference_option]

        reference_option:
            RESTRICT | CASCADE | SET NULL | NO ACTION
        ```

    - ~~SQL Check~~ `MySQL`
    - SQL Default
- SQL Increment
- SQL Alter    
- SQL Create Index

```sql
CREATE INDEX ind_test ON demo.table_test (test);
SHOW INDEX FROM demo.table_test;
DROP INDEX ind_test ON demo.table_test;
```

### DML

  > Data Manipulate Language

  - SQL insert
  - SQL update
  - SQL delete

  > temporarily disable a foreign key constraint in MySQL

  ```sql
  Try DISABLE KEYS or

  mysql>SET FOREIGN_KEY_CHECKS=0;

  make sure to

  mysql>SET FOREIGN_KEY_CHECKS=1;

  after.
  ```

  > MySQL dupm and import

  ```sql
  dump:
  mysqldump -u user -p database_name > file_name.sql

  import:
  mysql>source file_name.sql
  ```

### DQL

  > Data Query Language

  - SQL select
  - SQL distinct
  - SQL where

  > 行检索

  - SQL AND & OR
  - SQL Order By
  - SQL Top `limit`
  - SQL Like  
  - SQL 通配符 `%` `_`
  - SQL In
  - SQL Between And
  - SQL Aliases
  - SQL Nulls
      - `is null / is not null`
  - SQL ifnull(,)    
  - SQL Join
  - SQL Inner Join
  - SQL Left Join
  - SQL Right Join
  - ~~SQL Full Join~~   `union` 
  - SQL Union
  - SQL Select Into    
  - SQL View

  > 被存储的查询

  ```sql
  CREATE [OR REPLACE] VIEW v_test
    [AS]
  SELECT * FROM test;
  ```
  ```sql
  show tables;

  show create view scott.v_test;
  ```

  - 子查询

  > 查询的嵌套

  1. 简单视图
      - 『简单查询』生成的，可以修改基表的数据
  2. 复杂视图
      - 『复杂查询』生成的，不可以修改基表的数据

### DTL

  > Data Transaction Language 事务处理

  > ACID

  - 原子性（Atomicity）
  - 一致性（Consistency）
  - 隔离性（Isolation）
  - 持久性（Durability）

  ```sql
  START TRANSACTION; # 开启一次事务

  DML... 

  COMMIT; # 提交
  ROLLBACK; # 回滚
  DDL 隐式结束事务

  SAVEPOINT save_point_name; # 设置保留点
  ROLLBACK TO save_point_name; # 回滚到保留点
  ```

### SQL 函数

  - aggregate 聚合函数
      - SQL max()
      - SQL min()
      - SQL avg()
      - SQL sum()
      - SQL count()
      - ~~SQL first()~~
      - ~~SQL last()~~
      - **SQL Group By**

      > GROUP BY cloumn_name

      > 把 column_name 列值相同的分为一组

      - **SQL Having**

      > 组检索

  - 标量函数 
      - SQL Date
      - SQL ucase()
      - SQL lcase()
      - SQL mid()
      - SQL len()
      - SQL round()
      - SQL now()
      - SQL format()
