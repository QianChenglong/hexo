---
title: python解析x-www-form-urlencoded数据
categories: [python]
tags: [python, x-www-form-urlencoded, query-string]
date: 2014-12-03 16:30:55
---

## 代码

-   `urlencoded`转`string`

```python
    query_string = 'access_token=CB4C8F99D9B3E4AD376E7CF179CFA470&expires_in=7776000&refresh_token=4CCB49CAD66A9506F0621CE8E427F492'
    data = urlparse.parse_qs(query_string)
    access_token = data['access_token'][0]
```

-   `dict`转`urlencoded`

``` python
params = {'criterias[]': ['member', 'issue']}
urllib.urlencode(params, True)
```

## 参考

1.  <https://docs.python.org/2/library/urlparse.html>
