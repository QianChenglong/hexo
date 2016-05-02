---
title: mysql-IP类型.md
tags: [mysql, IP]
date: 2015-07-15 13:59:19
---

-   int

-   字符串转int

        select inet_aton('192.168.0.1');

-   int转字符串

        select inet_ntoa('3232235521');

-   判断IP段

        select inet_aton('192.168.0.0') <= inet_aton('192.168.0.1');
        select inet_aton('192.168.1.1') <= inet_aton('192.168.0.255');
