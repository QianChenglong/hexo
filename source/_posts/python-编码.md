---
title: python-编码
categories: [python]
tags: [python, 编码, encode, decode]
date: 2014-12-08 15:48:51
---

# unicode内部编码实现

-   python2 UCS2(编译默认，--enable-unicode=ucs2)

        >>> sys.maxunicode
        65535

-   python3 UCS4(编译默认，--enable-unicode=ucs4)

        >>> sys.maxunicode
        1114111

# 相关数据类型

## 字节序列(bytes)

一串由0到255之间的数字组成的序列叫做bytes对象

-   用来存储经过某种编码方式(如`UTF-8`)的`unicode`字符串

-   转换为字符串时,需要知道该`bytes`的编码

## 字符串(string)

-   字符是一种抽象

-   一个不可变(immutable)的Unicode编码的字符序列叫做string

-   存储对应的UNICODE编码值

# python源文件编码方式

-   python2 默认编码为ASCII，若为其他编码，需要在文件头注释说明(`coding: XXX`)

-   python3 默认UTF-8

# 编码转换(str <=> bytes)

## python3

-   string => bytes

        a_string = '深入 Python'
        by = a_string.encode('utf-8')
        len(by)
        by = a_string.encode('gb18030')
        len(by)

-   bytes => string

        a_string = '深入 Python'
        by = a_string.encode('utf-8')
        by.decode('utf-8')

参考：

1.  <http://stackoverflow.com/questions/1446347/how-to-find-out-if-python-is-compiled-with-ucs-2-or-ucs-4>

## 获取系统编码参数

系统的缺省编码(一般就是ascii)：sys.getdefaultencoding()

系统当前的编码：locale.getdefaultlocale()

系统代码中临时被更改的编码（通过locale.setlocale(locale.LC_ALL,“zh_CN.UTF-8″)）：locale.getlocale()

文件系统的编码：sys.getfilesystemencoding()

终端的输入编码：sys.stdin.encoding

终端的输出编码：sys.stdout.encoding

## 文件编码与字符串编码

字符床常量编码取决于文件编码

-   默认编码为ASCII

-   文件头显式指定编码，需要文件本身编码与该声明编码一致

        # Coding: utf-8

定义`UNICODE`字符串，在字符床常量前加`u`

## 判断字符串编码

-   `type(str)`

-   `isinstance()`

```python
print 'default encoding: ' , sys.getdefaultencoding()
print 'stdout encoding: ' , sys.stdout.encoding
s='中文'
if isinstance(s, str):
    print 's is a string object'
elif isinstance(s, unicode):
    print 's is a unicode object'
```

## 常见问题

###   `SyntaxError: Non-ASCII character '\xe4' in file XXX`

-   原因

文件编码不是`ASCII`编码，但文件开头未指定文件编码

-   解决

在文件开头指定文件本身编码即可.(文件最好采用`utf-8`编码)



## 参考

1.  <http://woodpecker.org.cn/diveintopython3/strings.html>
1.  <https://docs.python.org/2/howto/unicode.html>
