---
title: windows获取文件名组成
categories: [windows]
tags: [windows, 文件名]
date: 2014-12-12 13:59:38
---

```C
void _splitpath(
   const char *path,
   char *drive,
   char *dir,
   char *fname,
   char *ext 
);
```

# 参考

1.  <http://msdn.microsoft.com/en-us/library/e737s6tf.aspx>
