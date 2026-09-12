---
aliases:
  - "Python list.sort 原地排序"
tags:
  - python/函数应用
week: week01
day: day03
review_order: 32
---

# Python list.sort 原地排序

> [!abstract] 本篇重点
> **`list.sort()` 修改原列表，返回 `None`；`key` 接收函数。**
>
> 前置知识：[[Python 列表|Python 列表]]、[[Python元组|Python 元组]]、[[Python Lambda表达式|Python lambda 表达式]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python 列表排序方法简介

排序[列表](https://www.pythontutorial.net/python-basics/python-list/)时，你使用以下方法：`sort()`

```python
list.sort()
```

`sort()` **原地排序**，修改原列表中元素的顺序，返回 `None`。

默认情况下，`sort()`使用小于运算符（）对列表中的元素进行排序。换句话说，它将较低的元素置于高元素之前。`<`

要降序排列，调用 `items.sort(reverse=True)`：

```python
list.sort(reverse=True)
```
### 排序元组列表

首先，指定一个排序键并将其传递给方法。要定义排序键，你需要创建一个函数，接受元组并返回你想要排序的元素：`sort()`

注意，`key` 接收的是函数对象，例如 `key=sort_key`；不要写成 `key=sort_key()`。

```python
companies = [('Google', 2019, 134.81),
             ('Apple', 2019, 260.2),
             ('Facebook', 2019, 70.7)]


# define a sort key
def sort_key(company):
    return company[2]



# sort the companies by revenue
companies.sort(key=sort_key, reverse=True)

# show the sorted companies
print(companies)
```
### 使用 lambda 表达式

为了更简洁，Python 允许你用以下语法定义一个没有名称的函数：

```python
lambda arguments: expression
```

没有名称的函数称为**匿名函数**。这种语法被称为**[λ表达](https://www.pythontutorial.net/python-basics/python-lambda-expressions/)**式。

从技术上讲，它等价于以下函数：

```python
def name(arguments):
    return expression
```

以下示例使用lambda表达式按收入从低到高排序公司：

```python
companies = [('Google', 2019, 134.81),
             ('Apple', 2019, 260.2),
             ('Facebook', 2019, 70.7)]

# sort the companies by revenue
companies.sort(key=lambda company: company[2])

# show the sorted companies
print(companies)
```
## 摘要

- 使用Python List方法对列表进行排序。`sort()`
- `sort()`按字母顺序排序字符串元素，并从最小到大排序数字元素。
- 使用该选项来反转默认排序顺序。`sort(reverse=True)`

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-sort-list/)

## 知识链与自查

- **学完可接着看**：[[Python sorted|Python sorted 返回新列表]]、[[week01/day03/今日练习|Day02 今日练习与错题复盘]]。
- **按顺序复习 · 上一篇**：[[Python Lambda表达式|Python lambda 表达式]]。
- **按顺序复习 · 下一篇**：[[Python sorted|Python sorted 返回新列表]]。
- **自查**：`key=sort_key` 与 `key=sort_key()` 有什么区别？
