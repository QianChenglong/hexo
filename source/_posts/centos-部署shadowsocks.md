---
title: centos-部署shadowsocks
categories: [centos]
tags: [centos, shadowsocks]
date: 2015-3-7 13:30:44
---

# 环境

-   centos7-64

# 安装

1.  安装pip

        yum install m2crypto python-setuptools
        easy_install pip

1.  安装shadowsocks

        pip install shadowsocks

1.  创建`/etc/shadowsocks.json`

    ```json
    {

    "server":"0.0.0.0",
    "server_port":80,
    "local_port":1080,
    "password":"password",
    "timeout":600,
    "method":"table",
    "fast_open":true
    }
    ```
1.  打开TCP fast open

        vi /etc/sysctl.conf

        # turn on TCP Fast Open on both client and server side
        net.ipv4.tcp_fastopen = 3
        sysctl -wp

1.  启动server

        ssserver -c /etc/shadowsocks.json

1.  防火墙放行

        firewall-cmd --permanent --add-port=80/tcp
        firewall-cmd --reload


# 使用systemd启动

-   编写service文件

        vim /etc/systemd/system/shadowsocks.service

    ```service
    [Unit]
    Description=Shadowsocks Server
    After=network.target

    [Service]
    Type=forking
    PIDFile=/run/shadowsocks/server.pid
    PermissionsStartOnly=true
    ExecStartPre=/bin/mkdir -p /run/shadowsocks
    ExecStart=/usr/bin/ssserver --pid-file /var/run/shadowsocks/server.pid --log-file /var/log/shadowsocks.log -c /etc/shadowsocks.json -d start
    Restart=on-abort

    [Install]
    WantedBy=multi-user.target
    ```

-   手动启动

        systemctl start shadowsocks

-   加入到开机启动

        systemctl enable shadowsocks

# 参考

1.  <http://www.live-in.org/archives/2043.html>
1.  <http://www.v2ex.com/t/108649>
1.  <https://github.com/shadowsocks/shadowsocks/wiki/Optimizing-Shadowsocks>
1.  <https://github.com/shadowsocks/shadowsocks/wiki/Configuration-via-Config-File>
