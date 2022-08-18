## 介绍

[gevent](https://pypi.org/project/gevent/)是一个基于协程的Python网络库。

> gevent is a [coroutine](https://en.wikipedia.org/wiki/Coroutine) -based [Python](http://python.org/) networking library that uses [greenlet](https://greenlet.readthedocs.io/) to provide a high-level synchronous API on top of the [libev](http://software.schmorp.de/pkg/libev.html) or [libuv](http://libuv.org/) event loop.
>
> Features include:
>
> * Fast event loop based on [libev](http://software.schmorp.de/pkg/libev.html) or [libuv](http://libuv.org/).
> * Lightweight execution units based on greenlets.
> * API that re-uses concepts from the Python standard library (for examples there are [events](http://www.gevent.org/api/gevent.event.html#gevent.event.Event) and [queues](http://www.gevent.org/api/gevent.queue.html#gevent.queue.Queue)).
> * [Cooperative sockets with SSL support](http://www.gevent.org/api/index.html#networking)
> * [Cooperative DNS queries](http://www.gevent.org/dns.html) performed through a threadpool, dnspython, or c-ares.
> * [Monkey patching utility](http://www.gevent.org/intro.html#monkey-patching) to get 3rd party modules to become cooperative
> * TCP/UDP/HTTP servers
> * Subprocess support (through [gevent.subprocess](http://www.gevent.org/api/gevent.subprocess.html#module-gevent.subprocess))
> * Thread pools
>
> gevent is [inspired by eventlet](http://blog.gevent.org/2010/02/27/why-gevent/) but features a more consistent API, simpler implementation and better performance. Read why others [use gevent](http://groups.google.com/group/gevent/browse_thread/thread/4de9703e5dca8271) and check out the list of the [open source projects based on gevent](https://github.com/gevent/gevent/wiki/Projects).

## 应用

- gunicorn
- celery
