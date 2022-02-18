
#### MacOS安装Nginx

使用homebrew安装

```
brew install nginx
```

Nginx安装后所在位置：`/usr/local/etc/nginx`      

##### 启动

`brew services start nginx`

##### 停止

`brew services stop nginx`

##### 重启nginx

`brew services restart nginx`

##### 重新加载配置文件

`nginx -s reload`

##### 验证nginx配置文件是否正确

`nginx -t`

##### 配置文件位置

`/usr/local/etc/nginx/nginx.conf`