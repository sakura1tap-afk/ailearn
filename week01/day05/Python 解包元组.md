# Python 元组与解包

## 元组怎么写

Python 元组主要由**逗号**决定：

```python
point = 10, 20
```

通常为了更清楚，会写成：

```python
point = (10, 20)
```

单元素元组要保留逗号：

```python
one = (1,)
```

而：

```python
(1)
```

只是整数 `1`。

## 什么是解包

解包就是把一组数据拆给多个变量：

```python
x, y = (10, 20)
```

结果：

```text
x = 10
y = 20
```

这也是你之前已经用过的：

```python
x, y = y, x
```

Python 会先计算右边，再分别赋值给左边。

## 数量必须匹配

```python
x, y = (10, 20, 30)
```

会报：

```text
ValueError: too many values to unpack
```

因为右边有 3 个值，左边只有 2 个变量。

如果某个值不需要，可以用 `_` 表示“这里我不关心”：

```python
x, _, z = (10, 20, 30)
```

`_` 本质上仍然是普通变量，只是 Python 社区习惯用它表示“这个值不用”。

## 扩展解包 `*`

如果想把剩下的值全部收集起来：

```python
first, *rest = (10, 20, 30, 40)
```

结果：

```text
first = 10
rest = [20, 30, 40]
```

注意：`rest` 得到的是列表。

也可以：

```python
first, *middle, last = (1, 2, 3, 4, 5)
```

结果：

```text
first = 1
middle = [2, 3, 4]
last = 5
```

一次解包赋值中只能有一个带 `*` 的变量。

## 你已经在字典遍历里用过解包

```python
scores = {
    "Tom": 78,
    "Alice": 95
}

for name, score in scores.items():
    print(name, score)
```

`scores.items()` 每次给出类似：

```python
("Tom", 78)
```

然后：

```python
name, score = ("Tom", 78)
```

这就是解包。

## 右侧的 `*`：拆开序列

```python
a = (1, 2, 3)
b = (4, 5, 6)

numbers = (*a, *b)
```

结果：

```python
(1, 2, 3, 4, 5, 6)
```

调用函数时也能用：

```python
def add(a, b):
    return a + b

nums = (10, 20)
add(*nums)
```

等价于：

```python
add(10, 20)
```

## 记忆

```text
左边 a, b = data → 把数据拆给变量
左边 *rest       → 收集剩余值
右边 *data       → 把序列拆开
```

当前阶段重点是看懂和会用，不需要把“元组解包”当成新的复杂体系。