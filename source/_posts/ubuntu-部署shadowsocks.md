---
title: ubuntu-部署shadowsocks
categories: [ubuntu]
tags: [ubuntu, shadowsocks]
date: 2015-03-06 14:59:42
---

# 安装

-   安装pip

        apt-get install python-gevent python-pip

-   安装shadowsocks

        pip install shadowsocks

-   创建`/etc/shadowsocks/config.json`

```json
{

“server”:“my_server_ip”,

“server_port”:8388,

“local_port”:1080,

“password”:“password”,

“timeout”:600,

“method”:“table”
}
```

- 启动server

    -   前端运行

        /usr/local/bin/ssserver -c /etc/shadowsocks.json

    -   daemon

        /usr/local/bin/ssserver -c /etc/shadowsocks.json -d start

# 客户端

[下载地址](https://github.com/clowwindy/shadowsocks/wiki/Ports-and-Clients)


## windows


# 参考

1.  <http://felixqu.com/2014/06/23/setup-shadowsocks-on-ubuntu/>
1.  <https://github.com/shadowsocks/shadowsocks/wiki/Shadowsocks-%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E>
