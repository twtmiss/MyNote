## CentOS 6.5安装
从redis官网下载最新的redis压缩包
通过scp命令上传到centos 6.5服务器上
使用命令tar解压
进入解压后的目录，使用make命令编译


#### 如果没有安装gcc可能会报错
安装完gcc后，执行命令`make distclean && make`

#### 修改redis.conf配置文件

修改daemonize为yes，以守护进程的方式运行
```
daemonize yes
```

将保护模式`protected-mode` yes改为no **可供远程连接**
将`bind` 127.0.0.1改为 0.0.0.0 或者指定ip **可供远程连接**
通过修改requirepass的值，从而修改redis密码，redis6.2.6版本大概在901行