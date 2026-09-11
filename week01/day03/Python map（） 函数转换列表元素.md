---
aliases:
  - "Python map 转换元素"
tags:
  - python/函数应用
week: week01
day: day03
review_order: 34
---

# Python map 转换元素

> [!abstract] 本篇重点
> **`map(fn, iterable)` 逐项转换，返回迭代器。**
>
> 前置知识：[[Python 迭代|Python 可迭代对象与迭代器]]、[[Python Lambda表达式|Python lambda 表达式]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python map（） 函数简介

在处理[列表](https://www.pythontutorial.net/python-basics/python-list/)（或[元组](https://www.pythontutorial.net/python-basics/python-tuples/)）时，通常需要转换列表的元素，并返回包含变换后元素的新列表。

假设你想将以下列表中的每个数字加倍：`bonuses`

```python
bonuses = [100, 200, 300]
```

为此，你可以用[for循环](https://www.pythontutorial.net/python-basics/python-for-loop-list/)遍历这些元素，将每个元素加倍，然后像这样添加到一个新的列表里：

```python
bonuses = [100, 200, 300]

new_bonuses = []

for bonus in bonuses:
    new_bonuses.append(bonus*2)

print(new_bonuses)
```

[试试看吧](https://www.pythontutorial.net/playground/?q=Ym9udXNlcyA9IFsxMDAsIDIwMCwgMzAwXQoKbmV3X2JvbnVzZXMgPSBbXQoKZm9yIGJvbnVzIGluIGJvbnVzZXM6CiAgICBuZXdfYm9udXNlcy5hcHBlbmQoYm9udXMqMikKCnByaW50KG5ld19ib251c2VzKQ%3D%3D)

输出：

```text
[200, 400, 600]
```

Python 通过使用内置函数，提供了一种更便捷的完成这类任务的方法。`map()`

`map()`遍历列表（或元组）中的所有元素，对每个元素应用函数，并返回新元素的新迭代器。

以下是该函数的基本语法：`map()`

```python
iterator = map(fn, list)
```
`map()` 接受任何[可迭代对象](https://www.pythontutorial.net/python-basics/python-iterables/)，不限于列表和元组。

回到前面的例子，先定义一个将奖金加倍的函数，再把它传给 `map()`：

```python
def double(bonus):
    return bonus * 2


bonuses = [100, 200, 300]

iterator = map(double, bonuses)
```

或者你用类似这样的[lambda表达式](https://www.pythontutorial.net/python-basics/python-lambda-expressions/)让代码更简洁：

```python
bonuses = [100, 200, 300]
iterator = map(lambda bonus: bonus*2, bonuses)
```
## 使用 Python map（） 函数，并附带字符串列表

以下示例使用 `map()` 转换字符串，再用 `list()` 收集结果；`capitalize()` 将首字符大写，其余字符小写：

```python
names = ['david', 'peter', 'jenifer']
new_names = map(lambda name: name.capitalize(), names)
print(list(new_names))
```

输出：

```text
['David', 'Peter', 'Jenifer']
```
## 使用 Python map（） 函数，包含嵌套列表

假设你有一个以下购物车，以嵌套列表表示：

```python
carts = [['SmartPhone', 400],
         ['Tablet', 450],
         ['Laptop', 700]]
```

你需要计算每个产品的税额，并加收10%的税率。此外，你需要将税款金额添加到清单中的每个项目的第三个元素中。

返回的列表应该大致如下：

```python
[['SmartPhone', 400, 40.0],
['Tablet', 450, 45.0],
['Laptop', 700, 70.0]]
```

为此，您可以使用函数创建列表中的新元素，并像这样添加新的税款金额：`map()`

```python
carts = [['SmartPhone', 400],
         ['Tablet', 450],
         ['Laptop', 700]]

TAX = 0.1
carts = map(lambda item: [item[0], item[1], item[1] * TAX], carts)

print(list(carts))
```
输出：

```text
[['SmartPhone', 400, 40.0], ['Tablet', 450, 45.0], ['Laptop', 700, 70.0]]
```
## 摘要

- `map()` 对每一项应用函数，返回产生转换结果的迭代器。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-map-list/)

## 知识链与自查

- **学完可接着看**：[[Python的reduce（） 函数将列表简化为单一值|Python reduce 累积归约]]。
- **按顺序复习 · 上一篇**：[[Python sorted|Python sorted 返回新列表]]。
- **按顺序复习 · 下一篇**：[[Python中筛选列表元素|Python filter 筛选元素]]。
- **自查**：能先用 for 写出与 map 相同的逐项转换吗？
