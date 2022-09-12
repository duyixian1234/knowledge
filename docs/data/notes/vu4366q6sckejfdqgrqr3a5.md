

参考[【使用 Python 实现算法】02 原生类型与内置函数 | 那时难决 (duyixian.cn)](https://www.duyixian.cn/2022/06/27/2022-06-27%20algorithms%20in%20python%2002/#int)

## round

Python 的 round 实现为银行家算法，四舍六入五成双

```python
assert round(1.2) == 1
assert round(1.6) == 2
assert round(1.5) == 2
assert round(2.5) == 2
```

## all, any

会提前返回

## next

可以应用在获取第一个符合条件的元素的场景。

```python
assert next(x for x in range(1, 10) if x % 3 == 0) == 3
```

## enumerate

```python
for index, ch in enumerate("abc"):
    pass
```

## map, filter

返回一个[[迭代器 | programming-languages.python.iterators]]，可使用列表推导式替换

## sorted

返回的是一个 list

## zip

可用于初始化 dict

```python
assert dict(zip('abcd', range(4))) == {'a': 0, 'b': 1, 'c': 2, 'd': 3}
```

可以使用 zip 进行矩阵转置。

```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
assert [list(row) for row in zip(*matrix)] == [[1, 4, 7], [2, 5, 8], [3, 6, 9]]
```
