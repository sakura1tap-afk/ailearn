---
aliases:
  - "Python 默认参数"
tags:
  - python/函数
week: week01
day: day02
review_order: 21
---

# Python 默认参数

> [!abstract] 本篇重点
> **调用时省略该参数就使用默认值；普通参数列表中必填参数在前。**
>
> 前置知识：[[Python 函数|Python 函数]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python 默认参数介绍

当你[定义一个函数](https://www.pythontutorial.net/python-basics/python-functions/)时，可以为每个参数指定默认值。

要指定参数的默认值，你使用以下语法：

```python
def function_name(param1, param2=value2, param3=value3, ...):
```

## 摘要

- 使用 Python 默认参数来简化函数调用。
- 在非默认参数后面放置默认参数。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-default-parameters/)

> [!note] 理解补充
> 默认值在函数定义时求值一次。暂时避免用 `[]` 这类可变对象作默认值，以免多次调用共享它。参见 [Python 默认参数](https://docs.python.org/3/tutorial/controlflow.html#default-argument-values)。

## 知识链与自查

- **学完可接着看**：[[Python 关键词参数|Python 关键字参数]]、[[Python Lambda表达式|Python lambda 表达式]]。
- **按顺序复习 · 上一篇**：[[Python 函数|Python 函数]]。
- **按顺序复习 · 下一篇**：[[Python 关键词参数|Python 关键字参数]]。
- **自查**：调用时显式传值，还会使用默认值吗？
