---
aliases:
  - "Python 基础语法"
tags:
  - python/基础
week: week01
day: day01
review_order: 1
---

# Python 基础语法

> [!abstract] 本篇重点
> **缩进决定代码块；名称区分大小写。**
>
> 前置知识：从这里开始
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 1. 缩进与代码块
通过使用**==缩进和空白==**来组织代码，Python 代码获得了以下优势：

- 首先，你永远不会漏掉一个区块的开头或结尾代码，这与其他编程语言（如Java或[C#](https://www.csharptutorial.net/)）不同。
- 其次，编码风格本质上是统一的。如果你必须维护别人开发的代码，那个代码看起来和你的一样。
- 第三，代码比其他编程语言更易读、更清晰。

## 2. 注释
在 Python 中，单行**==注释==**以哈希（#）符号开头，后面跟着注释。例如：

```python
# This is a single line comment in Python
```

而且Python还支持其他类型的[注释](https://www.pythontutorial.net/python-basics/python-comments/)。

## 3. 语句与换行
Python 使用换行字符来分隔语句。

## 4. 标识符

标识符是用来标识 Python 中[变量](https://www.pythontutorial.net/python-basics/python-variables/)、[函数](https://www.pythontutorial.net/python-basics/python-functions/)、[模块](https://www.pythontutorial.net/python-basics/python-module/)、[类](https://www.pythontutorial.net/python-oop/python-class/)及其他对象的名称。

标识符以字母或下划线 `_` 开头，后面可以包含字母、数字和下划线。

Python 标识符区分大小写。例如，`counter` 和 `Counter` 是不同的标识符。

此外，你不能使用 Python 关键字来命名标识符。

## 5. 关键字
Python 的 `keyword` 模块可用于查看当前版本的关键字。

要查找当前的关键字列表，您可以使用以下代码：

```python
import keyword

print(keyword.kwlist)
```

## 摘要

- Python 语句以换行字符结尾。
- Python 使用空格和缩进来组织其代码结构。
- 标识符是用来标识变量、函数、模块、类等的名称。
- 注释描述了代码为何有效。Python 解释器会忽略它们。
- 使用单引号、双引号、三引号或三重双引号来表示字符串的字面值。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-syntax/)

## 知识链与自查

- **学完可接着看**：[[python注释|Python 注释]]、[[python变量|Python 变量]]、[[Python范围循环|Python for 与 range]]。
- **按顺序复习 · 下一篇**：[[python注释|Python 注释]]。
- **自查**：看到冒号后，能判断哪些行属于同一个代码块吗？
