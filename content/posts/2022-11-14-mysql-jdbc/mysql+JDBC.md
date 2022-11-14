---
title: Mysql+JDBC
author: ma
date: '2022-11-14'
slug: mysql+JDBC
categories: []
tags:
  - 大数据
layout: post
math: no
---

#                      **大数据学习之SQL+JDBC总结**

1. ### MySql字段类型

   - 常用的有：数值（int float ）,字符串(varchar,text),日期（date,datetime）.

2. ### MySql约束

   - 主键：primary  key
   - 外键：foreign key
   - 默认值：default
   - 唯一：unique
   - 非空： not null

3. ### 物理删除和逻辑删除

   - 物理删除就是把一条数据从数据库中永久的删除，不能在找到也不能在恢复。
   - 逻辑删除就是在设计的表中添加一列（例如：isdelete，设置默认值为0），当你想删除数据将这个字段设置为1，当在进行数据库操作时筛选数据即可。这样数据也不会丢失。

4. ### 数据库的基本操作（增删改查）

   - 创建数据库：

     CERATE DATABASE [IF NOT EXISTS]  dbname [CHARACTER SET utf8];

   - 查看数据库：

     SHOW DATABASES;

   - 查看数据库创建方式：

     SHOW CREATE DATABASES dbname;

   - 修改数据库编码方式

     ALTER DATABASE db_name [character set utf8]

   - 删除数据库

     DROP DATABASE [IF EXISTS]db_name;

   - 使用数据库

     USE db_name;

   - 查看当前使用数据库

     SELECT DADABASE();

5. ### 数据库管理

   - 通过grant命令，给test数据库，添加用户***，密码123456

     grant select,insert,updata,delete,create,drop on test to '***'@ 'localhost' identified by 'asdfasdf';

   - 修改用户密码

     grant select,insert,update,delete,create,drop on test to '***' @'localhost' identifiled 'asdfasdf';

   - 显示用户

     select user from mysql.user;

   - 删除用户

     drop user '***' @ 'localhost'

   

6. ### 数据表的基本操作

   - 查看数据库

     SHOW TABLES;

   - 创建数据表

     CERATE TABLE [IF NOT EXISTS] TABLE_NAME(

     字段名 数据类型，

     ....

     );

   - 查看表结构

     DESCRIBE TABLE_NAME;

   - 查看创建数据表语句

     SHOW CREATE TABLE TABLE_NAME;

   - 增加数据（列，字段）

     ALTER TABLE TABLE_NAME ADD 字段名 数据类型。

   - 增加多个字段

     ALTER TABLE TABLE_NAME ADD 字段名 数据类型，ADD 字段名 数据类型 约束等；

   - 修改列名

     ALTER TABLE TABLE_ANME CHANGE 字段名 新字段名 数据类型；

   - 修改一列类型

     ALTER TABLE TABLE_NAME MODIFY 字段名 新数据类型；

   - 删除一类

     ALTER TABLE TABLE_NAME DROP 字段名；

   - 修改表名

     RENAME TABLE TABLE_NAME TO 新表名；

   - 修改表所用字符集

     ALTER TABLE TABLE_NAME CHARACTER SET 字符集名；

   - 删除表

     DROP TABLE TABLE_NAME;

   - 添加主键（表已经创建完成）

     ALTER TABLE TABLE_NAEM ADD PROMARY KEY(字段名)；

   - 删除主键

     ​	ALTER TABEL TABEL_NAME DROP PRIMARY KEY;

   - 添加唯一索引

     ALTER TABLE TABLE_NAME ADD UNIQUE(字段名)；

   - 添加唯一索引设置索引名

     ALTER TABLE TABLE TABLE_NAME ADD UNIQUE KEY 索引名（字段名）;

   - 添加联合索引

     ALTER TABLE TABLE_NAME ADD UNIQUE INDEX 索引名（字段名1，字段名2）；

   - 删除索引

     ALTER TABLE TABLE_NAME DROP INDEX 索引字段名；

   - 插入一条数据

     INSERT INTO TABLE_NAME(字段名1，字段名2...) VALUES(值一，值二...)；

   - 插入多天数据

     INSERT INTO TABLE_NAME(字段名1，字段名2...) VALUES(值一，值二...)，(值一，值二...)...；

   - 修改数据

     UPDATE TABLE_NAME SET 字段名=值 WHERE 条件；

   - 数据表中的数据可知直接运算

     UODATE TABLE_NAME SET 数值字段=数值字段+数值；

   - 删除数据

     DELETE FROM TABLE_NAME WHERE 条件；

   - 删除表中的所用数据

     DELETE FROM TABLE_NAME;

   - 清空表中数据

     TRUNCATE TABLE TABLE_NAME;

   - 修改数据表结构

     - alter table  表名：

     - add [column] create_definition [first|after column_name]　//添加新字段

     - add primary key （index_col_name,...）　//添加主码名称

     - alter [column] col_name {set default literal |rop default} //修改字段名称

     - change [column] old_col_name create_definition**　//修改字段名及类型

     - modify [column] create_definition　　//修改字段类型

     - *drop [column] col_name**　　//删除字段

     - drop primary key　//删除主码

     - rename [as] new_tablename　//更改表名

       

