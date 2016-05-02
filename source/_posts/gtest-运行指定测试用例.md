---
title: gtest-运行指定测试用例
categories: [gtest]
tags: [gtest, 测试用例]
date: 2015-01-21 17:01:33
---

# 使用命令行

-   指定测试用例

    test.exe --gtest_filter=request_save_release_ip.multi_ips

-   指定测试用例集

    test.exe --gtest_filter=request_save_release_ip.*

# 使用gtest GUI工具(Guitar)

![](/img/gtest-运行指定测试用例-01.png)

# 参考

1.  <http://stackoverflow.com/questions/19798879/how-to-run-single-google-test-in-visual-studio>
