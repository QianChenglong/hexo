---
title: python-获取文件名组成
categories: [python]
tags: [python, 文件名]
date: 2014-12-23 10:46:45
---

# 获取基本文件名

```python
filename="/tmp/test.txt"
os.path.basename(filename)
```

# 获取基本文件名(不包括拓展名)

```python
filename="/tmp/test.txt"
os.path.splitext(os.path.basename(filename))[0]
```

# 获取文件拓展名

```python
filename="/tmp/test.txt"
os.path.splitext(os.path.basename(filename))[1]
```

# 获取父目录
```python
filename="/tmp/test.txt"
os.path.dirname(filename)
```

# 参考

1.  <http://stackoverflow.com/questions/678236/how-to-get-the-filename-without-the-extension-from-a-path-in-python>
