
## 升级 pip

```shell
$ python -m pip install -U pip
```

## 指定 Pypi 源

### 镜像地址

| 镜像   | 地址                                          |
| ------ | --------------------------------------------- |
| 豆瓣   | https://pypi.doubanio.com/simple/             |
| 阿里云 | https://mirrors.aliyun.com/pypi/simple        |
| 腾讯云 | https://mirrors.cloud.tencent.com/pypi/simple |

### 安装时指定

```shell
$ pip install flask -i https://mirrors.tencent.com/pypi/simple
```

### 修改 requirements.txt

第一行加入`-i https://mirrors.tencent.com/pypi/simple`

### 设置为默认值

修改`$HOME/.config/pip/pip.conf`

```ini
[global]
timeout = 60
index-url = https://pypi.doubanio.com/simple/
NPM
```
