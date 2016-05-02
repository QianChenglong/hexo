---
title: libnet_init
categories: [libnet]
tags: [libnet, libnet_init]
date: 2015-02-06 15:16:04
---

# 原型

```c
libnet_t* libnet_init(int injection_type, char*  device, char*  err_buf)
```

-   device

    -   windows

        -   winpcap设备名，类似`\Device\NPF_{2A7DEE95-B437-444C-BB09-85E4EAD5E61C}`
        -   前缀一致`\Device\NPF_`，后面的UUID可以通过`getmac /v`查看

    _参考:_

    1.  <http://stackoverflow.com/questions/17400903/libnet-device-network-interface-command-line-argument>
