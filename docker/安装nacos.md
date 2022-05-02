### 在本机上以单机模式运行nacos

##### 拉取最新的nacos镜像

```
docker pull nacos/nacos-server
```

##### 获取docker宿主机ip

```
ping host.docker.internal
```

##### 创建nacos容器

```
docker run -d \
-p 8848:8848 \
-p 9848:9848 \
-p 9849:9849 \
--env MODE=standalone \
--env SPRING_DATASOURCE_PLATFORM=mysql \
--env MYSQL_SERVICE_HOST=192.168.65.2 \
--env MYSQL_SERVICE_PORT=3306 \
--env MYSQL_SERVICE_DB_NAME=sarnath-config \
--env MYSQL_SERVICE_USER=root \
--env MYSQL_SERVICE_PASSWORD=11111111 \
--restart always --name nacos-sarnath-dsgj nacos/nacos-server:latest
```

- 单机模式模式：MODE=standalone
- 数据库：SPRING_DATASOURCE_PLATFORM=mysql
- 数据库IP：MYSQL_SERVICE_HOST=192.168.65.2
- 数据库端口号：MYSQL_SERVICE_PORT=3306
- 数据库名称：MYSQL_SERVICE_DB_NAME=sarnath-config
- 数据库连接用户名：MYSQL_SERVICE_USER=root
- 数据库连接密码：MYSQL_SERVICE_PASSWORD=11111111