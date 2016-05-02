---
title: samba-常见问题
categories: [samba]
tags: [samba]
date: 2015-06-11 17:14:27
---

# 诊断流程

1.  首先确定samba服务是否运行，smb和nmb两个进程。

1.  看一下服务器samba配置文件/etc/samba/smb.conf的workgroup，它必须与Win的工作组一致，一般Win的工作组是WORKGROUP。

1.  看配置文件里的interfaces是否正确，hosts allow的ip段是否覆盖Win的ip地址。

1.  服务器上启用user安全级别时，是否添加了共享用户，是否允许共享用户浏览。

1.  防火墙的规则设置是否正确。

1.  SELinux是否阻止你访问samba共享的目录。

