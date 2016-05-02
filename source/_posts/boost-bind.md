---
title: boost-bind
tags: [c++, boost, bind]
date: 2016-02-27 18:06:45
---

# 要点

-   `_1,_2...`代表的是原函数的第n个参数

```c++
void f(int i, int j, int k)
{
    cout << i << " " << j << " " << k << endl;
}

int main()
{
    boost::function<void (int i, int j, int k)> f1 = boost::bind(f, _3, _1, _2); // f1(k, i ,j)
    f1(1, 2, 3); // 3 1 2

    return 0;
}
```
