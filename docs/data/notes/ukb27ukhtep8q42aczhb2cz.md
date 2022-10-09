
![系统架构](https://res.weread.qq.com/wrepub/epub_30179184_142)

## DMA(Direct Memory Access)

## 设备驱动程序

大部分操作系统内核代码都是驱动程序。

## 磁盘驱动器

平均寻道时间

### 磁盘调度

- 最短寻道时间优先
- 电梯算法（C-SCAN）

## 廉价冗余磁盘阵列（RAID）

- RAID 0(条带化)
- RAID 1(镜像)
- RAID 4(奇偶校验)
- RAID 5(旋转奇偶校验)

![RAID](https://res.weread.qq.com/wrepub/epub_30179184_187)

## 文件系统

- 文件
- 目录
- inode
- open 调用
- 文件描述符
- fsync 调用
- 硬链接，软链接，unlink
- 文件系统检查程序（fsck）与日志
- ext3/ext4，NTFS，btrfs

> inode 是许多文件系统中使用的通用名称，用于描述保存给定文件的元数据的结构，例如其长度、权限以及其组成块的位置。这个名称至少可以追溯到 UNIX（如果不是早期的系统，可能还会追溯到 Multics）。它是 index node（索引节点）的缩写，因为 inode 号用于索引磁盘上的 inode 数组，以便查找该 inode 号对应的 inode。我们将看到，inode 的设计是文件系统设计的一个关键部分。大多数现代系统对于它们记录的每个文件都有这样的结构，但也许用了不同的名字（如 dnodes、fnodes 等）。

### 数据完整性与保护

- 校验和
