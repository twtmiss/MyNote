#### 配置Vue 

>例：配置项目文件夹名称为 rixin

**1. 配置/router/index.js**

修改Router方法下的参数：

- mode 修改为 `history`
- base(如果没有，新增该参数) 修改为`/rixin`

```js
export default new Router({  
  mode: 'history', // 去掉url中的#  
  base: '/rixin',  
  scrollBehavior: () => ({ y: 0 }),  
  routes: constantRoutes  
})
```

**2. 配置vue.config.js**

publicPath需要改为`"production"？"/你的文件夹名称/":"/"`

```js
publicPath: process.env.NODE_ENV === "production" ? "/rixin" : "/",
```

#### Nginx配置

**1. 修改nginx.conf文件**

解决刷新404问题：`try_files $uri $uri/ /rixin/index.html;`

```
location /rixin {

	alias /Users/twtmiss/otherFiles/nginx_static/rixin/;

	try_files $uri $uri/ /rixin/index.html;

	index index.html;

}
```

**2.后端请求转发**

`proxy_pass`：配置后端的ip和端口

```
location /prod-api/ {

	proxy_set_header Host $http_host;

	proxy_set_header X-Real-IP $remote_addr;

	proxy_set_header REMOTE-HOST $remote_addr;

	proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

	proxy_pass http://192.168.9.210:28081/;

}
```