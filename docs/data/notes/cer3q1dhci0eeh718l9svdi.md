
## 介绍

> decorator -- 装饰器返回值为另一个函数的函数，通常使用 `@wrapper` 语法形式来进行函数变换。装饰器的常见例子包括 `classmethod` 和 `staticmethod`。
>
> 装饰器语法只是一种语法糖，以下两个函数定义在语义上完全等价:
>
> ```python
> def f(arg):
>     ...
> f = staticmethod(f)
>
> @staticmethod
> def f(arg):
>     ...
> ```

## 示例

```python
def log_call(func):
    def wrapper(*args, **kwargs):
        print(f'Function {func.__name__} Called With ({args}, {kwargs})')
        return func(*args, **kwargs)
    return wrapper

@log_call
def add(x, y):
    return x + y

assert add(1, 2) == 3 # Function add Called With ((1, 2), {})
```
