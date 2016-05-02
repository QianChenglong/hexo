---
title: dns中递归查询与迭代查询的区别
categories: [网络]
tags: [网络, dns]
date: 2015-01-04 16:30:55
---

-   递归查询:

一般客户机和服务器之间属递归查询，即当客户机向DNS服务器发出请求后,若DNS服务器本身不能解析,则会向另外的DNS服务器发出查询请求，得到结果后转交给客户机；

-   迭代查询(反复查询):

一般DNS服务器之间属迭代查询，如：若DNS2不能响应DNS1的请求，则它会将DNS3的IP给DNS2，以便其再向DNS3发出请求；

# 参考

1.  <http://zhidao.baidu.com/link?url=zZcn6vwAvt3f_391aq8kqR-rohsN-WYq5mDst_bUkzxYpEJZyuH-3ggW5BibrDPcrNpbWMqH8nMrACtahNhmZq>
