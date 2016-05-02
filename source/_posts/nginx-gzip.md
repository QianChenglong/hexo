---
title: nginx-gzip
tags: [nginx, gzip]
date: 2015-11-26 15:38:20
---

```nginx
http {
    gzip  on; # 开启gzip
    gzip_min_length 1k; # 大于等于1K才压缩
    gzip_comp_level 1; # 压缩级别(1~10),值越大,压缩程度越高
    gzip_proxied any; # 所有代理的返回都压缩
    gzip_types text/plain application/x-javascript text/css text/javascript application/json; # 当Content-Type为这些值时才压缩
}
```

# 参考

1.  <http://nginx.org/en/docs/http/ngx_http_gzip_module.html>
