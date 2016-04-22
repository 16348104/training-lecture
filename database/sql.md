# Chapter 3 SQL 语言

## 基础语法

```sql
-- a SQL statement
SELECT * FROM some_table;
```

1. SQL 关键字不区分大小写
2. 分号 `;` 是区分语句的标志
3. MySQL 注释

  ```sql
  SELECT 1+1;     # This comment continues to the end of line
  SELECT 1+1;     -- This comment continues to the end of line
  SELECT 1 /* this is an in-line comment */ + 1;
  SELECT 1+
  /*
  this is a
  multiple-line comment
  */
  1;
  ```

4. 常用的 SQL 语句
  
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

  ```sql
  CREATE DATABASE database_name;
  ```

- SQL 数据类型
 
  > text, number, and Date/Time

  1. Text types
<table>
    <tr>
      <th>Data type</th>
      <th>Description</th>
    </tr>
    <tr>
      <td>CHAR(size)</td>
      <td>Holds a fixed length string (can contain letters, numbers, and special 
	  characters). The fixed size is specified in parenthesis. Can store up to 
	  255 characters</td>
    </tr>
    <tr>
      <td><b>VARCHAR(size)</b></td>
      <td>Holds a variable length string (can contain letters, numbers, and 
	  special characters). The maximum size is specified in parenthesis. Can 
	  store up to 255 characters. <b>Note:</b> If you put a greater value than 
	  255 it will be converted to a TEXT type</td>
    </tr>
    <tr>
      <td>TINYTEXT</td>
      <td>Holds a string with a maximum length of 255 characters</td>
    </tr>
    <tr>
      <td>TEXT</td>
      <td>Holds a string with a maximum length of 65,535 characters</td>
    </tr>
    <tr>
      <td>BLOB</td>
      <td>For BLOBs (Binary Large OBjects). Holds up to 65,535 bytes of data</td>
    </tr>
    <tr>
      <td>MEDIUMTEXT</td>
      <td>Holds a string with a maximum length of 16,777,215 characters</td>
    </tr>
    <tr>
      <td>MEDIUMBLOB</td>
      <td>For BLOBs (Binary Large OBjects). Holds up to 16,777,215 bytes of data</td>
    </tr>
    <tr>
      <td>LONGTEXT</td>
      <td>Holds a string with a maximum length of 4,294,967,295 characters</td>
    </tr>
    <tr>
      <td>LONGBLOB</td>
      <td>For BLOBs (Binary Large OBjects). Holds up to 4,294,967,295 bytes of 
	  data</td>
    </tr>
    <tr>
      <td>ENUM(x,y,z,etc.)</td>
      <td>Let you enter a list of possible values. You can list up to 65535 
	  values in an ENUM list. If a value is inserted that is not in the list, a 
	  blank value will be inserted.<p><b>
		Note:</b> The values are sorted in the order you enter them.</p>
		<p>You enter the possible values in this format: ENUM('X','Y','Z')</td>
    </tr>
	<tr>
      <td>SET</td>
      <td>Similar to ENUM except that SET may contain up to 64 list items and 
	  can store more than one choice</td>
    </tr>
</table>

  2. Number types
<table>
    <tr>
      <th style="width:20%">Data type</th>
      <th>Description</th>
    </tr>
    <tr>
      <td>TINYINT(size)</td>
      <td>-128 to 127 normal. 0 to 255 UNSIGNED*. The maximum number of digits 
	  may be specified in parenthesis</td>
    </tr>
    <tr>
      <td>SMALLINT(size)</td>
      <td>-32768 to 32767 normal. 0 to 65535 UNSIGNED*. The maximum number of 
	  digits may be specified in parenthesis</td>
    </tr>
    <tr>
      <td>MEDIUMINT(size)</td>
      <td>-8388608 to 8388607 normal. 0 to 16777215 UNSIGNED*. The maximum 
	  number of digits may be specified in parenthesis</td>
    </tr>
    <tr>
      <td><b>INT(size)</b></td>
      <td>-2147483648 to 2147483647 normal. 0 to 4294967295 UNSIGNED*. The 
	  maximum number of digits may be specified in parenthesis</td>
    </tr>
    <tr>
      <td>BIGINT(size)</td>
      <td>-9223372036854775808 to 9223372036854775807 normal. 0 to 
	  18446744073709551615 UNSIGNED*. The maximum number of digits may be 
	  specified in parenthesis</td>
    </tr>
    <tr>
      <td>FLOAT(size,d)</td>
      <td>A small number with a floating decimal point. The maximum number of 
	  digits may be specified in the size parameter. The maximum number of 
	  digits to the right of the decimal point is specified in the d parameter</td>
    </tr>
    <tr>
      <td><b>DOUBLE(size,d)</b></td>
      <td>A large number with a floating decimal point. The maximum number of 
	  digits may be specified in the size parameter. The maximum number of 
	  digits to the right of the decimal point is specified in the d parameter</td>
    </tr>
    <tr>
      <td>DECIMAL(size,d)</td>
      <td>A DOUBLE stored as a string , allowing for a fixed decimal point. The 
	  maximum number of digits may be specified in the size parameter. The 
	  maximum number of digits to the right of the decimal point is specified in 
	  the d parameter</td>
    </tr>
