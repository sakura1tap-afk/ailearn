---
aliases:
  - "Python filter 筛选元素"
tags:
  - python/函数应用
week: week01
day: day03
review_order: 35
---

# Python filter 筛选元素

> [!abstract] 本篇重点
> **`filter(fn, iterable)` 保留判断结果为真的元素，返回迭代器。**
>
> 前置知识：[[Python 迭代|Python 可迭代对象与迭代器]]、[[Python Lambda表达式|Python lambda 表达式]]、[[python if语句|Python if 条件分支]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python filter（） 函数简介

有时，你需要[遍历列表中的元素](https://www.pythontutorial.net/python-basics/python-for-loop-list/)，并根据指定条件选择其中一些元素。

假设你有以下列表：`scores`

```python
scores = [70, 60, 80, 90, 50]
```

要从列表中获得每个元素大于或等于70的所有元素，使用以下代码：`scores`

```python
scores = [70, 60, 80, 90, 50]

filtered = []

for score in scores:
    if score >= 70:
        filtered.append(score)

print(filtered)
```

它是如何运作的。

- 首先，定义空列表 `filtered`，用于存放从 `scores` 中筛选出的元素。
- 然后遍历 `scores`，把大于或等于 70 的元素追加到 `filtered`。
- 第三，把清单展示给屏幕。`filtered`
Python 内置了一个叫做函数，可以让你以更美观的方式过滤列表（或元组）。`filter()`

以下是函数的语法：`filter()`

```python
filter(fn, list)
```
`filter()` 的第二个参数可以是任何可迭代对象，不限于列表。

以下用 `filter()` 筛选 `scores` 中大于或等于 70 的分数，再用 `list()` 收集结果：

```python
scores = [70, 60, 80, 90, 50]
filtered = filter(lambda score: score >= 70, scores)

print(list(filtered))
```
### 使用 Python filter（） 函数过滤嵌套列表示例

假设你有以下嵌套列表：

```python
countries = [
    ['China', 1394015977],
    ['United States', 329877505],
    ['India', 1326093247],
    ['Indonesia', 267026366],
    ['Bangladesh', 162650853],
    ['Pakistan', 233500636],
    ['Nigeria', 214028302],
    ['Brazil', 21171597],
    ['Russia', 141722205],
    ['Mexico', 128649565]
]
```

列表中的每个元素是一个包含国家名称和人口的列表；这些数字是教程的历史示例数据。

要获取所有人口超过3亿的国家，你可以使用以下函数：`filter()`

```python
countries = [
    ['China', 1394015977],
    ['United States', 329877505],
    ['India', 1326093247],
    ['Indonesia', 267026366],
    ['Bangladesh', 162650853],
    ['Pakistan', 233500636],
    ['Nigeria', 214028302],
    ['Brazil', 21171597],
    ['Russia', 141722205],
    ['Mexico', 128649565]
]

populated = filter(lambda c: c[1] > 300000000, countries)

print(list(populated))
```

输出：

```text
[['China', 1394015977], ['United States', 329877505], ['India', 1326093247]]
```

## 摘要

- 使用 Python 函数来筛选列表（或元组）。`filter()`

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-filter-list/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[Python map（） 函数转换列表元素|Python map 转换元素]]。
- **按顺序复习 · 下一篇**：[[Python的reduce（） 函数将列表简化为单一值|Python reduce 累积归约]]。
- **自查**：筛选与转换的区别是什么？
