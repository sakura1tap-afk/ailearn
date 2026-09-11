---
aliases:
  - "Python 函数文档字符串"
tags:
  - python/函数
week: week01
day: day02
review_order: 23
---

# Python 函数文档字符串

> [!abstract] 本篇重点
> **函数体的第一条语句是字符串时，它可作为 docstring；用 `help()` 查看。**
>
> 前置知识：[[Python 函数|Python 函数]]、[[python注释|Python 注释]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## help（） 函数介绍

Python 提供了一个内置函数，叫做它`help()`，可以展示[函数](https://www.pythontutorial.net/python-basics/python-functions/)的文档。

以下示例展示了该函数的文档：`print()`

```python
help(print)
```

## 使用文档字符串来记录函数

要记录你的函数，可以使用docstrings。[PEP 257](https://www.python.org/dev/peps/pep-0257/) 提供了文档字符串的约定。
当函数体的第一条语句是字符串字面量时，Python 会将其解释为文档字符串。例如：

```python
def add(a, b):
    "Return the sum of two arguments"
    return a + b
```

用 `help(add)` 查看 `add` 函数的文档：

```python
def add(a, b):
    "Return the sum of two arguments"
    return a + b

help(add)
```

输出：

```text
add(a, b)
    Return the sum of two arguments
```

通常，你会使用多行文档字符串：

```python
def add(a, b):
    """ Add two arguments
    Arguments:
        a: an integer
        b: an integer
    Returns:
        The sum of the two arguments
    """
    return a + b

help(add)
```

[试试看吧](https://www.pythontutorial.net/playground/?q=ZGVmIGFkZChhLCBiKToKICAgICIiIiBBZGQgdHdvIGFyZ3VtZW50cwogICAgQXJndW1lbnRzOgogICAgICAgIGE6IGFuIGludGVnZXIKICAgICAgICBiOiBhbiBpbnRlZ2VyCiAgICBSZXR1cm5zOgogICAgICAgIFRoZSBzdW0gb2YgdGhlIHR3byBhcmd1bWVudHMKICAgICIiIgogICAgcmV0dXJuIGEgKyBiCgpoZWxwKGFkZCk%3D)

输出：

```text
add(a, b)
    Add the two arguments
    Arguments:
            a: an integer
            b: an integer
        Returns:
            The sum of the two arguments
```

Python 将文档字符串存储在函数的属性中。`__doc__`

## 摘要

- 使用 `help()`获取函数的文档。
- 在函数的第一行放置字符串，可以是单行或多行字符串，以便添加文档。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-function-docstrings/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[Python 关键词参数|Python 关键字参数]]。
- **按顺序复习 · 下一篇**：[[Python 列表|Python 列表]]。
- **自查**：知道函数做什么之后，还能从文档中找到参数和返回值吗？
