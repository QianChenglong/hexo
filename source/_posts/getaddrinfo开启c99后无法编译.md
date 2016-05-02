---
title: getaddrinfo开启c99后无法编译
categories: [socket]
tags: [socket, getaddrinfo, c99, error, 编译]
date: 2015-02-05 11:29:56
---

# 原因

开启了`c99`后，gcc采用严格标准c(`__STRICT_ANSI`)，而`getaddrinfo`是POSIX定义的，
所以无法使用，具体可查看`/usr/include/netdb.h`，`/usr/include/features.h`

**摘取:**

```
The `-ansi' switch to the GNU C compiler, and standards conformance
options such as `-std=c99', define __STRICT_ANSI__.  If none of
these are defined, or if _DEFAULT_SOURCE is defined, the default is
to have _SVID_SOURCE, _BSD_SOURCE, and _POSIX_SOURCE set to one and
_POSIX_C_SOURCE set to 200809L.  If more than one of these are
defined, they accumulate.  For example __STRICT_ANSI__,
_POSIX_SOURCE and _POSIX_C_SOURCE together give you ISO C, 1003.1,
and 1003.2, but nothing else.
```

# 参考

1.  <https://groups.google.com/d/msg/gnu.gcc.help/a88eE4Ga73o/P3vji9iM5pwJ>
