* `MySQL` 登录参数
    * `-D, --database=name` 打开指定数据库
    * `--delimiter = name` 指定分隔符
    * `-h, --host=name` 服务器名称
    * `-p, --password[=name]` 密码
    * `-P, --port=#` 端口号
    * `--prompt=name` 设置提示符
    * `-u, --user=name` 用户名
    * `-V, --version` 版本信息
* `MySQL` 退出 
    * `exit`
    * `quit`
    * `\q`
* 修改 `MySQL` 提示符
    * 建立连接时指定 `mysql -uroot -proot --prompt \u@\h \d`
    * 连接成功后指定 `prompt \u@\h \d`
    * 参数
        * `\D` 完整的日期
        * `\d` 当前数据库
        * `\h` 服务器名称
        * `\u` 当前用户
* `MySQL` 常用命令
    * `SELECT VERSION();` 显示当前服务器版本
    * `SELECT NOW();` 显示当前日期时间
    * `SELECT USER();` 显示当前用户
    * `SHOW WARNINGS;` 显示警告信息
    * `SHOW {DATABASE | SCHEMAS} [LIKE 'pattern' | WHERE expr];` 查看当前服务器下的数据库列表
    * `SHOW CREATE DATABASE db_name;` 显示创建数据库时使用的指令
    * `SHOW DATABASES;` 显示现有的数据库
    * `USE 数据库名称;` 打开数据库
    * `SELECT DATABASE();` 显示当前打开的数据库
    * `SHOW TABLES [FROM db_name] [LIKE 'pattern' | WHERE expr];` 查看数据库中的数据表
    * `SHOW INDEX FROM table_name\G;` 查看表中的索引 `\G` 指定查看方式
* `MySQL` 语句规范
    * 关键字与函数名称全部大写
    * 数据库名称、表名称、字段名称全部小写
    * `SQL` 语句必须以分号结尾
* 数据库操作语句
    * 创建数据库 `CREATE {DATABASE | SCHEMA} [IF NOT EXISTS] db_name [DEFAULT] CHARACTER SET [=] charset_name;`
    * 修改数据库 `ALTER {DATABASE | SCHEMA} [db_name] [DEFAULT] CHARACTER SET [=] charset_name;`
    * 删除数据库 `DROP {DATABASE | SCHEMA} [IF EXISTS] db_name;`
* `MySQL` 数据类型
    * 整形
        * `TINTINT` `0~255 或 -128~127 1字节`
        * `SMALLINT` `0~65535 或 -32768~32767 2字节`
        * `MEDIUMINT` `0~16777215 或 -8388608~8388607 3字节`
        * `INT` `0~4294967295 或 -2147483648~2147483647 4字节`
        * `BIGINT` `反正够用了 8字节`
    * 浮点型
        * `FLOAT[(M,D)]` `M 代表数字总位数 , D 代表小数点后位数`
        * `DOUBLE[(M,D)]` `同上`
    * 日期时间
        * `YEAR` 
        * `TIME` 
        * `DATE` 
        * `DATETIME` 
        * `TIMESTAMP` 
    * 字符
        * `CHAR(M)` `M个字符 0<=M<=255`
        * `VARCHAR(M)` `L+1个字符 其中 L<=M 且 0<=M<=65535`
        * `TINYTEXT`
        * `TEXT`
        * `MEDIUMTEXT`
        * `LONGTEXT`
        * `ENUM(v1,v2)`
        * `SET(v1,v2)`
* 数据表基本操作语句
    * 创建数据表 `CREATE TABLE [IF NOT EXISTS] table_name (column_name data_type , ...);`
    * 查看数据表 `SHOW COLUMNS FROM table_name;`
    * 修改数据表 `ALTER TABLE table_name ADD [COLUMN] column_name column_definition [FIRSR | AFTER column_name];`
    * 删除列 `ALTER TABLE table_name DROP column_name;`
    * 插入记录 `INSERT [INTO] table_name [(column_name,...)] VALUES(val,...);`
    * 查找记录 `SELECT EXPR,... FROM table_name;`
    * 更新记录 `UPDATE table_name SET column_name = val , ... [WHERE condition];`
    * 删除记录 `DELETE FROM table_name [WHERE condition];`
* 约束条件
    * `PRIMARY KEY` 主键约束
    * `UNIQUE KEY` 唯一约束
    * `DEFAULT` 默认约束
    * `NOT NULL` 非空约束
    * `FOREIGN KEY` 外键约束
        * `CASCADE` 父表删除或更新自动删除或更新子表匹配的行
        * `SET NULL` 父表删除则更新子表匹配的值为 `NULL`
        * `RESTRICT` 拒绝对父表的删除或更新操作
        * `NO ACTION` 同上
