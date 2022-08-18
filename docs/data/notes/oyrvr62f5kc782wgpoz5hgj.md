## 介绍

[asyncio](https://docs.python.org/zh-cn/3/library/asyncio.html)是 Python 原生的协程标准库。

> asyncio 是用来编写 **并发** 代码的库，使用 **async/await** 语法。
>
> asyncio 被用作多个提供高性能 Python 异步框架的基础，包括网络和网站服务，数据库连接库，分布式任务队列等等。
>
> asyncio 往往是构建 IO 密集型和高层级 **结构化** 网络代码的最佳选择。
>
> asyncio 提供一组 **高层级** API 用于:
>
> - 并发地 [**运行 Python 协程**](https://docs.python.org/zh-cn/3/library/asyncio-task.html#coroutine) 并对其执行过程实现完全控制;
> - 执行 [**网络 IO 和 IPC**](https://docs.python.org/zh-cn/3/library/asyncio-stream.html#asyncio-streams);
> - 控制 [**子进程**](https://docs.python.org/zh-cn/3/library/asyncio-subprocess.html#asyncio-subprocess);
> - 通过 [**队列**](https://docs.python.org/zh-cn/3/library/asyncio-queue.html#asyncio-queues) 实现分布式任务;
> - [**同步**](https://docs.python.org/zh-cn/3/library/asyncio-sync.html#asyncio-sync) 并发代码;
>
> 此外，还有一些 **低层级** API 以支持 _库和框架的开发者_ 实现:
>
> - 创建和管理 [**事件循环**](https://docs.python.org/zh-cn/3/library/asyncio-eventloop.html#asyncio-event-loop)，以提供异步 API 用于 [<span class="pre">网络化</span>](https://docs.python.org/zh-cn/3/library/asyncio-eventloop.html#asyncio.loop.create_server "asyncio.loop.create_server"), 运行 [<span class="pre">子进程</span>](https://docs.python.org/zh-cn/3/library/asyncio-eventloop.html#asyncio.loop.subprocess_exec "asyncio.loop.subprocess_exec")，处理 [<span class="pre">OS</span><span> </span><span class="pre">信号</span>](https://docs.python.org/zh-cn/3/library/asyncio-eventloop.html#asyncio.loop.add_signal_handler "asyncio.loop.add_signal_handler") 等等;
> - 使用 [**transports**](https://docs.python.org/zh-cn/3/library/asyncio-protocol.html#asyncio-transports-protocols) 实现高效率协议;
> - 通过 async/await 语法 [**桥接**](https://docs.python.org/zh-cn/3/library/asyncio-future.html#asyncio-futures) 基于回调的库和代码。

## 生态

- ASGI（[[programming-languages.python.FastAPI]]）
- [timofurrer/awesome-asyncio](https://github.com/timofurrer/awesome-asyncio)
