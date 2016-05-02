---
title: python获取IP对应的MAC
categories: [python]
tags: [python, IP, MAC]
date: 2014-12-05 10:21:28
---

## 代码

```python
def get_mac_from_ip(ip):
    """
    Return the mac from ip in windows.
    """
    from subprocess import Popen, PIPE
    import re
    Popen(["ping", "-c 1", ip], stdout=PIPE, stderr=PIPE)
    pid = Popen(["arp", "-a", ip], stdout=PIPE, stderr=PIPE)
    s = pid.communicate()[0]
    if s is None:
        raise IOError("can't get mac from ip(%s)!" % ip)
    try:
        mac = re.search(r"(([a-f\d]{1,2}\-){5}[a-f\d]{1,2})", s).groups()[0]
    except AttributeError:
        raise IOError("can't find mac from ip(%s)!" % ip)
    return mac

print(get_mac_from_ip('100.100.102.300'))
```

## 参考

1.  <http://snipplr.com/view/70832/>
