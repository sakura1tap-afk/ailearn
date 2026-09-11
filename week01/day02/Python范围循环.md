---
aliases:
  - "Python for 与 range"
tags:
  - python/流程控制
week: week01
day: day02
review_order: 15
---

# Python for 与 range

> [!abstract] 本篇重点
> **`range(start, stop, step)` 不包含 stop；step 不能为 0。**
>
> 前置知识：[[python基础|Python 基础语法]]、[[python数字|Python 数字]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 带有range（）函数的Python循环语句简介
以下说明了循环的语法：`for`

```python
for index in range(n):
    statement
```

当 `n` 为正整数时，`range(n)` 表示从 `0` 到 `n - 1` 的整数序列，步长为 `1`，不包含 `n`。

下图展示了环路陈述：`for`

![Python for loop](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-for-loop.png)

### 指定序列的起始值

默认情况下，函数使用零作为序列的起始编号。`range()`

此外，该函数允许你指定起始编号如下：`range()`

```python
range(start, stop)
```

以下示例使用循环显示五个数字，从1到5显示到屏幕：`for`

```python
for index in range(1, 6):
    print(index)
```

### 指定序列的增量
要指定步长，使用 `range(start, stop, step)`：

```python
range(start, stop, step)
```

在这个形式中，你可以指定函数应增加的值。`range()`

下例展示了0到10的所有偶数：

```python
for index in range(0, 11, 2):
    print(index)
```

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-for-range/)

## 知识链与自查

- **学完可接着看**：[[Python break|Python break]]、[[Python continue|Python continue]]、[[For 循环|Python for 遍历列表与 enumerate]]。
- **按顺序复习 · 上一篇**：[[Python三进制算符|Python 三元表达式（条件表达式）]]。
- **按顺序复习 · 下一篇**：[[Python while|Python while 循环]]。
- **自查**：`list(range(1, 6, 2))` 是什么？
