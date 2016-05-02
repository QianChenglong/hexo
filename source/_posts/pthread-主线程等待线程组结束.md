---
title: pthread-主线程等待线程组结束
tags: [pthread]
date: 2015-08-15 16:41:42
---

```C++
for (int i = 0; i < THREAD_NUM; ++i) {
    if (pthread_create(&tid[i], NULL, counter, (void *)&i) != 0) {
        perror("pthread_create error");
        exit(1);
    }
}
for (int i = 0; i < THREAD_NUM; ++i) {
    if (pthread_join(tid[i], NULL) != 0) {
        perror("pthread_join error");
        exit(1);
    }
}
```

# 参考

1.  <http://stackoverflow.com/questions/11624545/how-to-make-main-thread-wait-for-all-child-threads-finish>
