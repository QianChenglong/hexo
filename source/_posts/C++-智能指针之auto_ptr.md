---
title: C++-智能指针之auto_ptr
categories: [C++]
tags: [C++, auto_ptr]
date: 2015-06-16 15:59:42
---

# 功能

-   提供一种简单的垃圾回收机制，当变量(`new`分配的)离开其作用域，自动执行`delete`

# 原理

基于RAII(资源申请即初始化)，利用C++确定性析构，保证变量当离开作用域时，自动执行析构函数来释放内存

# 缺陷

-   不能将同一个对象存储到多个`auto_ptr`，会导致多次析构，从而崩溃

        A *p = new A();
        std::auto_ptr<A> a(p);
        std::auto_ptr<A> b(p);

-   不能管理数据对象，因为`~auto_ptr`是`delete`而不是`delete []`

        int *p=new int[10];
        auto_ptr<int>ap(p);

# 结论

C++11已经抛弃它，boost也有更好的替代品，决不使用！

# 示例代码

```C++
#include <iostream>
#include <memory>

class A {
public:
    A()
    {
        std::cout << __PRETTY_FUNCTION__ << std::endl;
    }

    ~A()
    {
        std::cout << __PRETTY_FUNCTION__ << std::endl;
    }

private:
};


int main(int argc,char* argv[])
{
    std::auto_ptr<A> a(new A());

    return 0;
}
```

# 参考

1.  <http://www.cplusplus.com/reference/memory/auto_ptr/?kw=auto_ptr>
1.  <http://baike.baidu.com/view/3511189.htm>
