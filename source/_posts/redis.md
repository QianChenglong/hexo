---
title: redis
tags: [redis]
date: 2016-04-05 19:41:45
---

# 配置(/etc/redis.conf)

```conf
requirepass foobared # 设置密码
```

# 命令

-   启动redis

        redis-server /etc/redis.conf

-   根据pattern删除key

        redis-cli KEYS "prefix:*" | xargs redis-cli DEL
