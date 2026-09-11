---
aliases:
  - "Python break"
tags:
  - python/流程控制
week: week01
day: day02
review_order: 17
---

# Python break

> [!abstract] 本篇重点
> **`break` 立即退出最内层循环。**
>
> 前置知识：[[Python范围循环|Python for 与 range]]、[[Python while|Python while 循环]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python break 语句简介

有时，你想提前终止[`for`循环](https://www.pythontutorial.net/python-basics/python-for-range/)或[`while`循环](https://www.pythontutorial.net/python-basics/python-while/)，无论条件测试结果如何。在这种情况下，你可以使用以下陈述：`break`

```python
break
```

## 在 for 循环中使用 break

以下展示了如何在 `for` 循环中使用 `break`：

```python
for index in range(n):
    # more code here 
    if condition:
        break
```

当 `condition` 为真时，`break` 立即终止该层循环，不再执行它剩余的迭代。

当你在嵌套循环中使用该语句时，它会终止最内层的循环。例如：
当你在嵌套循环中使用该语句时，它会终止最内层的循环。例如：`break`

```python
for x in range(5):
    for y in range(5):
        # terminate the innermost loop
        if y > 1:
            break
        # show coordinates on the screen
        print(f"({x},{y})")
```

输出：

```text
(0,0)
(0,1)
(1,0)
(1,1)
(2,0)
(2,1)
(3,0)
(3,1)
(4,0)
(4,1)
```

## 摘要

- 使用Python `break`语句提前终止for循环或while循环。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-break/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[Python while|Python while 循环]]。
- **按顺序复习 · 下一篇**：[[Python continue|Python continue]]。
- **自查**：嵌套循环里的 break 会退出几层？
