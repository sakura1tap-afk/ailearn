---
aliases:
  - "Python 列表"
tags:
  - python/序列
week: week01
day: day02
review_order: 24
---

# Python 列表

> [!abstract] 本篇重点
> **列表有序且可变；`append()` 修改原列表并返回 `None`。**
>
> 前置知识：[[python变量|Python 变量]]、[[python字符串|Python 字符串]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 什么是列表

列表是有序的项目集合。

Python 使用方括号（`[]`）表示列表。以下显示了一个空白列表：

```python
empty_list = []
```

通常，一个列表包含一个或多个项目。要分隔两个项目，使用逗号（，）。例如：

```python
todo_list = ['Learn Python List','How to manage List elements']
```
由于列表通常包含许多项目，使用复数名词命名是个好习惯，例如 `numbers`、`colors` 和 `shopping_carts`。

以下示例定义了一个六[个数字](https://www.pythontutorial.net/python-basics/python-numbers/)的列表：

```python
numbers = [1, 3, 2, 7, 9, 4]
```

如果你打印出列表，你会看到包括方括号在内的表示方式。例如：

```python
numbers = [1, 3, 2, 7, 9, 4]
print(numbers)
```

一个列表可以包含其他列表。以下示例定义了一个列表列表：

```python
coordinates = [[0, 0], [100, 100], [200, 200]]
print(coordinates)
```

输出：

![](https://www.pythontutorial.net/wp-content/uploads/2021/02/Python-List-a-List-of-Lists-1.png)

## 访问列表中的元素

由于列表是一个有序集合，你可以通过以下索引访问其元素：

```python
list[index]
```

列表是基于零的索引。换句话说，第一个元素的索引为0，第二个元素的索引为1，依此类推。

例如，下面展示了如何访问列表的第一个元素：`numbers`

```python
numbers = [1, 3, 2, 7, 9, 4]
print(numbers[0])
```

负索引允许你访问从列表末尾开始的元素。

`items[-1]` 返回最后一个元素，`items[-2]` 返回倒数第二个元素。

```python
numbers = [1, 3, 2, 7, 9, 4]
print(numbers[-1])
print(numbers[-2])
```

输出：

```text
4
9
```

## 修改、添加和移除元素

列表是可变的。这意味着你可以修改列表中的元素，添加新元素到列表中，或从列表中移除元素。

### 修改列表中的元素

要更改一个元素，你用以下语法为它分配一个新值：

```python
list[index] = new_value
```

### 向列表添加元素

该方法在列表末尾附加一个元素。例如：`append()`

```python
numbers = [1, 3, 2, 7, 9, 4]
numbers.append(100)

print(numbers)
```

`insert()`在列表中的任意位置添加一个新元素。

例如，以下在列表的索引2处插入数字100：`numbers`

```python
numbers = [1, 3, 2, 7, 9, 4]
numbers.insert(2, 100)

print(numbers)
```

输出：

```text
[1, 3, 100, 2, 7, 9, 4]
```

### 从列表中移除元素

该语句允许你通过指定元素的位置来移除列表中的元素。`del`

以下示例展示了如何从列表中移除第一个元素：

```python
numbers = [1, 3, 2, 7, 9, 4]
del numbers[0]

print(numbers)
```

该方法从列表中移除最后一个元素并返回该元素：`pop()`

要通过值去除元素，使用`remove()`。注意，该方法只去除列表中遇到的第一个元素。`remove()`

例如，以下步骤将值为9的元素从列表中移除：`numbers`

```python
numbers = [1, 3, 2, 7, 9, 4, 9]

numbers.remove(9)
print(numbers)
```

输出：

```text
[1, 3, 2, 7, 4, 9]
```

## 摘要

- 列表是有序的项目集合。
- 使用 `items[index]` 访问元素；第一个元素的索引是 `0`。
- 使用负索引从末尾访问元素；最后一个元素的索引是 `-1`。
- 用于修改列表中的元素。`list[index] = new_value`
- 用于在列表末尾添加一个新元素。`append()`
- 用于在列表中的某个位置添加新元素。`insert()`
- 用来从列表中移除一个元素并返回该元素。`pop()`
- 用于从列表中移除元素。`remove()`

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-list/)

## 知识链与自查

- **学完可接着看**：[[Python元组|Python 元组]]、[[Python 中解包列表|Python 序列解包]]、[[Python 列表切片|Python 列表切片]]、[[For 循环|Python for 遍历列表与 enumerate]]、[[查找列表中元素的索引|Python 列表查找与成员判断]]、[[Python 排序列表|Python list.sort 原地排序]]。
- **按顺序复习 · 上一篇**：[[Python 函数文档字符串|Python 函数文档字符串]]。
- **按顺序复习 · 下一篇**：[[Python元组|Python 元组]]。
- **自查**：`a.append(x)`、`a[x]`、`a = a.append(x)` 分别意味着什么？
