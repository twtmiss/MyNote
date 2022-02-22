##### jar包后台运行命令

```
nohup java -jar ruoyi-admin.jar >output 2>&1 &
```

**nphup作用**

使ssh会话关闭也可以保持运行

**>output 2>&1**

保存日志至output文件中
