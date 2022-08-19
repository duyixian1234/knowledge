---
id: lhye4vil5un8143hanrbkni
title: Memory Management
desc: ""
updated: 1660888550231
created: 1660280832914
---

## 虚拟内存

### 目标

- 透明
- 效率
- 保护

## 类型

### 栈内存

### 堆内存

- malloc 调用
- free 调用

### 错误

- segment fault 忘记分配内存
- buffer overflow 缓冲区溢出 安全风险
- uninitialized read
- memory leak 内存泄漏
- dangling pointer 悬垂指针
- double free 重复释放
- invalid free 无效释放

## 内存管理

### 地址转换

#### dynamic relocation 动态重定位

```
physical address = virtual address + base
```

![os-memory-management](https://res.weread.qq.com/wrepub/epub_30179184_52)

### 分段

### 空闲空间管理

- 最优匹配
- 最差匹配
- 首次匹配
- 下次匹配

[Linux 内存管理中的 slab 分配器 ](https://www.cnblogs.com/pengdonglin137/p/3878552.html)

### 分页

![分页](https://res.weread.qq.com/wrepub/epub_30179184_85)

> #### 数据结构——页表
>
> 现代操作系统的内存管理子系统中最重要的数据结构之一就是页表（page table）。通常，页表存储虚拟—物理地址转换（virtual-to-physical address translation），从而让系统知道地址空间的每个页实际驻留在物理内存中的哪个位置。由于每个地址空间都需要这种转换，因此一般来说，系统中每个进程都有一个页表。页表的确切结构要么由硬件（旧系统）确定，要么由 OS（现代系统）更灵活地管理。

#### 交换空间