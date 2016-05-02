---
title: net
tags: [windows, net]
date: 2016-04-25 10:59:32
---

# use(samba)

-   查看帮助

        net help use

-   建立连接

        net use /user:username \\computername\sharename password
        net use /user:pm \\192.168.1.2\pm pm0422

-   映射连接

        net use * /user:pm \\192.168.1.2\pm pm0422

-   删除连接

        net use \\computername\sharename /delete

## 参考

1.  <https://technet.microsoft.com/en-us/library/bb490717.aspx>
