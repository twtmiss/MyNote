### TDengine
官网教程
https://www.taosdata.com/docs/cn/v2.0/getting-started/docker

**拉取镜像**
```
docker pull tdengine/tdengine
```

**运行**
```
docker run -d -p 6030-6049:6030-6049 -p 6030-6049:6030-6049/udp tdengine/tdengine
```