---
id: se4tmj9t31kkax83l4wmprt
title: Venv
desc: ''
updated: 1660394367688
created: 1660319282842
---

## 创建虚拟环境

```shell
ubuntu:tmp/ $ python -m venv .venv                                                                           [20:35:41]
ubuntu:tmp/ $ ls -l -a                                                                                       [20:35:49]
总用量 12
drwxrwxr-x  3 ubuntu ubuntu 4096 8月  13 20:35 .
drwxr-xr-x 43 ubuntu ubuntu 4096 8月  13 20:35 ..
drwxrwxr-x  5 ubuntu ubuntu 4096 8月  13 20:35 .venv
```

## 激活虚拟环境

```shell
ubuntu:tmp/ $ source .venv/bin/activate                                                                      [20:37:29]
(.venv) ubuntu:tmp/ $ which python                                                                           [20:38:01]
/home/ubuntu/tmp/.venv/bin/python
(.venv) ubuntu:tmp/ $                                                                                        [20:38:07]
```