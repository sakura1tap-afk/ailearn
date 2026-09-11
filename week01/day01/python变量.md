---
aliases:
  - "Python 变量"
tags:
  - python/基础
week: week01
day: day01
review_order: 3
---

# Python 变量

> [!abstract] 本篇重点
> **`name = value` 把名称绑定到值；变量名应表达用途。**
>
> 前置知识：[[python基础|Python 基础语法]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 命名变量

当你命名变量时，需要遵守一些规则。如果不这样做，你会收到错误。

以下是你应牢记的变量规则：

- 变量名可以包含字母、数字和下划线 `_`，不能以数字开头。
- 变量名不能包含空格。要区分变量中的单词，可以使用下划线，例如 `sorted_list`。
- 变量名不能使用 Python 关键字；应避免使用 `list`、`str`、`sum` 等内置名称，以免遮蔽原有功能。

以下指南帮助你定义好的变量名：

- 变量名称应简洁且具描述性。例如，`active_user` 比 `au` 更有描述性。
- 使用下划线（_）来分隔变量名中的多个单词。
- 避免单独用 `l` 和 `O` 命名，因为它们容易与数字 `1` 和 `0` 混淆。

## 摘要

- 变量是一个标签，你可以给它赋予一个值。变量的值可以在程序过程中变化。
- 使用 `variable_name = value` 为变量赋值。
- 变量名称应尽可能简洁且具描述性。此外，它们应遵守 Python 变量命名规则。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-variables/)

## 知识链与自查

- **学完可接着看**：[[python常量|Python 常量约定]]、[[python数字|Python 数字]]、[[python赋值操作符|Python 复合赋值运算符]]、[[python字符串|Python 字符串]]、[[Python 函数|Python 函数]]、[[Python 列表|Python 列表]]。
- **按顺序复习 · 上一篇**：[[python注释|Python 注释]]。
- **按顺序复习 · 下一篇**：[[python常量|Python 常量约定]]。
- **自查**：能解释变量名与它所指向的值的区别吗？
