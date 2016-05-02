---
title: python-映射list
categories: [python]
tags: [python, 映射list]
date: 2015-01-27 10:06:21
---

# 数学联系

对某个集合进行映射（数学运算），生成一个新集合

# 作用

将一个序列映射为另一个序列，新序列的元素依赖于原序列的元素

# 示例

-   简单转换

```python
>>> li = [1, 9, 8, 4]
>>> [elem*2 for elem in li]      1
[2, 18, 16, 8]
>>> li                           2
[1, 9, 8, 4]
>>> li = [elem*2 for elem in li] 3
>>> li
[2, 18, 16, 8]
```

-   buildConnectionString

```python
>>> params = {"server":"mpilgrim", "database":"master", "uid":"sa", "pwd":"secret"}
>>> params.items()
[('server', 'mpilgrim'), ('uid', 'sa'), ('database', 'master'), ('pwd', 'secret')]
>>> [k for k, v in params.items()]                1
['server', 'uid', 'database', 'pwd']
>>> [v for k, v in params.items()]                2
['mpilgrim', 'sa', 'master', 'secret']
>>> ["%s=%s" % (k, v) for k, v in params.items()] 3
['server=mpilgrim', 'uid=sa', 'database=master', 'pwd=secret']
```

# 过滤列表推导

```python
>>> special_squares = [ x**2 for x in range(10) if x**2 > 5 and x**2 < 50 ]
>>> print special_squares
[9, 16, 25, 36, 49]
```

## 执行顺序

-   `range(10)`

-   `for x in range(10)`

-   `if ...`

-   `x**2`

# 参考

1.  <http://www.u.arizona.edu/~erdmann/mse350/topics/list_comprehensions.html>
1.  <http://woodpecker.org.cn/diveintopython/native_data_types/mapping_lists.html>
1.  <https://docs.python.org/2/tutorial/datastructures.html#list-comprehensions>