* 查询语句
    * 基本结构 `SELECT select_expr ... FROM table_name [WHERE where_condition] [GROUP BY {colo_name | position} [ASC | DESC], ...] [HAVING where_condition] [ORDER BY {col_name | expr | position} [ASC | DESC], ...] [LIMIT {[offset,] row_count | row_count OFFSET offset}]`
    * 子查询 
        * 由比较运算符引发的子查询
        * 由 `[NOT] IN/EXISTS` 引发的子查询
    * 查询插入 `INSERT [INTO] table_name(col_name,...) SELECT col_name FROM table_name WHERE expr;`
    * 连接类型
        * `INNER JOIN` 内连接 仅显示符合连接条件的记录 相当于 `JOIN` 和 `CROSS JOIN`
        * `LEFT [OUTER] JOIN` 左外连接 显示左表的全部记录及右表符合连接记录的条件
        * `RIGHT [OUTER] JOIN` 右外连接 显示右表的全部记录及左表符合连接记录的条件
    * 查询创建 `CREATE TABLE [IF NOT EXISTS] table_name [create_definition,...] select_statement`
* 运算符和函数
    * 字符函数
        * `CONCAT()` 字符连接
        * `CONCAT_WS()` 使用指定的分隔符进行字符连接
        * `FORMAT()` 数字格式化
        * `LOWER()` 转换成小写字母
        * `UPPER()` 转换成大写字母
        * `LEFT()` 获取左边字符
        * `RIGHT()` 获取右边字符
        * `LENGTH()` 获取字符串长度
        * `LTRIM()` 删除前导空格
        * `RTRIM()` 删除后续空格
        * `TRIM()` 删除前导和后续空格
        * `SUBSTRING()` 字符串截取
        * `[NOT] LINK` 模式匹配
        * `REPLACE()` 字符串替换
    * 数值运算符与函数
        * `CEIL()` 进一取整
        * `DIV` 整数除法
        * `FLOOR()` 舍一取整
        * `MOD` 取余数
        * `POWER()` 幂运算
        * `ROUND()` 四舍五入
        * `TRUNCATE()` 数值截取
    * 比较运算符与函数
        * `[NOT] BETWEEN...AND...` [不]在范围之内
        * `[NOT] IN()` [不]在列出值范围内
        * `IS [NOT] NULL` [不]为空
    * 日期时间函数
        * `NOW()` 当前日期和时间
        * `CURDATE()` 当前日期
        * `CURTIME()` 当前时间
        * `DATE_ADD()` 日期变化
        * `DATE_DIFF()` 日期差值
        * `DATE_FORMAT()` 日期格式化
    * 信息函数
        * `CONNECTION_ID()` 连接ID
        * `DATEBASE()` 当前数据库
        * `LAST_INSERT_ID()` 最后插入记录的ID号
        * `USER()` 当前用户
        * `VERSION()` 版本信息
    * 聚合函数
        * `AVG()` 平均值
        * `COUNT()` 计数
        * `MAX()` 最大值
        * `MIN()` 最小值
        * `SUM()` 求和
    * 加密函数
        * `MD5()` 信息摘要算法
        * `PASSWORD()` 密码算法
* 自定义函数
    * 创建自定义函数 `CREATE FUNCTION function_name RETURNS {STRING | INTEGER | REAL | DECIMAL} routine_body`
    * 删除函数 `DROP FUNCTION [IF EXISTS] function_name`
* 存储过程
    * 优点
        * 增强 SQL 语句的功能和灵活性
        * 实现较快的执行速度
        * 减少网络流量
    * 创建存储过程 `CREATE [DEFINER = {user | CURRENT_USER}] PROCEDURE sp_name ([proc_parameter[,...]]) [characteristic ...] routine_body` (`proc_parameter: [IN | OUT | INOUT] param_name type`) 
        * `IN` 该参数的值必须在调用存储过程时指定
        * `OUT` 该参数的值可以被存储过程改变，并且可以返回
        * `INOUT` 该参数的值在调用时指定，并且可以被改变和返回
    * 删除存储过程 `DROP PROCEDURE [IF EXISTS] sp_name`
* 存储过程与自定义函数的区别
    * 存储过程实现的功能要复杂一些；而函数的针对性更强
    * 存储过程可以返回多个值；函数只能有一个返回值
    * 存储过程一般独立的来执行；而函数可以作为其他SQL语句的组成部分来出现
* 存储引擎
    * `MyISAM`
    * `InnoDB`
    * `Memory`
    * `CSV`
    * `Archive`
* 设置存储引擎
    * 修改配置文件 `default-storage-engine = engine`
    * 创建或修改表时指定 `CREATE TABLE table_name (...) ENGINE = engine;`
