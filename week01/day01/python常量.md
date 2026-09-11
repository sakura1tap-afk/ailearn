---
aliases:
  - "Python 常量约定"
tags:
  - python/基础
week: week01
day: day01
review_order: 4
---

# Python 常量约定

> [!abstract] 本篇重点
> **全大写名称表示常量约定，Python 不会禁止重新赋值。**
>
> 前置知识：[[python变量|Python 变量]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

用其他编程语言实现时，可以用常量。常量就像变量，但在程序执行过程中它们的值不会改变。

Python 的普通变量没有强制禁止重新赋值的常量机制。

为了解决这个问题，你用所有大写字母来命名变量，表示该变量应被视为常数。例如：

```python
FILE_SIZE_LIMIT = 2000
print(FILE_SIZE_LIMIT)
```
遇到这些变量时，不应更改它们的值。这些变量按**惯例是常数**的，而非规则。

## 摘要

- Python 没有内置的常量类型。
- 按照惯例，Python 使用一个变量，其名称包含所有大写字母来定义常量。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-constants/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[python变量|Python 变量]]。
- **按顺序复习 · 下一篇**：[[python数字|Python 数字]]。
- **自查**：全大写变量能不能重新赋值？
