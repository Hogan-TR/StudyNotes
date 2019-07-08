1. 创建root用户的密码
```
[root@host]# mysqladmin -u root password "new_password"
``` 
2. 连接到Mysql服务器/登陆
```
[root@host]# mysql -h 主机名 -u 用户名 -p
Enter password:*******
本地登陆:
mysql -u root -p
Enter password:*******
```
3. Linux启动时启动Mysql,在 /etc/rc.local 文件中添加以下命令:
```
/etc/init.d/mysqld start  # 同时要将mysqld文件添加到/etc/init.d/目录中
```
4. 检查MySQL服务器是否启动
```
ps -ef | grep mysqld
```
5. 查看MySQL运行状态
```
systemctl status mysqld
```
6. 启动MySQL服务器
```
root@host# cd /usr/bin
./safe_mysqld &
或：
systemctl start mysqld
```
7. 关闭目前运行的MySQL服务器
```
root@host# cd /usr/bin
./mysqladmin -u root -p shutdown
Enter password: ******
```
8. 管理MySQL常用命令
```
SHOW DATABASES;			# 列出数据库列表
SHOW TABLES;			# 显示指定数据库的所有表,使用前需使用use命令来选择要操作的数据库


```
