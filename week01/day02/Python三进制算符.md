---
aliases:
  - "Python 三元表达式（条件表达式）"
tags:
  - python/流程控制
week: week01
day: day02
review_order: 14
---

# Python 三元表达式（条件表达式）

> [!abstract] 本篇重点
> **`a if condition else b` 根据条件选择一个值。**
>
> 前置知识：[[python if语句|Python if 条件分支]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

以下是**Python中三元表达式**的基本语法：

```python
value_if_true if condition else value_if_false
```

先判断 `condition`：为真时取 `value_if_true`，否则取 `value_if_false`。

下面的 `if...else` 展示相同的分支选择过程；如果需要取得表达式的值，应在两个分支中分别赋值给同一个变量：

```python
if condition:
    value_if_true
else:
    value_if_false
```
## 摘要

- Python 的三元表达式是 。`value_if_true if condition else value_if_false`
- 使用三元表达式使代码更简洁。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-ternary-operator/)

## 知识链与自查

- **学完可接着看**：[[Python 递归函数|Python 递归函数]]。
- **按顺序复习 · 上一篇**：[[python if语句|Python if 条件分支]]。
- **按顺序复习 · 下一篇**：[[Python范围循环|Python for 与 range]]。
- **自查**：能把条件表达式改写成给变量赋值的 if/else 吗？
