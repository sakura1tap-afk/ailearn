---
aliases:
  - "Python reduce 累积归约"
tags:
  - python/函数应用
week: week01
day: day03
review_order: 36
---

# Python reduce 累积归约

> [!abstract] 本篇重点
> **从 functools 导入 reduce；把累积值与下一项反复合并。**
>
> 前置知识：[[Python map（） 函数转换列表元素|Python map 转换元素]]、[[python赋值操作符|Python 复合赋值运算符]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 介绍 Python reduce（） 函数

Python 提供了一个函数，可以让你以更简洁的方式缩减列表。`reduce()`

以下是函数的语法：`reduce()`

```python
reduce(fn,list)
```

`reduce()` 从左向右反复调用 `fn(累积值, 当前元素)`，最终得到一个值。

与内置的 `map()`、`filter()` 不同，`reduce()` 属于 `functools` 模块，需要先导入。

要使用 `reduce()`，先从 `functools` 模块导入：

```python
from functools import reduce
```

## 摘要

- 使用Python函数将列表简化为单一值。`reduce()`

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-reduce-list/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[Python中筛选列表元素|Python filter 筛选元素]]。
- **按顺序复习 · 下一篇**：[[Python 递归函数|Python 递归函数]]。
- **自查**：能用“累积值 + 当前元素”解释列表求和吗？
