# Python `*args`

`*args` 用来让函数接收**任意数量的位置参数**。

```python
def add(*args):
    total = 0
    for num in args:
        total += num
    return total

print(add(1, 2, 3))  # 6
```

在函数内部，`args` 是一个元组：

```python
def show(*args):
    print(type(args))
    print(args)

show(1, 2, 3)
# <class 'tuple'>
# (1, 2, 3)
```

## 什么时候用

当参数数量不固定时很方便，例如：

```python
def total_price(*prices):
    return sum(prices)
```

调用者可以传 0 个、1 个或多个位置参数。

## 和普通参数一起使用

```python
def add(x, y, *args):
    total = x + y
    for num in args:
        total += num
    return total
```

调用：

```python
add(10, 20, 30, 40)
```

其中：

```text
x = 10
y = 20
args = (30, 40)
```

## `*args` 后面的参数

`*args` 后面的普通参数必须使用关键字传入：

```python
def func(x, *args, mode):
    print(x, args, mode)

func(1, 2, 3, mode="debug")
```

这里的 `mode` 是**仅限关键字参数（keyword-only argument）**。

## 调用函数时的 `*`

定义函数时：

```python
def func(*args):
```

`*` 表示把多个位置参数**收集**起来。

调用函数时：

```python
values = (10, 20)
func(*values)
```

`*` 表示把序列**解包**成多个位置参数。

例如：

```python
def point(x, y):
    return f"({x}, {y})"

coords = (3, 5)
print(point(*coords))
```

等价于：

```python
point(3, 5)
```

## 记忆

```text
定义时 *args  → 收集位置参数 → tuple
调用时 *data  → 解包序列     → 多个位置参数
```

`args` 只是惯用名称，也可以写成 `*numbers`、`*values`。真正起作用的是前面的 `*`。