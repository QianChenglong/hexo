---
title: python-遍历目录
categories: [python]
tags: [python, 遍历, 目录]
date: 2015-01-27 11:05:54
---

# os.walk

```python
import os

for root, dirs, files in os.walk('.'):
    for file in files:
        print file
```

# 查找指定文件

## glob.glob

```python
import glob

for file in glob.glob('*.txt'):
    print(file)
```

## fnmatch.fnmatch

```python
import fnmatch
import os

for file in os.listdir('.'):
    if fnmatch.fnmatch(file, '*.txt'):
        print file
```

## re.match

```python
for d in [f for f in os.listdir('.') if re.match(r'build-\(.*\)-.*', f)]:
    print('cleanning {} ...'.format(d))
    shutil.rmtree(d)
```

# 参考

1.  <http://stackoverflow.com/questions/2225564/get-a-filtered-list-of-files-in-a-directory>
