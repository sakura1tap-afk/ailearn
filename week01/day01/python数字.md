---
aliases:
  - "Python 数字"
tags:
  - python/基础
week: week01
day: day01
review_order: 5
---

# Python 数字

> [!abstract] 本篇重点
> **区分 `int` 与 `float`；数字中的下划线只改善可读性。**
>
> 前置知识：[[python变量|Python 变量]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

Python 支持[整数](https://www.pythontutorial.net/advanced-python/python-integers/)、[浮点](https://www.pythontutorial.net/advanced-python/python-float/)数和复数。

## 整数

[整数](https://www.pythontutorial.net/advanced-python/python-integers/)包括 -1、0、1、2 和 3 等数字。它们的类型为 `int`。
数学运算符如+、-、*和/来形成包含整数的表达式
计算幂时，使用 `**` 运算符。
要修改操作顺序，使用括号 。例如：`()`

## 浮点数

任何带有小数点的数字都是[浮点数](https://www.pythontutorial.net/advanced-python/python-float/)。“float”一词意味着小数点可以出现在数字的任意位置。
两个整数使用 `/` 做除法时，结果为浮点数（除数不能为零）；`//` 是向下取整除法。
如果在任何算术运算中将整数和浮点混合，结果是浮点数：

## 数字下划线

当数字过大时，读起来会变得困难。例如：

```python
count = 10000000000
```

为了让长数字更易读，可以用下划线分组数字，比如这样：

```python
count = 10_000_000_000
```

存储这些值时，Python 会忽略下划线。当屏幕上显示带下划线的数字时，它会这样做：

```python
count = 10_000_000_000
print(count)
```

## 摘要

- Python 支持常见的数值类型，包括整数、浮点数和复数。
- 用下划线将大数字分组。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-numbers/)

## 知识链与自查

- **学完可接着看**：[[python算术|Python 算术运算符]]、[[python布尔|Python 布尔值与真值判断]]、[[类型转换|Python 类型转换]]、[[python比较|Python 比较运算符]]、[[Python范围循环|Python for 与 range]]。
- **按顺序复习 · 上一篇**：[[python常量|Python 常量约定]]。
- **按顺序复习 · 下一篇**：[[python算术|Python 算术运算符]]。
- **自查**：`10_000` 和 `10000` 的值相同吗？
