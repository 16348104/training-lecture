# Chapter 2 数据库安装 / 设置

> MySQL (mysql-5.6.27-win32.zip)

1. upzip zip file to your_mysql_directory/

2. Edit configuration file
	
    > your_mysql_directory/my.ini (rename my-default.ini to my.ini )

    ```
    [client]
    default-character-set=utf8
    
    [mysql]
    default-character-set=utf8
    
    [mysqld]
    collation-server = utf8_unicode_ci
    init-connect='SET NAMES utf8'
    character-set-server = utf8
    default-storage-engine = innodb
    ```

3. Install
	
    > CMD your_mysql_directory/bin
  
    ```sql
    mysqld --install your_mysql_service_name --defaults-file=your_mysql_directory\my.ini
    
    (if your_mysql_directory include spaces,use double quotation marks)
    ```

4. Start / stop MySQL

    ```
    run > services.msc
	
	or:
	
	CMD
	net start your_mysql_service_name
	net stop your_mysql_service_name
	```

5. Update MySQL password

  > CMD your_mysql_directory/bin
    
    ```sql
    mysql -u root -p
    
    update mysql.user set password = PASSWORD('your_new_password') where user='root';
    flush privileges;
    ```
	
6. Check configuration
  
    ```sql    
    mysql> show variables like 'char%';
    mysql> show variables like 'coll%';
    ```

7. Delete service

    ```
    SC delete your_mysql_service_name
    ```

7. dump data
     
  > CMD your_mysql_directory/bin

    ```sql
    mysqldump -u root -p database > your_dump_file_name.sql
    
    ```
    
8. import data

    ```sql
    mysql> source your_dump_file_name.sql
    ```