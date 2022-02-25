#### 准备工作

在初次安装Git时，往往会使用如下的命令配置全局用户名和邮箱：

`git config --global user.name "xxx" // 配置全局用户名，如Github上注册的用户名`
`git config --global user.email "yyy@mail.com" // 配置全局邮箱，如Github上配置的邮箱`

这个`--global`选项，是指这里配置的`user.name`和`user.email`是相对于全局进行配置的，即不同的Git仓库默认的用户名和邮箱都是这个值。由于需要管理多个账户，所以仅仅使用这个全局值是不够的，**需要在每个仓库中单独配置**。

如果之前已经使用该命令进行配置，则先使用如下命令清除

`git config --global --unset user.name`
`git config --global --unset user.email`

如果不确定是否已经配置过，可以使用下面的命令查看

`git config --global user.name`
`git config --global user.email`

#### 配置步骤

首先进入保存秘钥的目录：

`cd ~/.ssh` 

然后，根据账户邮箱生成秘钥：

`ssh-keygen -t rsa -C "2284436468@qq.com"`

