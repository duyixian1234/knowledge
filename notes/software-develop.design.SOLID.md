---
id: v03c4xgyco81innvtbwsn60
title: SOLID
desc: ""
updated: 1661937094575
created: 1660279910063
---

## 单一职责原则（Single Responsibility Principle）

- 每个模块应该只做一件事
- 每个模块都因该有且仅有一个被修改的原因
- 任何一个软件模块都应该只对某一类行为者负责

## 开放封闭原则（Open Close Principle）

- 设计良好的计算机软件应该易于扩展，同时抗拒修改
- 如果 A 组件不想被 B 组件上发生的修改所影响，那么就应该让 B 组件依赖于 A 组件

## 里氏替换原则（Liskov Substitution Principle）

- 典型反例，Square 与 Rectangle（Rectangle可以分别设置宽和高，Square的变长会被最后一次的设置覆盖）


## 接口隔离原则（Interface Sgregation Principle）

- 模块不应该依赖未使用到的组件

## 依赖反转原则（Dependency inversion principle）

- 应在代码中多使用抽象接口，尽量避免使用那些多变的具体实现类
- 不要在具体实现类上创建衍生类
- 不要覆盖包含具体实现的函数
- 应避免在代码中写入与任何具体实现相关的名字，或者是其他容易变动的事物的名字
- 常见实践：工厂模式
