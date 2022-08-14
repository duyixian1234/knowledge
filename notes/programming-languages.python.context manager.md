---
id: ukppn0c8e7ihvzi1s3ttqge
title: 上下文管理器
desc: ""
updated: 1660448483458
created: 1660319059855
---

## 介绍

[RAII 概念与在 Python 中的应用 | 那时难决 (duyixian.cn)](https://www.duyixian.cn/2021/08/22/RAII/)

## 示例

```python
class MyContextManager:
    def __init__(self):
        self.used = False
    def __enter__(self):
        print('entering')
        self.used = True
        return self
    def __exit__(self, exc_type, exc_val, exc_tb):
        print('exiting')

with MyContextManager() as cm:
    print('in context')
    assert cm.used
```
