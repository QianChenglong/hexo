---
title: boost-lexical_cast
tags: [boost,lexiacal_cast]
date: 2015-07-23 15:38:32
---

-   不能转换空字符串!(需要捕获异常)

        try {
            boost::lexical_cast<int>("");
        } catch (boost::bad_lexical_cast &e) {
            ;
        }
