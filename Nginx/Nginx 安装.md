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

#### Ubuntu安装Nginx

##### 安装命令

`sudo apt install nginx

一旦安装完成，Nginx 将会自动被启动。你可以运行下面的命令来验证它：

`sudo systemctl status nginx`

##### 配置文件所在位置

`/etc/nginx/nginx.conf`

##### Nginx 配置文件结构以及最佳实践

-   所有的 Nginx 配置文件都在`/etc/nginx/`目录下。
-   主要的 Nginx 配置文件是`/etc/nginx/nginx.conf`。
-   为每个域名创建一个独立的配置文件，便于维护服务器。你可以按照需要定义任意多的 block 文件。
-   Nginx 服务器配置文件被储存在`/etc/nginx/sites-available`目录下。在`/etc/nginx/sites-enabled`目录下的配置文件都将被 Nginx 使用。
-   最佳推荐是使用标准的命名方式。例如，如果你的域名是`mydomain.com`，那么配置文件应该被命名为`/etc/nginx/sites-available/mydomain.com.conf`
-   如果你在域名服务器配置块中有可重用的配置段，把这些配置段摘出来，做成一小段可重用的配置。
-   Nginx 日志文件(access.log 和 error.log)定位在`/var/log/nginx/`目录下。推荐为每个服务器配置块，配置一个不同的`access`和`error`。
-   你可以将你的网站根目录设置在任何你想要的地方。最常用的网站根目录位置包括：
	-   `/home/<user_name>/<site_name>`
	-   `/var/www/<site_name>`
	-   `/var/www/html/<site_name>`
	-   `/opt/<site_name>`