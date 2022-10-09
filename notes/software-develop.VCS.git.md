---
id: xxrwfft52a57a8c4tfrxnu3
title: git
desc: ""
updated: 1665301491003
created: 1660279209410
---

## 介绍

Git 是一个分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。

### 历史

> 同生活中的许多伟大事物一样，Git 诞生于一个极富纷争大举创新的年代。
>
> Linux 内核开源项目有着为数众多的参与者。 绝大多数的 Linux 内核维护工作都花在了提交补丁和保存归档的繁琐事务上（1991－2002 年间）。 到 2002 年，整个项目组开始启用一个专有的分布式版本控制系统 BitKeeper 来管理和维护代码。
>
> 到了 2005 年，开发 BitKeeper 的商业公司同 Linux 内核开源社区的合作关系结束，他们收回了 Linux 内核社区免费使用 BitKeeper 的权力。 这就迫使 Linux 开源社区（特别是 Linux 的缔造者 Linus Torvalds）基于使用 BitKeeper 时的经验教训，开发出自己的版本系统。 他们对新的系统制订了若干目标：
>
> - 速度
> - 简单的设计
> - 对非线性开发模式的强力支持（允许成千上万个并行开发的分支）
> - 完全分布式
> - 有能力高效管理类似 Linux 内核一样的超大规模项目（速度和数据量）
>
> 自诞生于 2005 年以来，Git 日臻成熟完善，在高度易用的同时，仍然保留着初期设定的目标。 它的速度飞快，极其适合管理大项目，有着令人难以置信的非线性分支管理系统

## Git 是什么

- 直接记录快照，而非差异比较
- 近乎所有操作都是本地执行
- Git 保证完整性
- Git 一般只添加数据

### 状态

- **已修改**表示修改了文件，但还没保存到数据库中。
- **已暂存**表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。
- **已提交**表示数据已经安全地保存在本地数据库中。

### 工作区、暂存区以及 Git 目录

