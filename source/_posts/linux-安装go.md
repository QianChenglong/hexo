---
title: linux-安装go
tags: [linux, go]
date: 2015-07-22 10:37:34
---

1.  下载对应二进制包([官网](https://golang.org/dl/))

1.  解压安装

    tar -C /opt/go-$VERSION -xvf go$VERSION.$OS-$ARCH.tar.gz

1.  修改环境变量

    vi /etc/profile

    export GOROOT=/opt/go-$VERSION
    export PATH=$PATH:$GOROOT/bin

1.  生效

    -   `source /etc/profile`

    -   重启sshd
