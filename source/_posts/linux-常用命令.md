---
title: linux-常用命令
categories: [linux]
tags: [linux, 命令]
date: 2015-02-09 11:20:50
---

# 系统

-   修改时区

        ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

-   查看或设置用户限制

        ulimit -a

-   查看系统配置参数

        getconf -a

# 磁盘

-   查看磁盘使用情况

        df

-   查看分区类型

        df -T

-   查看分区UUID，label等

        blkid

-   检查并自动修复磁盘错误

        fsck -a /dev/sda1

-   重新读取fstab

        mount -a

# 压缩包

-   解压tar包

        tar xvf XXX.tar

-   解压tar.gz

         tar xvzf XXX.tar.gz

# 文件

-   重命名文件、目录

        mv SRC DST

-   查看目录使用情况

        du

-   实时查看文件

        tail -f filename

-   复制，若父目录不存在则创建

        cp src/a.txt /data/ ==> /data/src/a.txt

# 账号

-   添加用户

        useradd -m <username>

-   设置密码

        passwd <username>

-   查看用户基本信息

        id USERNAME

-   查看用户所属组

        groups USERNAME
        lid <username>

-   查看组成员

        lid -g <group-name>

-   用户添加附加组

        usermod -a -G GROUPNAME USERNAME

-   查看动态库加载

        ldd ./dbgateway_svc 

# 进程管理

-   批量删除进程

        pkill <pattern>

-   根据端口杀进程

        fuser -k 12000/tcp

-   查看进程树

        pstree -apls PID

-   查看进程打开的文件

        lsof -p 18661

# 其他

-   选择默认编辑器

        select-editor

-   查看glibc版本

        ldd --version
