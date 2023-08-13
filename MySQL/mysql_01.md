# SQL分类
SQL语言在功能上:
**DDL**（Data Definition Languages, 数据定义语言）：定义了不同的数据库、表、视图、索引等数据库对象，还可以用来创建、删除、修改数据库和数据表的结构。主要的语句关键字包括 CREATE 、 DROP 、 ALTER 等。
**DML**（Data Manipulation Language, 数据操作语言）：用于添加、删除、更新和查询数据库记录，并检查数据完整性。主要的语句关键字包括 INSERT 、 DELETE 、 UPDATE 、 SELECT 等。SELECT是SQL语言的基础，最为重要。
**DCL**（Data Control Language、数据控制语言）：用于定义数据库、表、字段、用户的访问权限和安全级别。主要的语句关键字包括 GRANT 、 REVOKE 、 COMMIT 、 ROLLBACK 、 SAVEPOINT 等。
因为查询语句使用的非常的频繁，所以很多人把查询语句单拎出来一类：DQL（数据查询语言）。
还有单独将 COMMIT 、 ROLLBACK 取出来称为TCL （Transaction Control Language, 事务控制语言）。


# 第12章
P59
浮点类型存在损失，小数很长的时候会出现四舍五入的情况。
推荐使用定点数类型decimal。

关于属性：CHARACTER SET name
1.创建数据库时指明字符集
create database if not exists dbtest12 CHARACTER SET 'utf8';
show create database dbtest12;
2.创建表的时候，指明表的字符集
create table temp(
id INT
) CHARACTER SET 'utf8';
show create table temp;
3.创建表，指明表中的字段时，可以指定字段的字符集
create table temp1(
id INT,
name varchar(15) CHARACTER SET 'utf8'
);
show create table temp1;
字段没有声明，那就按照你表声明时的字符集；表没有声明的话，那就按你表所在的数据库的字符集；数据库也没声明，那就再往上，就到了my.ini配置文件内，配置文件里用的什么字符集那就是什么字符集。
查看：show variables like 'character_%';

# 第13章
P66
添加约束：
1.create table时添加约束
2.alter table时增加约束、删除约束
增加约束:alter table test1 modify email varchar(25) not null;
删除约束:alter table test1 modify email varchar(25) null;
P68
unique唯一性约束允许列值为空，并且允许多次添加NULL值
