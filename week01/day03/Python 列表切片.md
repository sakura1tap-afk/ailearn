---
aliases:
  - "Python 列表切片"
tags:
  - python/序列
week: week01
day: day03
review_order: 27
---

# Python 列表切片

> [!abstract] 本篇重点
> **`items[start:stop:step]` 提取子列表；切片赋值可以修改原列表。**
>
> 前置知识：[[Python 列表|Python 列表]]、[[python字符串|Python 字符串]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python 列表切片符号入门

[列表](https://www.pythontutorial.net/python-basics/python-list/)支持切片符号，允许你从列表中获得子列表：

```python
sub_list = list[begin: end: step]
```
## 基础 Python 列表切片示例

假设你有以下字符串列表：

```python
colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']
```

以下示例使用列表切片从列表中获取子列表：`colors`

```python
colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']
sub_colors = colors[1:4]

print(sub_colors)
```

输出：

```text
['orange', 'yellow', 'green']
```

## 从列表中获取前 n 个元素

要从列表中获得 前 n 个 元素，省略第一个参数：

```python
list[:n]
```

以下示例返回包含颜色列表前三个元素的列表：

```python
colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']
sub_colors = colors[:3]

print(sub_colors)
```

输出：

```text
['red', 'orange', 'yellow']
```
注意 `colors[:3]`等价于 `colors[0:3]`

## 从列表中提取最后 n 个元素

要获得列表的 n 个后面元素，使用负索引。

例如，以下返回包含列表后三个元素的列表：`colors`

```python
colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']
sub_colors = colors[-3:]

print(sub_colors)
```

输出：

```text
['blue', 'indigo', 'violet']
```

## 从列表中检索每n个元素

```python
colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']
sub_colors = colors[::2]

print(sub_colors)
```

输出：

```text
['red', 'yellow', 'blue', 'violet']
```

## 逆转列表

这里使用 `[::-1]`，以步长 `-1` 从后向前取出元素，得到顺序反转的新列表。请参见以下示例：

```python
colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']
reversed_colors = colors[::-1]

print(reversed_colors)
```

## 替换列表的一部分

除了提取列表的一部分外，列表切片还允许你更改列表元素。

以下示例将颜色列表中的前两个元素更改为新的值：

```python
colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']
colors[0:2] = ['black', 'white']

print(colors)
```
## 删除元素

以下展示了如何使用列表切片删除列表中的第3、4和5个元素：`colors`

```python
colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet']
del colors[2:5]

print(colors)
```

## 摘要

- 使用列表切片从列表中提取子列表并修改该列表。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-list-slice/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[Python 中解包列表|Python 序列解包]]。
- **按顺序复习 · 下一篇**：[[For 循环|Python for 遍历列表与 enumerate]]。
- **自查**：`items[:3]`、`items[-3:]`、`items[::-1]` 分别做什么？
