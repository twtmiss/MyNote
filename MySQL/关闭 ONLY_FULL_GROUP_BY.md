### Mac系统MySQL8.0关闭 ONLY_FULL_GROUP_BY

> 系统配置
> 
> macOS Big Sur 11.6
> 
> MySQL 8.0.23

#### 1. 登入mysql查看sql_mode
登录后执行命令
```
SELECT @@GLOBAL.sql_mode;
```
![[Pasted image 20220316181421.png]]
将查到的值复制，并删除掉`ONLY_FULL_GROUP_BY,`
```
原先：
ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION

删除后：
STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION
```

#### 1. 首先查看MySQL所使用的配置文件
- 执行命令```mysql --help|grep 'my.cnf'```，使用的配置文件应该是```/etc/my.cnf```，对此配置文件进行编辑。

```
STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION 
```

	![[Pasted image 20211019150406.png]]

#### 2.编辑配置文件

- ```sudo vim /etc/my.cnf```，按 **i** 进行编辑
- 输入以下内容
	```     
	[mysqld]
	sql_mode = 'STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION'
	```
- 按下 **:** ，输入wq，保存并且退出	

#### 3. 重启MySQL服务
```      
 sudo /usr/local/mysql-8.0.23-macos10.15-x86_64/support-files/mysql.server restart
 ```

