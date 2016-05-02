---
title: samba搭建
categories: [samba]
tags: [samba, 搭建, 安装]
date: 2015-02-10 10:37:16
---

# 环境

-   CentOS-7.0.1

-   Samba version 4.1.12

# 步骤

-   安装samba

        yum install samba

-   修改配置文件

        cp /etc/samba/smb.conf /etc/samba/smb.conf~
        vi /etc/samba/smb.conf

        [global]
        workgroup = WORKGROUP
        netbios name = xianji-server
        server string = Samba Server Version %v
        security = user
        map to guest = Bad Password
        guest account = guest
        unix extensions  = no
        load printers = no
        log file = /var/log/samba/%m.log
        max log size = 50
        encrypt passwords = true
        passdb backend = tdbsam
        unix password sync = yes
        passwd program = /usr/bin/passwd %u
        passwd chat = *Enter\snew\s*\spassword:* %n\n *Retype\snew\s*\spassword:* %n\n *password\supdated\ssuccessfully* .
        pam password change = yes

        [root]
        path = /
        browseable = no
        writable = yes
        wide links = yes
        guest ok = no

        [share]
        path = /data/share
        guest ok = yes
        read only = no

-   添加samba用户(需要当前已存在用户名)

        pdbedit -a USERNAME

    输入2次密码

-   关闭SELinux

        setenfore 0

-   防火墙放行(445/tcp)

        firewall-cmd --permanent --add-port=445/tcp
        firewall-cmd --reload

-   重启samba服务

        systemctl restart smb
        systemctl restart nmb

# 权限控制

## 以用户的所有权限控制(`security = user`)

根据目录、文件的权限来控制

```
# 添加用户
useradd <username>
pdbedit -a -u <username>(输入相应密码)

# 修改用户名
smbpasswd <usernmae>
```

# 参考

1.  <https://wiki.archlinux.org/index.php/Samba_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>