</table>

  3. Date types
<table>
    <tr>
      <th>Data type</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><b>DATE()</b></td>
      <td>A date. Format: YYYY-MM-DD<p><b>Note:</b> The supported range is from 
	  '1000-01-01' to '9999-12-31'</p></td>
    </tr>
    <tr>
      <td><b>DATETIME()</b></td>
      <td>*A date and time combination. Format: YYYY-MM-DD HH:MI:SS<p><b>Note:</b> 
	  The supported range is from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'</p></td>
    </tr>
    <tr>
      <td>TIMESTAMP()</td>
      <td>*A timestamp. TIMESTAMP values are stored as the number of seconds 
	  since the Unix epoch ('1970-01-01 00:00:00' UTC). Format: YYYY-MM-DD 
	  HH:MI:SS<p><b>Note:</b> The supported range is from '1970-01-01 00:00:01' 
	  UTC to '2038-01-09 03:14:07' UTC</p></td>
    </tr>
    <tr>
      <td>TIME()</td>
      <td>A time. Format: HH:MI:SS<p><b>Note:</b> The supported range is from 
	  '-838:59:59' to '838:59:59'</p></td>
    </tr>
    <tr>
      <td>YEAR()</td>
      <td>A year in two-digit or four-digit format.<p>
		<b>Note:</b> Values allowed in four-digit format: 1901 to 2155. Values 
		allowed in two-digit format: 70 to 69, representing years from 1970 to 
		2069</p></td>
    </tr>
</table>


- SQL Create Table

  ```sql
  CREATE TABLE table_name (
    column_name1 data_type(size),
    column_name2 data_type(size),
    column_name3 data_type(size),
    ....
  );
```

- SQL Drop

  ```sql
  -- Drop database
  DROP DATABASE database_name;
  -- Drop table
  DROP TABLE table_name;
  -- Drop index in MySQL
  ALTER TABLE table_name DROP INDEX index_name;
  -- Truncate table
  TRUNCATE TABLE table_name;
  ```

