# 解决本地运行server时，search的结果带config.url路径问题

## 原因

因为`hexo-generator-search\search.ejs`生成`search.xml`时，
使用了`<url><%- encodeURI(post.permalink) %></url>`。
暂时知道如何去手动指定想要的目录

## 临时解决方案

采用`local_config.yml`，额外定义`url`的值，
再运行`hexo server --cwd=E:\blog\hexo --config=E:\blog\hexo\local_config.yml`
