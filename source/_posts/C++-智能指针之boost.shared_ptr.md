---
title: C++-智能指针之boost.scroped_ptr
categories: [C++]
tags: [C++, auto_ptr]
date: 2015-06-16 15:59:42
---

# 功能

-   提供一种强大的垃圾回收机制

-   copyable，可存放到容器中，可多次引用

-   当引用计数为0时，自动析构

# 使用误区

-   不能使用同一个对象指针来构造

        A *a = new A(1);

        boost::shared_ptr<A> p1(a);
        boost::shared_ptr<A> p2(a);
        // 应该这样
        // boost::shared_ptr<A> p1(new A(1));
        // boost::shared_ptr<A> p2(p1);

# 结论

非常强大，多多使用！

# 示例代码

```C++
#include <iostream>

#include <boost/shared_ptr.hpp>

class A {
public:
    A(int id): id_(new int(id))
    {
        std::cout << __PRETTY_FUNCTION__ << std::endl;
    }

    ~A()
    {
        std::cout << __PRETTY_FUNCTION__ << std::endl;
        delete id_;
    }

    int *id_;

};

int main(int argc,char* argv[])
{
    A *a = new A(1);

    boost::shared_ptr<A> p1(a);
    boost::shared_ptr<A> p2(p1);

    std::cout << *(p1->id_) << std::endl;

    return 0;
}
```
