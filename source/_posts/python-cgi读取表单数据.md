---
title: python-cgi读取表单数据
categories: [python]
tags: [python, cgi, form]
date: 2014-12-03 16:41:16
---

## 代码

```python
form = cgi.FieldStorage()
if "name" not in form or "addr" not in form:
    print "<H1>Error</H1>"
    print "Please fill in the name and addr fields."
    return
print "<p>name:", form["name"].value
print "<p>addr:", form["addr"].value
```

## 参考

1.  <https://docs.python.org/2/library/cgi.html>
