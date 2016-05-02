---
title: windows下git生成SSH公钥
categories: git
tags: [git, ssh]
---


## 步骤

-   `cd %HOMEPATH%`

-   `mkdir .ssh`

-   `ssh-keygen -t rsa -C "qian_cheng_long@163.com"`

    -   输入生成文件名(`.ssh/rd_rsa`)
    -   2次输入密码(空密码可以方便连接)

-   添加到`ssh-agent`

        ssh-agent -s
        ssh-add ~/.ssh/id_rsa

-   复制到粘贴板

        clip < ~/.ssh/id_rsa.pub

-   将`.ssh/rd_rsa.pub`内容添加到[github](https://github.com/settings/ssh)

-   测试是否添加成功

        ssh -vT git@github.com

## 参考

1.  <https://help.github.com/articles/generating-ssh-keys/>
