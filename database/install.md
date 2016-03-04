# Chapter 2 数据库安装

1.  MySQL

    - upzip to your_mysql_directory/

    - Edit configuration file
    	
      > your_mysql_directory/my-small.ini
      
    		[mysqld]
    		default-character-set=utf8
    		default-storage-engine=innodb
    
    - Install
    	
      > CMD your_mysql_directory/bin
      
    	    mysqld --install your_mysql_service_name --defaults-file=your_mysql_directory\my-small.ini
    	    
    	    (if your_mysql_directory include spaces,use double quotation marks)
    
    - Start or stop MySQL
    
            run > services.msc
        	
        	or:
        	
        	CMD
        	net start your_mysql_service_name
        	net stop your_mysql_service_name
    
    - Delete service
    
    		SC delete your_mysql_service_name
    
    - Update MySQL password
    
      > CMD your_mysql_directory/bin
      
    		mysql -u root -p
    		
    		update mysql.user set password = PASSWORD('your_new_password') where user='root';
    		flush privileges;