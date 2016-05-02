---
title: wireshark-捕捉过滤器
categories: [wireshark]
tags: [wireshark, 过滤器]
date: 2014-12-19 11:13:09
---

用于决定将什么样的信息记录在捕捉结果中。需要在开始捕捉前设置。

# 捕捉器语法

    [not] primitive [and | or [not] primitive ...]

    primitive := qualifiers id

    id := name or number

    qualifiers := type dir proto

type

>type qualifiers say what kind of thing the id name or number refers to. Possible types are host, net , port and portrange. E.g., `host foo`, `net 128.3`, `port 20`, `portrange 6000-6008`. If there is no type qualifier, host is assumed.

# 常用过滤器

-   DHCP

        port 67 or port 68

-   目的MAC

        ether dst 74-D4-35-46-3C-8E

-   tcp端口

        tcp port 80

# 参考

1.  <https://www.wireshark.org/docs/wsug_html_chunked/ChCapCaptureFilterSection.html>
1.  <http://www.tcpdump.org/manpages/pcap-filter.7.html>
1.  <http://wiki.wireshark.org/CaptureFilters>