![git](https://git-scm.com/book/en/v2/images/areas.png)

工作区是对项目的某个版本独立提取出来的内容。这些从 Git 仓库的压缩数据库中提取出来的文件，放在磁盘上供你使用或修改。

暂存区是一个文件，保存了下次将要提交的文件列表信息，一般在 Git 仓库目录中。按照 Git 的术语叫做“索引”，不过一般说法还是叫“暂存区”。

Git 仓库目录是 Git 用来保存项目的元数据和对象数据库的地方。这是 Git 中最重要的部分，从其它计算机克隆仓库时，复制的就是这里的数据。

### 基本的 Git 工作流程

1. 在工作区中修改文件。
2. 将你想要下次提交的更改选择性地暂存，这样只会将更改的部分添加到暂存区。
3. 提交更新，找到暂存区的文件，将快照永久性存储到 Git 目录。

## Git 基础

### 配置

#### 配置位置

1. `/etc/gitconfig` 文件: 包含系统上每一个用户及他们仓库的通用配置。 如果在执行`git config` 时带上`--system` 选项，那么它就会读写该文件中的配置变量。 （由于它是系统配置文件，因此你需要管理员或超级用户权限来修改它。）
2. `~/.gitconfig` 或`~/.config/git/config` 文件：只针对当前用户。 你可以传递`--global` 选项让 Git 读写此文件，这会对你系统上**所有** 的仓库生效。
3. 当前使用仓库的 Git 目录中的`config` 文件（即`.git/config`）：针对该仓库。 你可以传递`--local` 选项让 Git 强制读写此文件，虽然默认情况下用的就是它。。 （当然，你需要进入某个 Git 仓库中才能让该选项生效。）

每一个级别会覆盖上一级别的配置，所以 `.git/config` 的配置变量会覆盖 `/etc/gitconfig` 中的配置变量。

#### 配置项

- `user.name`：设置提交时使用的名字。
- `user.email`：设置提交时使用的邮箱地址。
- `core.editor`：设置 Git 在需要你输入信息时所使用的文本编辑器。

#### 检查配置信息

```bash
$ git config --list
user.name=John Doe
user.email=johndoe@example.com
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
...
```

## 使用 Git

### 获取 Git 仓库

#### 初始化仓库

```bash
$ git init
```

#### 克隆现有仓库

```bash
$ git clone <repo-url> [directory]
```

### 记录更新到仓库

![lifecycle](https://git-scm.com/book/en/v2/images/lifecycle.png)

#### 检查当前文件状态

```bash
$ git status
```

#### 跟踪新文件

```bash
$ git add <filename>
```

#### 暂存已修改的文件

```bash
$ git add <filename>
```

#### 状态简览

```bash
$ git status -s
```

#### 忽略文件

修改 `.gitignore`文件

##### 生成 .gitignore

- [github/gitignore: A collection of useful .gitignore templates](https://github.com/github/gitignore)
- [gitignore.io - 为你的项目创建必要的 .gitignore 文件 (toptal.com)](https://www.toptal.com/developers/gitignore)
- [.gitignore Generator - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=piotrpalarz.vscode-gitignore-generator)

#### 查看已暂存和未暂存的文件

```bash
$ git diff [--staged]
```

#### 提交更新

```bash
$ git commit
```

#### 跳过使用暂存区域

```bash
$ git commit -a -m "Commit Message"
```

#### 移除文件

```bash
$ git rm <filename>
```

##### 仅移除暂存区文件

```bash
$ git rm --cached <filename>
```

#### 移动文件

```bash
git mv file_from file_to
```

### 查看提交历史

```bash
git log
```

#### 格式

```bash
$ git log --pretty=oneline
```

| 选项 | 说明                                          |
| ---- | --------------------------------------------- |
| %H   | 提交的完整哈希值                              |
| %h   | 提交的简写哈希值                              |
| %T   | 树的完整哈希值                                |
| %t   | 树的简写哈希值                                |
| %P   | 父提交的完整哈希值                            |
| %p   | 父提交的简写哈希值                            |
| %an  | 作者名字                                      |
| %ae  | 作者的电子邮件地址                            |
| %ad  | 作者修订日期（可以用 --date=选项 来定制格式） |
| %ar  | 作者修订日期，按多久以前的方式显示            |
| %cn  | 提交者的名字                                  |
| %ce  | 提交者的电子邮件地址                          |
| %cd  | 提交日期                                      |
| %cr  | 提交日期（距今多长时间）                      |
| %s   | 提交说明                                      |

#### 常用选项

| 选项            | 说明                                                                                                        |
| --------------- | ----------------------------------------------------------------------------------------------------------- |
| -p              | 按补丁格式显示每个提交引入的差异。                                                                          |
| --stat          | 显示每次提交的文件修改统计信息。                                                                            |
| --shortstat     | 只显示 --stat 中最后的行数修改添加移除统计。                                                                |
| --name-only     | 仅在提交信息后显示已修改的文件清单。                                                                        |
| --name-status   | 显示新增、修改、删除的文件清单。                                                                            |
| --abbrev-commit | 仅显示 SHA-1 校验和所有 40 个字符中的前几个字符。                                                           |
| --relative-date | 使用较短的相对时间而不是完整格式显示日期（比如“2 weeks ago”）。                                             |
| --graph         | 在日志旁以 ASCII 图形显示分支与合并历史。                                                                   |
| --pretty        | 使用其他格式显示历史提交信息。可用的选项包括 oneline、short、full、fuller 和 format（用来定义自己的格式）。 |
| --oneline       | --pretty=oneline --abbrev-commit 合用的简写。                                                               |

### 撤销操作

#### 重新提交

```bash
$ git commit --amend
```

#### 取消暂存的文件

```bash
$ git reset HEAD <filename>
```

#### 撤销对文件的修改

```bash
$ git checkout -- <filename>
```

### 远程仓库的使用

#### 查看远程仓库

```bash
$ git remote -v
```

#### 添加远程仓库

```bash
$ git remote add <remote-name> <remote-url>
```

#### 从远程仓库中抓取与拉取

```bash
$ git fetch <remote>
```

#### 推送到远程仓库

```bash
$ git push <remote> <branch>
```

#### 远程仓库的重命名与移除

```bash
$ git remote rename <old-name> <new-name>
$ git remote remove <remote>
```

### 标签

#### 列出标签

```bash
$ git tag
```

#### 创建标签

```bash
$ git tag -a <tag> -m <message>
$ git tag <tag>
```

#### 后期打标签

```bash
$ git tag <tag> <commit-id>
```

#### 共享标签

```bash
$ git push <remote> <tag>
```

#### 删除标签

```bash
$ git tag -d <tag> # local
$ git push origin --delete <tag> # remote
```

#### 检出标签

```bash
$ git checkout <tag>
$ git checkout -b <new-branch> <tag>
```

### Git 别名

```bash
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
```

或者编辑`.gitconfig`文件的 alias 部分。

## Git 分支

### Git 对象

- blob：文件内容
- tree：目录结构
- commit：提交信息

![commit-and-tree](https://git-scm.com/book/en/v2/images/commit-and-tree.png)

Git 的分支，其实本质上仅仅是指向提交对象的可变指针。

> Git 的 master 分支并不是一个特殊分支。它就跟其它分支完全没有区别。之所以几乎每一个仓库都有 master 分支，是因为 git init 命令默认创建它，并且大多数人都懒得去改动它。

### 分支创建

本质是创建一个可以移动的新的指针。

```bash
$ git branch <branch-name>
```

![two-branches](https://git-scm.com/book/en/v2/images/two-branches.png)

#### HEAD 指针

HEAD 指针指向当前所在的本地分支。

![head-to-master](https://git-scm.com/book/en/v2/images/head-to-master.png)

### 分支切换

```bash
$ git checkout <branch-name>
```

![head-to-testing](https://git-scm.com/book/en/v2/images/head-to-testing.png)

创建分支并同时切换

```bash
$ git checkout -b <branch-name>
```

#### 项目分叉

在不同的分支上进行改动并提交，会造成项目分叉。

![divergent_history](https://git-scm.com/book/en/v2/images/advance-master.png)

### 分支合并

```bash
$ git checkout master
$ git merge <branch-name>
```

#### 冲突处理

手动修改有冲突的文件或使用图形化工具。

```bash
$ git mergetool
```

### 分支管理

`git branch` 命令

- `--merged`：已经合并到当前分支的分支
- `--no-merged`：尚未合并到当前分支的分支
- `-d`：删除已经合并的分支
- `-D`：强制删除分支
- `-m`：重命名分支

### 分支开发工作流

#### 长期分支

![long-term-branches](https://git-scm.com/book/en/v2/images/lr-branches-2.png)

#### 主题分支（功能分支）

主题分支是一种短期分支，用来实现单一特性或其相关工作。

### 远程分支

远程引用是对远程仓库的引用（指针），包括分支、标签等等。

#### 推送

```bash
$ git push <remote> <branch>
```

#### 拉取

fetch：从远程仓库获取数据，但不会自动合并到当前分支。

```bash
$ git fetch <remote> <branch>
```

pull：从远程仓库获取数据并自动合并到当前分支。

```bash
$ git pull <remote> <branch>
```

#### 删除远程分支

```bash
$ git push <remote> --delete <branch>
```

### 变基

提取其他分支的提交并将其应用到当前分支。

```bash
$ git rebase <branch>
```

#### 变基的风险

如果提交存在于你的仓库之外，而别人可能基于这些提交进行开发，那么不要执行变基。

`git pull --rebase`：在拉取时执行变基。

## 资源

![[resources.links#git:#*]]