- SQL Constraints
  1. 约束创建时间
    - 建表时创建
    
      ```sql
      CREATE TABLE table_name (
        column_name1 data_type(size) constraint_name,
        column_name2 data_type(size) constraint_name,
        column_name3 data_type(size) constraint_name,
        ....
      );
      ```
      
    - 建表后追加 `todo`
  - 非空约束 `Not Null`
  
    ```sql
    CREATE TABLE PersonsNotNull (
      P_Id int NOT NULL,
      LastName varchar(255) NOT NULL,
      FirstName varchar(255),
      Address varchar(255),
      City varchar(255)
    )
    ```
  
  - 唯一约束 `Unique`
  
    ```sql
    CREATE TABLE Persons (
      P_Id int NOT NULL,
      LastName varchar(255) NOT NULL,
      FirstName varchar(255),
      Address varchar(255),
      City varchar(255),
      CONSTRAINT uc_PersonID UNIQUE (P_Id,LastName)
    )
    ```
  
  - 主键约束 `Primary Key`

    ```sql
    CREATE TABLE Persons (
      P_Id int NOT NULL,
      LastName varchar(255) NOT NULL,
      FirstName varchar(255),
      Address varchar(255),
      City varchar(255),
      PRIMARY KEY (P_Id)
    )
    ```

  - SQL Foreign Key
    - 主表 父表（主键所在的表）
    - 从表 子表（外键所在的表）

    ```
    [CONSTRAINT [symbol]] FOREIGN KEY
        [index_name] (index_col_name, ...)
        REFERENCES tbl_name (index_col_name,...)
        [ON DELETE reference_option]
        [ON UPDATE reference_option]

    reference_option:
        RESTRICT | CASCADE | SET NULL | NO ACTION
    ```

  - 缺省值 `Default`
  
    ```sql
    CREATE TABLE Persons (
      P_Id int NOT NULL,
      LastName varchar(255) NOT NULL,
      FirstName varchar(255),
      Address varchar(255),
      City varchar(255) DEFAULT 'Sandnes'
    )
    ```

  - ~~SQL Check~~ `MySQL`
  
    >  The CHECK clause is parsed but ignored by all storage engines.

    > [CHECK constraint in MySQL is not working](http://stackoverflow.com/questions/2115497/check-constraint-in-mysql-is-not-working)
  
- Auto Increment

  ```sql
  CREATE TABLE Persons (
  ID int NOT NULL UNSIGNED AUTO_INCREMENT,
  ...
  PRIMARY KEY (ID)
  )
  ```

  ```sql
  ALTER TABLE Persons AUTO_INCREMENT = 100;
  ```

- Alter    

  ```sql
  ALTER TABLE table_name
  ADD column_name datatype;
  ```

  ```sql
  ALTER TABLE table_name
  DROP COLUMN column_name;
  ```

  ```sql
  ALTER TABLE table_name
  MODIFY COLUMN column_name datatype;
  ```
  
  ```sql
  ALTER TABLE table_name 
  ADD CONSTRAINT primary_key_name PRIMARY KEY(columns);
  ```
  
  ```sql
  ALTER TABLE table_name
  ADD CONSTRAINT
  foreign_key_name
  FOREIGN KEY (columns)
  REFERENCES parent_table(columns)
  ON DELETE action
  ON UPDATE action;
  ```
  
  ```sql
  ALTER TABLE table_name 
  DROP FOREIGN KEY constraint_name;
  ```
  
  ```sql
  ALTER TABLE table_name DROP INDEX unique_column_name;
  ```

- Index

  ```sql
  CREATE INDEX ind_column ON table_name(column);
  ```
  
  ```sql
  DROP INDEX ind_column ON table_name;
  ```
  
  - primary key > index
  - foreign key > index (only for InnoDB)
      > [Does MySQL index foreign key columns automatically?](http://stackoverflow.com/questions/304317/does-mysql-index-foreign-key-columns-automatically)

### DML

> Data Manipulate Language

- Insert

  ```sql
  INSERT INTO table_name
  VALUES (value1,value2,value3,...);
  ```

  ```sql
  INSERT INTO table_name (column1,column2,column3,...)
  VALUES (value1,value2,value3,...);
  ```

- Update

  ```sql
  UPDATE table_name
  SET column1=value1,column2=value2,...
  WHERE some_column=some_value;
  ```

- Delete

  ```sql
  DELETE FROM table_name
  WHERE some_column=some_value;
  ```

  > temporarily disable a foreign key constraint in MySQL

  ```sql
  Try DISABLE KEYS or

  mysql>SET FOREIGN_KEY_CHECKS=0;

  make sure to

  mysql>SET FOREIGN_KEY_CHECKS=1;

  after.
  ```

  > MySQL dupm and import

  - import
  
  ```sql
  mysql> source file_name.sql
  ```
  - dump
  
  ```
  mysqldump -B -u your_mysql_username -p database_name > file_name.sql

  ```

### DQL

> Data Query Language

- MySQL SHOW
  - SHOW DATABASES;
  - SHOW TABLES;
  - SHOW COLUMNS FROM table_name;
  - SHOW VARIABLES;
  - SHOW CREATE TABLE table_name;
  - SHOW CREATE VIEW view_name;
  - SHOW INDEX FROM table_name;

- SQL select

  ```sql
  SELECT column_name,column_name
  FROM table_name;
  ```

- SQL distinct

  ```sql
  SELECT DISTINCT column_name,column_name
  FROM table_name;
  ```

- SQL where

  > 行检索
  
  ```sql
  SELECT column_name,column_name
  FROM table_name
  WHERE column_name operator value;
  ```

- SQL AND & OR

  ```sql
  SELECT * FROM Customers
  WHERE Country='Germany'
  AND City='Berlin';
  ```
  
  ```sql
  SELECT * FROM Customers
  WHERE City='Berlin'
  OR City='München';
  ```
  
  ```sql
  SELECT * FROM Customers
  WHERE Country='Germany'
  AND (City='Berlin' OR City='München');
  ```
  
- SQL Order By

  ```sql
  SELECT column_name, column_name
  FROM table_name
  ORDER BY column_name ASC|DESC, column_name ASC|DESC;
  ```
  
- SQL Top `limit`

  ```sql
  SELECT column_name(s)
  FROM table_name
  LIMIT number;
  ```
  
- SQL Like  

  ```sql
  SELECT column_name(s)
  FROM table_name
  WHERE column_name [NOT] LIKE pattern;
  ```
  
- SQL 通配符 
  - `%`
  - `_`
 
- MySQL RLIKE REGEXP

- SQL In

  ```sql
  SELECT column_name(s)
  FROM table_name
  WHERE column_name [NOT] IN (value1,value2,...);
  ```
  
- SQL Between And

  ```sql
  SELECT column_name(s)
  FROM table_name
  WHERE column_name [NOT] BETWEEN value1 AND value2;
  ```
  
- SQL Aliases

  ```sql
  SELECT column_name [AS] alias_name
  FROM table_name;
  ```
  
  ```sql
  SELECT alias_name.column_name(s)
  FROM table_name [AS] alias_name
  ```
- SQL Nulls

    > `IS [NOT] NULL`
    
- SQL ifnull(,)    
- SQL Join

  > SQL joins are used to combine rows from two or more tables.
 
  > 连接条件 = N - 1

  1. INNER JOIN
  2. LEFT JOIN
  3. RIGHT JOIN
  4. FULL JOIN


- SQL Inner Join

  ```sql
  SELECT column_name(s)
  FROM table1
  [INNER] JOIN table2
  ON table1.column_name=table2.column_name;
  ```
  
- SQL Left Join

  ```sql
  SELECT column_name(s)
  FROM table1
  LEFT [OUTER] JOIN table2
  ON table1.column_name=table2.column_name;
  ```
  
- SQL Right Join

  ```sql
  SELECT column_name(s)
  FROM table1
  RIGHT [OUTER] JOIN table2
  ON table1.column_name=table2.column_name;
  ```
  
- ~~SQL Full Join~~   `union` 
- SQL Union

  ```sql
  SELECT column_name(s) FROM table1
  UNION
  SELECT column_name(s) FROM table2;
  ```
  
  ```sql
  SELECT column_name(s) FROM table1
  UNION ALL
  SELECT column_name(s) FROM table2;
  ```
  
- SQL Create Table Select  

  ```sql
  CREATE TABLE new_table_name
  SELECT * FROM original_table_name;
  ```
- SQL Insert Into Select

  ```sql
  INSERT INTO table2
  (column_name(s))
  SELECT column_name(s)
  FROM table1;
  ```
  
- SQL View

  > 被存储的查询
 
  1. 简单视图 `updatable view`
      - `简单查询` 生成的，可以修改基表的数据
        - 单表查询
        - 没有使用函数，计算
        - 没有使用分组查询
        - 没有使用子查询
        - 没有使用 `DISTINCT`
        - 没有使用 `UNION`
  2. 复杂视图 `read-only view`
      - `复杂查询` 生成的，不可以修改基表的数据
  ```sql
  CREATE [OR REPLACE] VIEW view_name AS
  SELECT column_name(s)
  FROM table_name
  WHERE condition;
  ```
  
  ```sql
  DROP VIEW view_name;
  ```


- 子查询 `Sub Queries`

  > 查询的嵌套


### DTL

  > Data Transaction Language
  
  - 事务的 ACID 特性
    - 原子性（Atomicity）
    - 一致性（Consistency）
    - 隔离性（Isolation）
    - 持久性（Durability）
  - 开启一次事务
    - START TRANSACTION; # 
  - 事务处理语句
    - DML 语句 `insert` `update` `delete`
    - DQL 语句与事务无关
  - 显式结束事务
    - COMMIT; # 提交 
    - ROLLBACK; # 回滚
  - 隐式结束事务
    - DDL 语句

  - 事务保留点
  
  ```sql
  SAVEPOINT save_point_name; # 设置保留点
  ROLLBACK TO save_point_name; # 回滚到保留点，不能结束事务
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
