---
aliases:
  - "Python 关键字参数"
tags:
  - python/函数
week: week01
day: day02
review_order: 22
---

# Python 关键字参数

> [!abstract] 本篇重点
> **调用时用 `参数名=值` 指明含义。**
>
> 前置知识：[[Python 函数|Python 函数]]、[[Python 默认参数|Python 默认参数]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

以下调用 `get_net_price()`，根据原价 `100` 和折扣 `10%` 计算折后价格：

```python
def get_net_price(price, discount):
    return price * (1-discount)

net_price = get_net_price(100, 0.1)
print(f'{net_price: .2f}')
```

以下演示了如何使用关键字参数语法调用该函数：`get_net_price()`

```python
def get_net_price(price, discount):
    return price * (1-discount)

net_price = get_net_price(
    price=100, 
    discount=0.1
)

print(f'{net_price: .2f}')
```

## 摘要

- 使用Python关键字参数，使函数调用更易读、更直观，尤其是对接受多参数的函数。
- 普通调用中，位置参数放在关键字参数之前；这里暂不讨论 `*args`、`**kwargs` 解包。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-keyword-arguments/)

## 知识链与自查

- **按顺序复习 · 上一篇**：[[Python 默认参数|Python 默认参数]]。
- **按顺序复习 · 下一篇**：[[Python 函数文档字符串|Python 函数文档字符串]]。
- **自查**：能把位置参数调用改成关键字参数调用吗？
