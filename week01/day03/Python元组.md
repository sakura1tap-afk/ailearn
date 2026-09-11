---
aliases:
  - "Python 元组"
tags:
  - python/序列
week: week01
day: day03
review_order: 25
---

# Python 元组

> [!abstract] 本篇重点
> **元组是不可变序列；不能重新指定某个位置的元素。**
>
> 前置知识：[[Python 列表|Python 列表]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python 元组介绍

有时，你想列出一个在程序中不能[](https://www.pythontutorial.net/python-basics/python-list/)更改的项目清单。元组可以做到这一点。
元组与列表都属于序列；**元组是不可变序列**，不是列表的一种。不可变表示元组中各位置对元素的引用不能更改。

### 定义元组

元组通常用圆括号 `()` 表示，列表用方括号 `[]` 表示。

以下示例定义了一个称为 的元组：`rgb`

```python
rgb = ('red', 'green', 'blue')
```
元组中的元素引用不能替换；下面尝试把 `rgb[0]` 改为 `'yellow'`，会报错：

```python
rgb = ('red', 'green', 'blue')
rgb[0] = 'yellow'
```
结果是错误：

```text
TypeError: 'tuple' object does not support item assignment
```

## 分配元组

虽然你不能更改元组，但你可以为[引用](https://www.pythontutorial.net/advanced-python/python-references/)元组的[变量](https://www.pythontutorial.net/python-basics/python-variables/)分配一个新的元组。例如：

```python
colors = ('red', 'green', 'blue')
print(colors)

colors = ('Cyan', 'Magenta', 'Yellow', 'black')
print(colors)
```

## 摘要

- 元组是不可变序列。
- 当你需要不可变的序列时，可以使用元组。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-tuples/)

> [!note] 理解补充
> 单元素元组写作 `(1,)`，逗号不能省略。元组中的引用不能替换，但其内部引用的列表仍然可以被修改。参见 [Python 元组与序列](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences)。

## 知识链与自查

- **学完可接着看**：[[Python 中解包列表|Python 序列解包]]、[[Python 排序列表|Python list.sort 原地排序]]。
- **按顺序复习 · 上一篇**：[[Python 列表|Python 列表]]。
- **按顺序复习 · 下一篇**：[[Python 中解包列表|Python 序列解包]]。
- **自查**：元组本身不可变，与变量可以重新赋值矛盾吗？
