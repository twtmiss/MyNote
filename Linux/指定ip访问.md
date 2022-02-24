#### Ubuntu系统

一、拒绝所有IP访问27701端口

`sudo iptables -I INPUT -p tcp --dport 27701-j DROP`

二、允许某个IP访问27701端口

`sudo iptables -I INPUT -s 192.168.9.1 -p tcp --dport 18080 -j ACCEPT`

三、查看规则

`sudo iptables -L -n`

![[Pasted image 20220224134631.png]]

删除iptables 策略的命令

`iptables -D INPUT num`

num 是 使用命令查看出来的数值

`iptables -L -n --line-numbers`

![[Pasted image 20220224140051.png]]