7. ### 查询数据

   - SELECT查询
     - 查询所有数据：SELECT * FROM TABLE_ANEM;'
     - 查询其中的几个字段：SELECT 字段名1，字段名2  FROM TABLE_NAME;
     - 过滤表中重复数据：SELECT  DISTINCT 字段名 FROM TABLE_NAME;
     - 给字段或者表起别名： SELECT NAME AS ANAME 或者 （空格+别名）FROM TABLE_NAME;
   - WHERE 过滤查询
     - SELECT 字段名 FROM TABLE_NAME WHRE 过滤条件；
     - 模糊查询：SELECT 字段名 FROM TABLE_NAME WHRE 过滤条件 LIKE "_%";(下滑线可具体表示第几位，百分号表示通配符)
     - 区间表示：
       - 第一种：SELECT 字段名 FROM TABLE_NAME WHRE 字段名>数值 AND 数值<字段名；
       - 第二种：SELECT 字段名 FROM TABLE_NAME WHRE 字段名 in(数值1,数值2);
       - SELECT 字段名 FROM TABLE_NAME WHRE 字段名 BETWEEN 数值1 AND 数值2；

8. ### ORDER BY 排序

   - 升序：ASC,降序：DESC；
   - 语法 SELECT 字段名 FROM TABLE_NAME WHERE 过滤条件 ORDER BY ASC OR DESC;

9. ### GROUP BY 分组查询

   - 通常用法：SELECT 字段名  聚合函数 FROM TABEL_NAME GROUP BY 字段名(为SELECT 后的字段名);

10. ### WHERE 和having 的区别

    首先，明确一点就是能使用where的地方都能使用having；where只能用于分组之前数据的筛选；having只能用于分组之后数据的筛选，而且having中可以使用聚合函数。

11. ### 聚合函数：

    - COUNT（列名）：统计行的个数
      - 统计学生个数： select count(id) from grade;
    - SUM（列名）：统计总量
      - 统计所有js总成绩： select sum(js) as 'js总成绩' from grade;
    - AVG（列名）：平均数
      - 统计所有js平均分： select avg(js) as 'js平均分' from grade;
    - MAX,MIN （最高，最低）

12. ### SQL语句执行顺序

    - from----where----select----group by----having----order by

13. ### limit和正则表达式

    - limit 

      - 查询前三条数据：SELECT * FROM TABLE_NAME LIMIT 3;
      - 跳过1条，查询3条数据： SELECT  * FROM  grade LIMIT 1,3;
      - 分页：SELECT * FROM TABLE_NAME LIMIT (第几页-1*页面数据条数) 页面数据条数

    - 正则表达式

      　　　　查询j开头的学生： select * from grade where name regexp '^j';

      　　　　查询名字中m出现2次的学生： select * from grade where name regexp 'm{2}';

14. ### 多表操作

    - 多表连接：将多张表连在一起进行查询。通过两个表共有的列去进行拼接。多表连接，首先要在表之间建立连接。
      - ​	交叉连接：将一张表的数据与另外一张表中的数据彼此交叉。也就是说把一张表中的每一行逐个与另一张表去进行匹配。没有任何连接条件，所有的记录都会被保留。结果是笛卡尔积，没有实际应用。
        - 用法：SELECT 字段1，字段2 FROM 表1 JOIN 表2
      - 内连接：即最常见的等值连接，指连接结果仅包含符合连接条件的行，参与连接的两个表都应该符合连接条件。
        - 用法：SELECT 字段1，字段2 FROM 表1 JOIN 表2 WHERE 连接（检索条件）
      - 外连接：在查询时所有的表有主从之分。把作为主表的表的行与从表中的行一一进行匹配，如果匹配成功返回到主表中，如果匹配不成功，则仍然保留主表中的行，相应的从表中的行也被填上null值。驱动表（主表），从表（副表），\
        - ​	左外连接：LEFT JOIN ON\n把左表作为主表去连接右表
          - ​	用法：SELECT * FROM 表1 LEFT JOIN 表2 ON条件表达式\n
        - 右外连接：RIGHT JOIN ON把右表作为主表去连接左边的表
          - 用法：SELECT * FROM 表1 RIGHT JOIN 表2 ON 条件表达式
        - 全外连接（经常不用）：即都为主表。左表中未匹配的行仍保留，同时赋给右表NULL值，右表的未匹配的行仍然保留同时赋给左表值NULL
          - 用法：SELECT * FROM 表1 FULL JOIN 表2 ON 条件表达式
        - 自连接：就是两个表的两个副本进行连接，为了区别，对表设置别名

    

    - 外键约束：MySQL 外键约束（FOREIGN KEY）用来在两个表的数据之间建立链接，它可以是一列或者多列。一个表可以有一个或多个外键。
      - 主表（父表）：对于两个具有关联关系的表而言，相关联字段中主键所在的表就是主表。
      - 从表（子表）：对于两个具有关联关系的表而言，相关联字段中外键所在的表就是从表
      - 在创建表时设置外键约束：[CONSTRAINT <外键名>] FOREIGN KEY 字段名 [，字段名2，…] REFERENCES <主表名> 主键列1 [，主键列2，…]
      - 删除外键：ALTER TABLE <表名> DROP FOREIGN KEY <外键约束名>;
    - 多表查询
      - 子查询就是将一个查询的结果作为另一个查询的数据来源或判断条件的查询。
         常见的子查询包括：WHERE子查询，FROM子查询，HAVING子查询，EXISTS子查询，子查询必须使用小括号括起来。

