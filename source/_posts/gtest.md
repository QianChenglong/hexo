---
title: gtest
tags: [gtest]
date: 2016-03-30 19:20:48
---

# 选项

-   当失败时，退出，打印堆栈

        --gtest_break_on_failure --gtest_catch_exceptions=0

# 编译

gtest默认安装到编译器搜索路径中

    g++ hex.cpp hex_test.cpp -lgtest -lgtest_main
