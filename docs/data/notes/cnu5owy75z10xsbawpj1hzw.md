
## 基本用法

```python
assert [x for x in range(10) if x % 2] == [1, 3, 5, 7, 9]
assert {x for x in range(10) if x % 2} == {1, 3, 5, 7, 9}
assert {x: x**2 for x in range(10)} == {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25, 6: 36, 7: 49, 8: 64, 9: 81}
```

## 内部实现

使用`get_iter`指令，效率高于 map/filter 函数

```python
>>> import dis
>>> dis.dis("[x for x in 'abc']")
1           0 LOAD_CONST               0 (<code object <listcomp> at 0x000001F3D5502E40, file "<dis>", line 1>)
              2 LOAD_CONST               1 ('<listcomp>')
              4 MAKE_FUNCTION            0
              6 LOAD_CONST               2 ('abc')
              8 GET_ITER
             10 CALL_FUNCTION            1
             12 RETURN_VALUE

Disassembly of <code object <listcomp> at 0x000001F3D5502E40, file "<dis>", line 1>:
  1           0 BUILD_LIST               0
              2 LOAD_FAST                0 (.0)
        >>    4 FOR_ITER                 4 (to 14)
              6 STORE_FAST               1 (x)
              8 LOAD_FAST                1 (x)
             10 LIST_APPEND              2
             12 JUMP_ABSOLUTE            2 (to 4)
        >>   14 RETURN_VALUE
```

```python
>>> import timeit
comprehension = timeit.timeit("[x.upper() for x in 'abc']", number=10000)
map_function = timeit.timeit("list(map(str.upper, 'abc'))", number=10000)
print(f'{comprehension=} vs {map_function=}')

comprehension=0.003946700002416037 vs map_function=0.0069931999896653
```
