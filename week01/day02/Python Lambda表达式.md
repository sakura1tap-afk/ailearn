---
aliases:
  - "Python lambda 表达式"
tags:
  - python/函数应用
week: week01
day: day02
review_order: 31
---

# Python lambda 表达式

> [!abstract] 本篇重点
> **`lambda 参数: 表达式` 创建函数，返回表达式的结果。**
>
> 前置知识：[[Python 函数|Python 函数]]、[[Python 默认参数|Python 默认参数]]、[[For 循环|Python for 遍历列表与 enumerate]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

有时，你需要写一个只有一个表达式的简单[函数](https://www.pythontutorial.net/python-basics/python-functions/)。不过，你需要用一次这个功能。因此，无需为此定义该函数。

这就是Python的lambda表达式发挥作用的地方。

## 什么是 Python lambda 表达式

Python 的 lambda 表达式允许你定义匿名函数。

匿名函数是指没有名称的函数。匿名功能在需要一次性使用时非常有用。

### 返回函数示例的函数
`times(2)` 返回一个函数，并把它赋给 `double`；使用 `double(...)` 调用这个返回的函数。

```python
def times(n):
    return lambda x: x * n

double = times(2)

result = double(2)
print(result)

result = double(3)
print(result)
```

## Python lambda 循环

请参见以下示例：

```python
callables = []
for i in (1, 2, 3):
    callables.append(lambda: i)

for f in callables:
    print(f())
```
它是如何运作的。

- 首先，定义空列表 `callables`，用于存放可调用的函数对象。
- 其次，从1迭代到3，每次迭代创建一个新的λ表达式，并将其添加到可调用列表。
- 第三，循环调用可调用函数。

预期输出为：

```text
1
2
3
```

然而，程序显示的输出如下：

```text
3
3
3
```

这些 lambda 在调用时读取变量 `i`；循环结束后 `i` 的值是 `3`，所以都返回 `3`。

要解决这个问题，你需要在每个λ表达式创建时将变量绑定到每个λ表达式。一种方法是使用[默认参数](https://www.pythontutorial.net/python-basics/python-default-parameters/)：`i`

```python
callables = []
for i in (1, 2, 3):
    callables.append(lambda a=i: a)

for f in callables:
    print(f())
```
输出：

```text
1
2
3
```

在这个例子中，a的值是在λ表达式创建时被评估的。因此，程序返回预期输出。

## 摘要

- 使用 Python lambda 表达式创建匿名函数，即没有名称的函数。
- lambda 表达式可以接受零个或多个参数，包含一个表达式，并返回该表达式的结果。
- 使用λ表达式将匿名函数传递给函数，并返回另一个函数的函数。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-lambda-expressions/)

## 知识链与自查

- **学完可接着看**：[[Python 排序列表|Python list.sort 原地排序]]、[[Python map（） 函数转换列表元素|Python map 转换元素]]、[[Python中筛选列表元素|Python filter 筛选元素]]。
- **按顺序复习 · 上一篇**：[[Python 迭代|Python 可迭代对象与迭代器]]。
- **按顺序复习 · 下一篇**：[[Python 排序列表|Python list.sort 原地排序]]。
- **自查**：为什么循环中的 lambda: i 最后都读到同一个 i？
