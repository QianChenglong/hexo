---
title: sql-数据更新
tags: [sql]
date: 2015-07-20 14:49:34
---

# 使用场景

-   记录不存在,则插入

-   记录若存在,则更新指定值

# 要求

-   数据必须存在唯一性

# 方法

## 1.`INSERT ... ON DUPLICATE KEY UPDATE`

```sql
INSERT INTO table (id, name, age) VALUES(1, "A", 19) ON DUPLICATE KEY
UPDATE name=VALUES(name), age=VALUES(age)
```

# 参考

1.  <https://dev.mysql.com/doc/refman/5.0/en/insert-on-duplicate.html>
