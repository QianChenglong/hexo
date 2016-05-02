---
title: python3-md5
tags: [python3, md5]
date: 2015-09-06 15:54:00
---

1.  方法1

```python3
import hashlib

hashlib.md5(b'Hello world').hexdigest()
```

2.  方法2

```python3
import hashlib

md5 = hashlib.md5()
md5.update(b'Hello world')
md5.hexdigest()
```

3.  方法3

```python3
import hashlib

md5 = hashlib.new('md5', b'Hello world')
md5.hexdigest()
```

# 参考

1.  <https://docs.python.org/3/library/hashlib.html>
