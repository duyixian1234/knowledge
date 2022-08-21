

## [GIL](https://docs.python.org/zh-cn/3/glossary.html#term-global-interpreter-lock)

> 在 CPython 中，由于存在 全局解释器锁，同一时刻只有一个线程可以执行 Python 代码（虽然某些性能导向的库可能会去除此限制）。 如果你想让你的应用更好地利用多核心计算机的计算资源，推荐你使用 multiprocessing 或 concurrent.futures.ProcessPoolExecutor。 但是，如果你想要同时运行多个 I/O 密集型任务，则多线程仍然是一个合适的模型。

## Python多线程

### threading标准库

可以使用threading标准库的Thread类创建并管理线程，相对而言比较繁琐。

### ThreadPoolExecutor

concurrent.futures 标准库提供了ThreadPoolExecutor类型，可以方便创建和使用线程池。

#### 示例

```python
import time
import requests
from functools import partial
from concurrent.futures import ThreadPoolExecutor

def fetch(url:str, session: requests.Session) -> int:
    resp = session.get(url)
    return resp.status_code

with requests.Session() as session:
    start = time.time()
    for x in range(100):
        fetch(f'http://httpbin.org/get?a={x}', session) 
    print(f'For Loop Cost: {time.time()-start} seconds')

# For Loop Cost: 26.713851928710938 seconds

with ThreadPoolExecutor() as pool,requests.Session() as session:
    fetch_with_session = partial(fetch, session = session)
    start = time.time()
    list(pool.map(fetch_with_session, [f'http://httpbin.org/get?a={x}' for x in range(100)]))
    print(f'ThreadPoolExecutor Cost: {time.time()-start} seconds')

# ThreadPoolExecutor Cost: 3.781949758529663 seconds
```