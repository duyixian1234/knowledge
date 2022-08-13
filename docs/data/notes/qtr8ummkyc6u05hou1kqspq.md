
## 介绍

[pipenv](https://pypi.org/project/pipenv/)是一个 Python 虚拟环境与包管理工具。可以理解为一个 Python 版本的 npm。

pipenv使用Pipfile定义项目的元信息（依赖，Python版本等）。

Pipfile使用[[software-develop.config.toml]]格式，下面是一个典型的[Pipfile](https://github.com/duyixian1234/fastapi-template/blob/master/Pipfile)的内容。

```toml
[[source]] # 设置pypi源信息
url = "https://mirrors.tencent.com/pypi/simple"
verify_ssl = true
name = "pypi"

[packages] # 维护依赖
fastapi = "*"
uvicorn = "*"
uvloop = "*"
httptools = "*"

[dev-packages] # 维护开发依赖
pylint = "*"
isort = "*"
mypy = "*"
pytest = "*"
pytest-cov = "*"
black = "*"
requests = "*"

[requires] # 指定Python版本
python_version = "3.9"

[pipenv] # 额外设置
allow_prereleases = true

```