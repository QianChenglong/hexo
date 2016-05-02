---
title: tcpdump
categories: [tcpdump]
tags: [tcpdump]
date: 2015-03-06 13:57:01
---

# 命令说明

    tcpdump [option] <expression>

# 选项

-   -n

    不将IP转换为域名

-   -nn

    协议，IP，端口都保持数字形式，不转换为对应名字

-   -i interface

    指定接口

-   -A 使用ASCII解释数据包

-   -w file

    packet存储到文件(pcap格式)，可用wireshark来分析

# 常用例子

-   DNS

        tcpdump port 53

-   ISAKMP

        tcpdump port 500

-   HTTP

        tcpdump -A tcp port 80
