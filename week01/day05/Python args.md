# Python `*args`

`*args` 用来解决一个很实际的问题：**函数参数数量不固定时，怎么接住这些额外的位置参数。**

## 1. 先看普通参数

```python
def add(x, y):
    return x + y
```

这个函数只能正常接收两个位置参数：

```python
add(1, 2)
```

如果你希望它还能接受 3 个、4 个、5 个参数，就可以使用 `*args`。

## 2. `*args` 会把额外的位置参数收集成元组

```python
def add(*args):
    print(args)

add(1, 2, 3)
```

输出：

```text
(1, 2, 3)
```

所以在函数内部：

```text
args 是一个 tuple（元组）
```

可以正常遍历：

```python
def add(*args):
    total = 0
    for num in args:
        total += num
    return total
```

## 3. 普通参数和 `*args` 可以一起用

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

此时：

```text
x = 10
y = 20
args = (30, 40)
```

## 4. `*args` 后面的参数通常要用关键字传递

```python
def add(x, *args, z):
    return x + sum(args) + z
```

正确调用：

```python
add(10, 20, 30, z=40)
```

这里 `z` 是 keyword-only argument（仅关键字参数）。

## 5. `*` 也可以用于调用函数时解包

```python
def point(x, y):
    return f"({x}, {y})"

position = (10, 20)
print(point(*position))
```

相当于：

```python
point(10, 20)
```

所以要区分两个场景：

```text
定义函数：*args     → 收集多个位置参数
调用函数：*some_data → 把序列拆开传进去
```

## 6. 什么时候会用到

例如一个日志函数可能接受任意数量的信息：

```python
def log(*messages):
    for message in messages:
        print(message)
```

或者包装另一个函数时，不确定调用方会传多少参数。

## 当前阶段记住

```text
*args = 多出来的位置参数
函数内部 args 是 tuple
```

名字 `args` 只是惯例，真正关键的是前面的 `*`。