---
title: http-content-type
tags: [http, content-type]
date: 2015-11-25 14:56:02
---

# application/json

-   数据必须是`Unicode`编码,默认编码方式为`UTF-8`

-   因为`json`数据前2个字符总是`ASCII`字符(`{"`,与`[空格]`的组合),所以可以推断出其编码方式

    ```
    00 00 00 xx  UTF-32BE
    00 xx 00 xx  UTF-16BE
    xx 00 00 00  UTF-32LE
    xx 00 xx 00  UTF-16LE
    xx xx xx xx  UTF-8
    ```

-   若采用`UTF-16`或`UTF-32`,则需要设置`content-transfer-encoding`为`binary`??

参考:

1.  <http://www.ietf.org/rfc/rfc4627.txt>

# 参考

1.  <http://stackoverflow.com/questions/9254891/what-does-content-type-application-json-charset-utf-8-really-mean>
