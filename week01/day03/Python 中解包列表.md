---
aliases:
  - "Python 序列解包"
tags:
  - python/序列
week: week01
day: day03
review_order: 26
---

# Python 序列解包

> [!abstract] 本篇重点
> **多个变量接收序列元素；带星号的变量收集剩余元素为列表。**
>
> 前置知识：[[Python 列表|Python 列表]]、[[Python元组|Python 元组]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 列表拆包介绍

以下示例定义了一个[字符串](https://www.pythontutorial.net/python-basics/python-string/)[列表](https://www.pythontutorial.net/python-basics/python-list/)：

```python
colors = ['red', 'blue', 'green']
```

要将列表中的第一、第二和第三个元素分配给[变量](https://www.pythontutorial.net/python-basics/python-variables/)，你可以像这样将单个元素分配给变量：

```python
colors = ['red', 'blue', 'green']

red = colors[0]
blue = colors[1]
green = colors[2]
```

不过，Python 提供了更好的实现方式。这叫做序列拆包。

基本上，你可以将[列表](https://www.pythontutorial.net/python-basics/python-list/)（以及[元组](https://www.pythontutorial.net/python-basics/python-tuples/)）的元素分配给多个变量。例如：

```python
colors = ['red', 'blue', 'green']

red, blue, green = colors

print(red)
print(green)
print(blue)
```

`colors` 中的第一、第二、第三个元素分别赋给 `red`、`blue`、`green`。

在这个例子中，左侧的变量数量与右侧列表中元素的数量相同。

如果左侧变量较少，就会出现错误。例如：

```python
colors = ['red', 'blue', 'green']
red, blue = colors
```
错误：

```text
ValueError: too many values to unpack (expected 2)
```

在这种情况下，Python 无法将三个元素解包为两个变量。

## 解包与打包

如果你只想拆解列表的前几个元素，而不在意其他部分，你可以：

- 首先，将所需元素解包到变量。
- 其次，把剩余的元素打包到一个新列表里，并赋值到另一个变量。

在变量名前加上星号（`*`）时，你可以把剩余元素打包到列表中并分配给变量。例如：

```python
colors = ['red', 'blue', 'green']
red, blue, *other = colors

print(red)
print(blue)
print(other)
```
输出：

```text
red
blue
['green']
```

## 摘要

- 解包将列表中的元素分配给多个变量。
- 在像这样的变量 *variable_name 前加上星号（*），将列表中剩余的元素打包到另一个列表中。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-unpack-list/)

## 知识链与自查

- **学完可接着看**：[[For 循环|Python for 遍历列表与 enumerate]]。
- **按顺序复习 · 上一篇**：[[Python元组|Python 元组]]。
- **按顺序复习 · 下一篇**：[[Python 列表切片|Python 列表切片]]。
- **自查**：`first, *rest = [1, 2, 3]` 得到什么？
