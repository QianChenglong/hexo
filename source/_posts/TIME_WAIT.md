---
title: TIME_WAIT
tags: [tcp, TIME_WAIT]
date: 2016-04-14 12:04:34
---

# 是什么?

# 为什么需要？

# 如何查看?

# 如何优化？

```conf
net.ipv4.tcp_tw_reuse = 1
#表示开启重用。允许将TIME-WAIT sockets重新用于新的TCP连接，默认为0，表示关闭；
net.ipv4.tcp_tw_recycle = 1
#表示开启TCP连接中TIME-WAIT sockets的快速回收，默认为0，表示关闭；
net.ipv4.tcp_fin_timeout
#修改系統默认的 TIMEOUT 时间。
```
