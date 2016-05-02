---
title: python-日期加减操作
tags: [python]
date: 2015-07-24 16:27:07
---

```python
datetime.date.today() + datetime.timedelta(days=1)
today = datetime.date.today() + datetime.timedelta(days=1)
period = int(today.strftime("%Y%m%d"))
```

# 参考

1.  <http://stackoverflow.com/questions/1506901/cleanest-and-most-pythonic-way-to-get-tomorrows-date>
