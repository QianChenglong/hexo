---
title: mysql使用memcached缓存
categories: [mysql]
tags: [mysql, memcached]
date: 2015-06-08 18:10:00
---

-   授权memcached访问权限

        grant select on stock_app.* to memcache@"%" identified by "12345";
