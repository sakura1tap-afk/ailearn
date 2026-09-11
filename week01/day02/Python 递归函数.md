---
aliases:
  - "Python 递归函数"
tags:
  - python/函数应用
week: week01
day: day02
review_order: 37
---

# Python 递归函数

> [!abstract] 本篇重点
> **递归需要终止条件，并在每次调用时向终止条件推进。**
>
> 前置知识：[[Python 函数|Python 函数]]、[[python if语句|Python if 条件分支]]、[[Python三进制算符|Python 三元表达式（条件表达式）]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 递归函数介绍

递归函数是指调用自身直到不再调用的[函数](https://www.pythontutorial.net/python-basics/python-functions/)。

此外，递归函数需要有一个条件来停止调用自身。所以你需要添加一个类似这样的[if语句](https://www.pythontutorial.net/python-basics/python-if/)：

```python
def fn():
    # ...
    if condition:
        # stop calling itself
    else:
        fn()
    # ...
```

## Python 递归函数示例

假设你需要开发一个倒计时函数，从指定正整数倒数到 1（下面的代码不输出 0）。
当下一个数字变为 0 时停止递归。为此，添加如下条件：

```python
def count_down(start):
    """ Count down from a number  """
    print(start)

    # call the count_down if the next
    # number is greater than 0
    next = start - 1
    if next > 0:
        count_down(next)


count_down(3)
```

在这个例子中，函数只有在下一个数字大于零时才调用自己。换句话说，如果下一个数字为零，它就停止调用自己。`count_down()`

### 使用递归函数计算序列的和
要应用递归技术，你可以计算从1到n的序列之和，具体如下：

- sum（n） = n + sum（n-1）
- sum（n-1） = n-1 + sum（n-2）
- …
- sum（0） = 0

只要函数的参数大于零，函数就会持续调用自己。`sum()`

以下是该函数递归版本的定义：`sum()`

```python
def sum(n):
    if n > 0:
        return n + sum(n-1)
    return 0


result = sum(100)
print(result)
```
递归函数更短且更易读。

如果使用[三元表达式](https://www.pythontutorial.net/python-basics/python-ternary-operator/)，则会更简洁：`sum()`

```python
def sum(n):
    return n + sum(n-1) if n > 0 else 0


result = sum(100)
print(result)
```

## 摘要

- 递归函数是指调用自身直到不再调用的函数。
- 递归函数总有一个停止调用自身的条件。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-recursive-functions/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[Python的reduce（） 函数将列表简化为单一值|Python reduce 累积归约]]。
- **按顺序复习 · 下一篇**：[[今日练习|Day02 今日练习与错题复盘]]。
- **自查**：除了写终止条件，每次递归调用还必须改变什么？
