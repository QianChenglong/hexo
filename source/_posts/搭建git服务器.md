---
title: 搭建git服务器
categories: [git]
tags: [git]
date: 2015-06-06 16:32:14
---

# 环境

-   CentOS-7.0.1

# 前提

-   安装启动sshd

# 步骤

1.  安装git

        yum install git

1.  创建git目录

        mkdir /data/git

1.  添加git用户

        adduser git

1.  设置登录shell

        vi /etc/passwd

        git:x:1008:1009::/home/git:/user/sbin/nologin


1.  用户认证

    -   密码方式

            passwd git

    -   将需要登录git的用户公钥添加进来(一个一行)

            vi /home/git/.ssh/authorized_keys

# 创建仓库

-   初始化仓库

        cd /data/git
        git init --bare sample.git

-   设置权限

        chown -R git:git sample.git

# 客户端配置

-   添加远程仓库

        git remote add web git@hostname:/data/sample.git

-   提交到远程仓库

        git push origin master

# 参考

1.  <http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137583770360579bc4b458f044ce7afed3df579123eca000>
