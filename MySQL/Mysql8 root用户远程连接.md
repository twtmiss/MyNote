
#### 1. 首先本地登录进mysql
```
mysql -uroot -p
```

#### 2.使用mysql数据库
```
use mysql;
```

#### 3.查看user和host
执行以下命令看到root用户的host为`localhost`，要把这个修改为`%`
```
select host,user,plugin from user;
```
![[Pasted image 20220316182403.png]]

#### 4.修改root用户的host
执行以下命令修改
```
update user set host='%' where user ='root';
```
修改完成后再查看一下修改结果
![[Pasted image 20220316182543.png]]

