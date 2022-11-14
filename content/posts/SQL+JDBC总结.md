#                      大数据学习之SQL+JDBC总结

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

   

6. 

7. 

8. 

9. 

10. 

11. 

12. 

13. 

14. 

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    