---
aliases:
  - "Python sorted 返回新列表"
tags:
  - python/函数应用
week: week01
day: day03
review_order: 33
---

# Python sorted 返回新列表

> [!abstract] 本篇重点
> **`sorted()` 创建新的排序列表，原列表顺序保持不变。**
>
> 前置知识：[[Python 排序列表|Python list.sort 原地排序]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python sorted（） 函数介绍

作为对比，列表的 `sort()` 方法原地排序，会改变原始列表的顺序。

要从原始列表返回新的排序列表，可以使用以下函数：`sorted()`

```python
sorted(list)
```

`sorted()`不会修改原始列表。

默认情况下，`sorted()`使用[小于算符](https://www.pythontutorial.net/python-basics/python-comparison-operators/)（）从低到高排序列表中的元素。`<`

如果需要降序排列，传入 `reverse=True`：

```python
sorted(list,reverse=True)
```

## 摘要

- 使用 `sorted()`从列表中返回新的排序列表。
- 使用 `sorted(items, reverse=True)` 返回降序排列的新列表。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-sorted/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[Python 排序列表|Python list.sort 原地排序]]。
- **按顺序复习 · 下一篇**：[[Python map（） 函数转换列表元素|Python map 转换元素]]。
- **自查**：什么时候选择 sorted()，什么时候选择 list.sort()？
