---
title: python-json操作
categories: [python]
tags: [python, json]
date: 2014-12-04 14:32:52
---

## 解码(decoding)：

把Json格式字符串解码转换成Python对象

-   从字符串中

```python
data = '{"id": 1, "name": "Tom"}'
json_data = json.loads(data)
```

-   从文件流

```python
data = '{"id": 1, "name": "Tom"}'
json_data = json.load(data)
```

## 编码(encoding)：

把一个Python对象编码转换成Json字符串

-   转为`python`字符串

```python
json.dumps(['foo', {'bar': ('baz', None, 1.0, 2)}])
```

## 参考

1.  <https://docs.python.org/2/library/json.html>
