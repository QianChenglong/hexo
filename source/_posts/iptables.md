---
title: iptables-命令简记
categories: [iptables]
tags: [iptables, 命令]
date: 2015-03-09 15:58:21
---

# 要点

-   多张表(filter, nat, mangle等)，最重要的是`filter`(`INPUT`, `FORWARD`, `OUTPUT`)用来制定本机规则

# 选项

-   -n IP数字显示，避免DNS查询，加快查看速度

-   --line-numbers 显示规则编号

-   -L 列出规则

-   -D 删除规则

-   -A 追加到链尾

-   -I 加到链头

# 查看类

- 查看规则(默认操作filter表)

        iptables -L

        iptables-save -t filter

# 删除类

- 删除指定链规则

        iptables -D FORWARD 1(删除FORWARD链中的第一条规则)

- 清除所有已定义的规则

        iptables -F

- 清除自定义规则

        iptables -X

- 将所有的chain计数和流量统计归零

        iptables -Z

# 添加规则


- INPUT链，默认政策：DROP

        iptables -P INPUT DROP

- INPUT链，接口：本地环回(lo), ACCEPT

        iptalbes -A INPUT -i lo -j ACCEPT

- INPUT链，接口：以太网口(eth0)，源IP：192.168.1.67, ACCEPT

        iptables -A INPUT -i eth0 -s 192.168.1.67 -j ACCEPT

- INPUT链，接口：以太网口(eth0)，源IP段：192.168.1.0/24, ACCEPT

        iptables -A INPUT -i eth0 -s 192.168.1.0/24 -j ACCEPT

- INPUT链，源IP段：192.168.1.0/24, TCP, 目的端口:80, ACCEPT

        iptables -A INPUT -s 192.168.1.0/24 -p tcp -dport 80 -j ACCEPT

# 保存规则

    iptables-save

# 实例

-   添加多个端口

        iptables -A INPUT -p tcp --match multiport --dports 80,22,53 -j ACCEPT

-   添加端口区间

        iptables -I INPUT -i eth1 -p tcp -m tcp --dport 6000:8000 -j ACCEPT
