---
aliases:
  - "Python for 遍历列表与 enumerate"
tags:
  - python/序列
week: week01
day: day03
review_order: 28
---

# Python for 遍历列表与 enumerate

> [!abstract] 本篇重点
> **直接遍历元素；同时需要位置和值时用 `enumerate()`。**
>
> 前置知识：[[Python 列表|Python 列表]]、[[Python范围循环|Python for 与 range]]、[[Python 中解包列表|Python 序列解包]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 使用 Python for 循环来迭代一个列表

要遍历[列表](https://www.pythontutorial.net/python-basics/python-list/)，使用循环语句如下：`for`

```python
for item in list:
    # process the item
```
## 使用 Python for 循环遍历带有索引的列表

有时，你可能想访问循环内部元素的索引。在这种情况下，你可以使用 `enumerate()`。

`enumerate()` 返回一个迭代器，每次产生一个 `(计数, 元素)` 元组；默认从 0 计数，对列表通常对应索引。

以下示例在 `for` 循环中使用 `enumerate(cities)` 遍历城市及其索引：

```python
cities = ['New York', 'Beijing', 'Cairo', 'Mumbai', 'Mexico']

for item in enumerate(cities):
    print(item)
```
输出：

```text
(0, 'New York')
(1, 'Beijing')
(2, 'Cairo')
(3, 'Mumbai')
(4, 'Mexico')
```

要访问索引，你可以在循环语句中[这样解包该元组](https://www.pythontutorial.net/python-basics/python-unpack-list/)：`for`

```python
cities = ['New York', 'Beijing', 'Cairo', 'Mumbai', 'Mexico']

for index, city in enumerate(cities):
    print(f"{index}: {city}")
```

输出：

```text
0: New York
1: Beijing
2: Cairo
3: Mumbai
4: Mexico
```

## 摘要

- 用循环来迭代一个列表。`for`
- 使用 `for index, item in enumerate(items)` 同时获取索引和元素。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-for-loop-list/)

## 知识链与自查

- **学完可接着看**：[[Python 迭代|Python 可迭代对象与迭代器]]、[[Python Lambda表达式|Python lambda 表达式]]、[[week01/day03/今日练习|Day02 今日练习与错题复盘]]。
- **按顺序复习 · 上一篇**：[[Python 列表切片|Python 列表切片]]。
- **按顺序复习 · 下一篇**：[[查找列表中元素的索引|Python 列表查找与成员判断]]。
- **自查**：何时只需要 num，何时还需要索引 i？
