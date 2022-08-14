---
id: agx5nqdeeujae4czk9e9c67
title: 结构化模式匹配
desc: ""
updated: 1660448337230
created: 1660319119340
---

## 介绍

[Python 3.10 中的模式匹配 | 那时难决 (duyixian.cn)](https://www.duyixian.cn/2021/03/19/Structural%20Pattern%20Matching%20In%20Python%203.10/)

## 示例

```python
# 快速排序的一个概念性实现
def quicksort(arr: list[int]) -> list[int]:
    match arr:
        case first,:
            return [first]
        case first, second:
            return [first, second] if first <= second else [second, first]
        case first, *rest:
            return (
                quicksort([num for num in rest if num <= first])
                + [first]
                + quicksort([num for num in rest if num > first])
            )
```
