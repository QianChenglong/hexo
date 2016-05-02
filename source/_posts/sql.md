---
title: sql
tags: [sql]
date: 2015-09-30 14:12:47
---

# update

-   当需要部分更新时,不要使用多表关联更新

    因为可能部分关联失败,导致需要更新的数据没有更新

    ```sql
    update product a, order b set ... where a.product_id = b.product_id
    ```
