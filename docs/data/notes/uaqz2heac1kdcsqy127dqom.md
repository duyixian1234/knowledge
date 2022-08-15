
## 介绍

[生成器类型](https://docs.python.org/zh-cn/3/library/stdtypes.html#generator-types)

## yield 表达式

[yield 表达式](https://docs.python.org/zh-cn/3/reference/expressions.html#yield-expressions)

## 特点

- 惰性计算
- 节省内存

## 示例

```python
import itertools


def fib():
    a, b = 1, 1
    while True:
        yield a
        a, b = b, a + b

assert list(itertools.takewhile(lambda x: x < 100, fib())) == [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
```
