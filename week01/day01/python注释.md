---
aliases:
  - "Python 注释"
tags:
  - python/基础
week: week01
day: day01
review_order: 2
---

# Python 注释

> [!abstract] 本篇重点
> **`#` 用于注释；文档字符串用于说明函数等对象。**
>
> 前置知识：[[python基础|Python 基础语法]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python 注释简介

有时候，你想记录你写的代码。例如，你可能想说明一段代码为何有效。要做到这一点，你就用注释。

通常，你会用注释来解释公式、算法和复杂的业务逻辑。
执行程序时，Python 解释器忽略注释，只解释代码本身。
记录代码时常用块注释、内联注释和文档字符串；严格来说，文档字符串是字符串字面量，不是 `#` 注释。

## Python 块注释

一个块注释解释了其后面的代码。通常，你会在与代码块相同的层级缩进一个块注释。

创建块注释时，你先有一个哈希符号（`#`），然后是一个空格和一个文本字符串。例如：

```python
# increase price by 5%
price = price * 1.05
```

## Python 内联注释
类似于块注释，内联注释以单一哈希符号（`#`）开头，后面跟一个空格和文本字符串。
以下示例展示了一个内联注释：

```python
salary = 120000
salary = salary * 1.02   # increase salary by 2%

print(salary)
```

## Python docstring

文档字符串是你在代码块（[例如函数）](https://www.pythontutorial.net/python-basics/python-functions/)中放入的[字符串](https://www.pythontutorial.net/python-basics/python-string/)字面量。

与普通注释不同，可以在运行时通过 `obj.__doc__` 访问对象的文档字符串，其中 `obj` 可以是函数对象。

通常，你会用文档字符串自动生成代码文档。

文档字符串称为docstrings。

严格来说，文档字符串不是注释。位于模块、类或函数体开头的字符串字面量可作为文档，通过 `__doc__` 访问。

Python 提供两种文档字符串：单行文档字符串和多行文档字符串。

## Python 多行注释

Python 没有专门包围多行注释的定界符；通常在每一行前加 `#`。

三引号用于多行字符串，不会自动让其中的内容成为注释；多行说明优先使用连续的 `#` 注释。

保持注释清晰、简洁且解释性强是一个好习惯。最终目标是为你和其他后续开发者节省时间和精力。

## 摘要

- 必要时使用注释来记录代码。
- 块注释和内联注释以哈希符号（`#`）开头。
- 用docstring来管理[函数](https://www.pythontutorial.net/python-basics/python-functions/)、[模块](https://www.pythontutorial.net/python-basics/python-module/)和[类](https://www.pythontutorial.net/python-oop/python-class/)。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-comments/)

## 知识链与自查

- **学完可接着看**：[[Python 函数文档字符串|Python 函数文档字符串]]。
- **按顺序复习 · 上一篇**：[[python基础|Python 基础语法]]。
- **按顺序复习 · 下一篇**：[[python变量|Python 变量]]。
- **自查**：能区分行内注释与函数文档字符串吗？