15. ### JDBC

    - JDBC : Java提供的一套用来操作数据库的接口

    - 创建数据库连接对象：

      ```Java
    /*
       1.保证数据库可以正常使用（MySQL服务是否开启了）
      2.保证数据库的账号，密码必须是对的
       3.确定MySQL版本和驱动包的版本是否匹配
      4.将驱动包导入到工程中
      */
      ```
    
    - -数据库连接

      import java.sql.*;
      public class JDBC {
          	public static void main(String[] args) {
      		String driver="com.mysql.cj.jdbc.Driver";//数据库驱动类所对应的字符串
          		String URL="jdbc:mysql://localhost:3306/school?serverTimezone=UTC&useUnicode=true&characterEncoding=utf-8";
                      //URL语法格式如下
          		//jdbc:mysql:是固定的写法，后面跟主机名localhost，3306是默认的MySQL端口号
      		//serverTimezone=UTC是指定时区时间为世界统一时间
          		//useUnicode=true是指是否使用Unicode字符集，赋值为true
      		//characterEncoding=utf-8是指定字符编码格式为UTF8
          		Connection conn=null;
      		//Connection接口代表Java程序和数据库的连接对象，只有获得该连接对象后，才能访问数据库，并操作数据表
          		try {
      			Class.forName(driver);//加载MySQL数据库驱动
          		}catch(java.lang.ClassNotFoundException e) {//如果找不到这个类，执行下面的异常处理
      			System.out.println("驱动程序配置未配置成功!!!");
          		}
      		try {
          			conn=DriverManager.getConnection(URL,"root","123123");//建立和数据库的连接，并返回表示连接的Connection对象
      			System.out.println("数据库连接成功!!!");
          		}catch(Exception e) {//未连接成功，执行下面的异常处理
      			System.out.println("数据库连接失败!!!");
          		}
      	}
          }
  
  ```
    
  
    
    - 抽取工具类和加载properties
    
      ```java
      /*
      抽取的工具类JDBCUtils
      /*
      package com.ma.JDBC;
      
      
      import java.io.FileInputStream;
      import java.io.FileNotFoundException;
      import java.io.IOException;
      import java.sql.Connection;
      import java.sql.DriverManager;
      import java.sql.PreparedStatement;
      import java.sql.SQLException;
      import java.util.Properties;
      
      
      public class JDBCUtils {
          public static String ClassName;
          public static String url;
          public static String userName;
          public static String password;
      
          static {
              FileInputStream p = null;
              try {
                  Properties properties = new Properties();
                  p = new FileInputStream("src/jdbc.properties");
                  properties.load(p);
                  ClassName = properties.getProperty("ClassName");
                  url = properties.getProperty("url");
                  userName = properties.getProperty("userName");
                  password = properties.getProperty("password");
              } catch (FileNotFoundException e) {
                  e.printStackTrace();
              } catch (IOException e) {
                  e.printStackTrace();
              } finally {
                  try {
                      p.close();
                  } catch (IOException e) {
                      e.printStackTrace();
                  }
              }
      
          }
      
          public static Connection connection() throws ClassNotFoundException, SQLException {
              Class.forName(ClassName);
              Connection connection = DriverManager.getConnection(url, userName, password);
              return connection;
          }
      
          public static void close(Connection connection, PreparedStatement preparedStatement) throws SQLException {
              connection.close();
              preparedStatement.close();
          }
      }
      
      /*
      JDBC.properties
      */
      ClassName = com.mysql.jdbc.Driver
      url = jdbc:mysql://192.168.37.101:3306/dbJDBC
      userName = root
      password = 123456
          
      /*
      数据库连接和进行简单操作
      */
      package com.ma.JDBC;
      
      import org.junit.Test;
      
      import java.sql.Connection;
      import java.sql.PreparedStatement;
      import java.sql.SQLException;
      
      public class demo1 {
          @Test
          public void insert() throws SQLException, ClassNotFoundException {
              Connection connection = JDBCUtils.connection(); 
              String sql = "INSERT INTO student(aname,age) value(?,?)";
              PreparedStatement preparedStatement = connection.prepareStatement(sql);//预编译
              preparedStatement.setString(1, "zhangsan");
              preparedStatement.setInt(2, 18);
              int result = preparedStatement.executeUpdate();
              System.out.println(result);
              JDBCUtils.close(connection,preparedStatement);
      
          }
      }
      
  ```


  