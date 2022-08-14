

参考[【使用 Python 实现算法】02 原生类型与内置函数 | 那时难决 (duyixian.cn)](https://www.duyixian.cn/2022/06/27/2022-06-27%20algorithms%20in%20python%2002/#int)

## int

- int.bit_count
- int.bit_length

## float

- float.as_integer_ration
- 格式化：`f"{1/3:.4f}" == "0.3333" `

## list

- 获取并删除指定位置的元素（O(n)复杂度）：list.pop(n)

## tuple

- tuple 对象可以作为字典的键

## dict

- dict.fromkeys
- 可使用[[字典推导式|programming-languages.python.list comprehension]]初始化 dict：`{ch: count for ch, count in [("a", 1), ("b", 2), ("c", 3)]} == {"a": 1, "b": 2, "c": 3}`
- 可使用`|`合并 dict，`{1: 2, 2: 3} | {2: 4, 3: 5} == {1: 2, 2: 4, 3: 5}`

## set

- 可使用[[集合推导式|programming-languages.python.list comprehension]]初始化 set：`{x for x in range(10) if x % 2 == 0} == {0, 2, 4, 6, 8}`
- set 支持的一些运算符：`&` `|` `-` `>` `>=` `<` `<=`

## str

- 使用各类 str.isxxx 方法检查字符串内容
- str.partition： `assert "A B C".partition(" ") == ("A", " ", "B C") `
