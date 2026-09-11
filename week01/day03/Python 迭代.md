---
aliases:
  - "Python 可迭代对象与迭代器"
tags:
  - python/序列
week: week01
day: day03
review_order: 30
---

# Python 可迭代对象与迭代器

> [!abstract] 本篇重点
> **`iter()` 获取迭代器，`next()` 取下一项；耗尽后不会自动重来。**
>
> 前置知识：[[For 循环|Python for 遍历列表与 enumerate]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## Python 可迭代对象简介

在 Python 中，可迭代对象（iterable）是能够通过 `iter()` 获取迭代器的对象，例如列表、字符串和 range 对象。

因此，你可以用[`for`循环](https://www.pythontutorial.net/python-basics/python-for-loop-list/)来遍历可迭代对象。

`range()` 返回的 range 对象是可迭代对象：

```python
for index in range(3):
    print(index)
```
此外，[字符串是可](https://www.pythontutorial.net/python-basics/python-string/)迭代的，因为你可以用[for循环](https://www.pythontutorial.net/python-basics/python-for-range/)来遍历它：

```python
str = 'Iterables'
for ch in str:
    print(ch)
```
## 什么是迭代器

可迭代对象提供迭代器；迭代器（iterator）记录当前位置，并逐个产生元素。

要从可迭代对象得到迭代器，你使用函数。例如：`iter()`

```python
colors = ['red', 'green', 'blue']
colors_iter = iter(colors)
```

有了迭代器后，你可以用函数从迭代中得到下一个元素：`next()`

```python
colors = ['red', 'green', 'blue']
colors_iter = iter(colors)

color = next(colors_iter)
print(color)
```
如果没有其他元素，你调用`next()`，就会得到异常。

```python
colors = ['red', 'green', 'blue']
colors_iter = iter(colors)

color = next(colors_iter)
print(color)

color = next(colors_iter)
print(color)

color = next(colors_iter)
print(color)

# cause an excpetion
color = next(colors_iter)
print(color)
```
本示例首先展示了颜色列表中的三个元素，然后发出一个例外：

```python
red
green
blue
Traceback (most recent call last):
  File "iterable.py", line 15, in <module>
    color = next(colors_iter)
StopIteration
```
迭代器是有状态的：每次取值会推进当前位置；这不会删除原列表中的元素。

换句话说，一旦你对一个迭代器完成循环，迭代器就变成空了。如果你再迭代一次，它什么都不会返回。

由于你可以对迭代器进行迭代，迭代器也是一个可迭代对象。这确实让人很困惑。例如：

```python
colors = ['red', 'green', 'blue']
iterator = iter(colors)

for color in iterator:
    print(color)
```
输出：

```text
red
green
blue
```

如果你调用函数并传递迭代器，它会返回同样的迭代器。`iter()`

之后可以进一步学习如何创建自己的可迭代对象。

## 摘要

- 可迭代对象是可以被迭代的对象。迭代算法能够一次返回其一个元素。
- 迭代器是执行迭代的代理。它是有状态的。迭代器也是一个可迭代对象。
- 用 `iter()` 获取迭代器，用 `next()` 从迭代器取得下一项；耗尽后，不带默认值的 `next()` 会抛出 `StopIteration`。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-iterables/)

## 知识链与自查

- **学完可接着看**：[[Python map（） 函数转换列表元素|Python map 转换元素]]、[[Python中筛选列表元素|Python filter 筛选元素]]。
- **按顺序复习 · 上一篇**：[[查找列表中元素的索引|Python 列表查找与成员判断]]。
- **按顺序复习 · 下一篇**：[[Python Lambda表达式|Python lambda 表达式]]。
- **自查**：对同一个耗尽的迭代器再调用 list() 会得到什么？
