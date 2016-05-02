---
title: sshd添加公钥
categories: [sshd]
tags: [sshd, 公钥]
date: 2015-03-07 14:42:53
---

# 环境

-   centos7

-   OpenSSH_6.4p1, OpenSSL 1.0.1e-fips 11 Feb 2013

# 步骤

-   编辑配置文件`/etc/ssh/sshd_config`

    反注释掉`AuthorizedKeysFile      .ssh/authorized_keys`

        AuthorizedKeysFile      .ssh/authorized_keys

-   编辑登录用户配置文件(`~/.ssh/authorized_keys`)

    添加公钥

-   设置权限

    chmod 700 ~/.ssh
    chmod 600 ~/.ssh/authorized_keys

# 重启sshd

    systemctl restart sshd
