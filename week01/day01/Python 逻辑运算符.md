---
aliases:
  - "Python 逻辑运算符"
tags:
  - python/基础
week: week01
day: day01
review_order: 12
---

# Python 逻辑运算符

> [!abstract] 本篇重点
> **组合条件用 `and`、`or`、`not`；优先级为 `not > and > or`。**
>
> 前置知识：[[python比较|Python 比较运算符]]、[[python布尔|Python 布尔值与真值判断]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

Python 有三个逻辑运算符：

- `and`
- `or`
- `not`

## and（与）
下表展示了将两种条件结合时运算符的结果：`and`

| a | b | a and b |
| ----- | ----- | ------- |
| True | True | True |
| True | False | False |
| False | False | False |
| False | True | False |

当 `a`、`b` 都是布尔值时，只有两者都为 `True`，`a and b` 才为 `True`。

## or（或）
下表展示了将两种条件结合时运算符的结果：`or`

| a | b | a or b |
| --- | --- | --- |
| True | True | True |
| True | False | True |
| False | True | True |
| False | False | False |
当两个条件都为假时，`a or b` 才为 `False`（本表中的 a、b 为布尔值）。

## not（非）

该操作符适用于一个条件。它会反转该条件的结果

| a | not a |
| ----- | ----- |
| True | False |
| False | True |

## 逻辑运算符的优先顺序

| Operator | Precedence |  |
| -------------------- | ---------- | ------------------------ |
| not | High |  |
| and | Medium |  |
| or | Low |  |
|  |  |  |
| `a or b and c` | means | `a or (b and c)` |
| `a and b or c and d` | means | `(a and b) or (c and d)` |
| `a and b and c or d` | means | `((a and b) and c) or d` |
| `not a and b or c` | means | `((not a) and b) or c` |
## 摘要

- 使用逻辑运算符组合多种条件。
- Python 有三个逻辑运算符：`and`、`or`、`not`。
- 逻辑运算符的优先级从高到低：`not`、`and`、`or`。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-logical-operators/)

> [!note] 理解补充
> 上面的真值表以布尔值为输入。一般情况下，`and`、`or` 返回某个操作数，不一定返回布尔值，例如 `0 or 5` 得到 `5`；`not` 总返回布尔值。参见 [Python 布尔运算](https://docs.python.org/3/library/stdtypes.html#boolean-operations-and-or-not)。

## 知识链与自查

- **学完可接着看**：[[python if语句|Python if 条件分支]]。
- **按顺序复习 · 上一篇**：[[python比较|Python 比较运算符]]。
- **按顺序复习 · 下一篇**：[[python if语句|Python if 条件分支]]。
- **自查**：能给混合 and/or 的条件加括号，说明实际顺序吗？
