目录
=====
[命令总结](#命令总结)

[常用技巧](#常用技巧)

[与PHP结合](#与PHP结合)

##命令总结
    环境：windows 7, xampp ,phpstrom
* 在mysql文件夹下 `shift+单击` 可以直接打开该目录下命令行； 
* `mysql -u root -p` 最高权限；
* 数据库操作
  * `show databases;` 不要忘记“ ; ”, 显示所有数据库（权限内）；
  * `use databasename;` 选择数据库；
  * `show tables;` 显示表；
* `mysql -u root -p `


##常用技巧
*   
```MYSQL
DROP DATABASES IF EXISTS `databasename`;
```
  NOTE: 在建数据库或建表之前执行；
*   `AUTO_INCREMENT` `NOT NULL` `PRIMARY KEY` `DEFAULT '默认值'` 
*   缓冲和无缓冲查询

##与PHP结合
        NOTE：使用错误处理机制；
*   （面向对象）连接：`$conn = mysqli_connect("localhost", "root", "password", "databasename");`

       `mysqli_connect_error()`;
*   查询：`mysqli_query($conn, $sql, "模式(缓冲/无缓冲)")`，返回结果集对象；

       `mysqli_error()`;
       
       `$row = $result->fetch_row()`;
       
       MYSQLI_USE_RESULT:无缓冲参数；   
 *   多重查询：`$conn->multi_query($query)`，多个sql语句用分号隔开；      
 *   获取模式
     *   枚举数组：`mysqli_fetch_row($result)`
     *   联合数组：`mysqli_fetchi_assoc($result)`
     *   对象：`mysqli_fetch_object($result)`
 *   预备语句（更安全、性能更好、更简便），可以把php变量直接绑定到数据库输入和输出。
     *  数据处理
     *  数据取回

 
       
