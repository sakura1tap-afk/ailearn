---
aliases:
  - "Python 布尔值与真值判断"
tags:
  - python/基础
week: week01
day: day01
review_order: 9
---

# Python 布尔值与真值判断

> [!abstract] 本篇重点
> **`True`、`False` 首字母大写；条件判断也接受其他类型的值。**
>
> 前置知识：[[python数字|Python 数字]]、[[python字符串|Python 字符串]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

布尔数据类型有两个值：`True` 和 `False`。

注意，`True` 和 `False` 分别以大写字母 `T` 和 `F` 开头。

## 虚值与真值

以下是 Python 中的虚值：

- 数字零（`0`)
- 空字符串`''`
- `False`
- `None`
- 一个[空列表](https://www.pythontutorial.net/python-basics/python-list/) `[]`
- 一个空[元组](https://www.pythontutorial.net/python-basics/python-tuples/) `()`
- 一个[空字典](https://www.pythontutorial.net/python-basics/python-dictionary/) `{}`

真值是那些不是虚假的其他值。

## 摘要

- Python 布尔数据类型有两个值：`True` 和 `False`。
- 使用 `bool(value)` 得到某个值的真值判断结果：`True` 或 `False`。
- 假值转换为 `False`，真值转换为 `True`；它们本身不一定是布尔类型。
- 假值包括数字零、空字符串、`False`、`None`、空列表 `[]`、空元组 `()` 和空字典 `{}` 等。
- 真值是那些不是虚假的值

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-boolean/)

## 知识链与自查

- **学完可接着看**：[[类型转换|Python 类型转换]]、[[python比较|Python 比较运算符]]、[[Python 逻辑运算符|Python 逻辑运算符]]。
- **按顺序复习 · 上一篇**：[[python字符串|Python 字符串]]。
- **按顺序复习 · 下一篇**：[[类型转换|Python 类型转换]]。
- **自查**：`bool(0)`、`bool("")`、`bool("False")` 分别是什么？
