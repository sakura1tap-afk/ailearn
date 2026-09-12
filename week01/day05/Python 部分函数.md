# Python 部分函数 `partial`

部分函数（partial function）可以理解成：

> 先把一个函数的部分参数固定下来，得到一个更方便调用的新函数。

例如：

```python
def multiply(a, b):
    return a * b
```

如果经常需要“乘 2”，可以自己包一层：

```python
def double(a):
    return multiply(a, 2)
```

也可以用标准库 `functools.partial`：

```python
from functools import partial


def multiply(a, b):
    return a * b


double = partial(multiply, b=2)

print(double(10))  # 20
```

这里相当于提前固定：

```text
b = 2
```

所以以后调用 `double()` 时只需要提供 `a`。

## 再举一个实际例子

```python
from functools import partial


def request(url, timeout):
    print(url, timeout)


quick_request = partial(request, timeout=3)

quick_request("https://example.com")
```

如果很多请求都使用同样的 `timeout=3`，就不用每次重复写。

## 已固定的关键字参数可以覆盖

```python
double(10, b=3)
```

这次会使用 `b=3`，结果为：

```text
30
```

## 当前阶段需要掌握到什么程度

知道：

```python
from functools import partial
```

能把：

```python
func(a, b, c)
```

其中一部分参数提前固定，生成一个新的可调用对象，就够了。

它不是 Python 基础阶段的核心知识，也不用为了使用 `partial` 而使用。

很多时候，普通包装函数反而更直观：

```python
def double(x):
    return multiply(x, 2)
```

## 记忆

```text
partial = 预先固定部分参数 → 得到一个更简单的新函数
```

当前优先级低于异常处理、模块、包和 `*args/**kwargs`。