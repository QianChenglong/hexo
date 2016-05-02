---
title: C++-智能指针之boost.scroped_ptr
categories: [C++]
tags: [C++, auto_ptr]
date: 2015-06-16 15:59:42
---

# 功能

-   提供一种垃圾回收机制，当变量(`new`分配的)离开其作用域，自动执行`delete`

# 缺陷

-   noncopyable，意味着不能存放到容器，或多次引用

# 结论

当不需要传递所有权时，可使用

# 示例代码

```C++
#include <iostream>

#include <boost/scoped_ptr.hpp>

class A {
public:
    A(int id): id_(id)
    {
        std::cout << __PRETTY_FUNCTION__ << std::endl;
    }

    ~A()
    {
        std::cout << __PRETTY_FUNCTION__ << std::endl;
    }

    int id_;

};

int main(int argc,char* argv[])
{
    boost::scoped_ptr<A> i(new A(1));

    std::cout << i->id_ << std::endl;

    return 0;
}
```
