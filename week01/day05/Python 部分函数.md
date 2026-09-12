把所有内容汇聚起来：

```python
def multiply(a, b):
    return a*b


def double(a):
    return multiply(a, 2)


result = double(10)
print(result)  # 20
```

该函数简化了函数的参数。`double``multiply`

该函数冻结了函数的第二个参数，从而生成一个签名更简单的新函数。`double``multiply`

换句话说，函数降低了函数的复杂性。`double``multiply`

在 Python 中，该函数称为**部分函数**。`double`

实际上，当你想减少函数的参数数量以简化函数的签名时，会使用部分函数。

因为你有时会创建部分函数，Python 会提供标准模块中的函数，帮助你更容易定义部分函数。`partial``functools`

## Functools 模块中的 Python 部分函数[](https://www.pythontutorial.net/python-basics/python-partial-functions/#python-partial-function-from-functools-module "Anchor for Python partial function from functools module")

以下展示了该模函数的语法：`partial``functools`

```python
functools.partial(fn, /, *args, **kwargs)
```

该函数返回新对象，该对象是[可调用](https://www.pythontutorial.net/python-built-in-functions/python-callable/)对象。`partial``partial`

当你调用对象时，Python 会调用带有位置参数和[关键词参数](https://www.pythontutorial.net/python-basics/python-keyword-arguments/)的函数。`partial``fn``args``[kwargs](https://www.pythontutorial.net/python-basics/python-kwargs/)`

下例展示了如何使用函数从函数定义函数：`partial``double``multiply`

```python
from functools import partial

def multiply(a, b):
    return a*b


double = partial(multiply, b=2)

result = double(10)
print(result)
```
输出：

```yaml
20
```

它是如何运作的。

- 首先，从模块导入函数。`partial``functools`
- 其次，定义函数。`multiply`
- 第三，从函数返回一个部分对象并将其赋值到变量上。`partial``double`

当你调用 时，Python 调用了参数默认为 的函数。`double``multiply``b``2`

如果你向部分对象传递更多参数，Python 会将它们附加到参数后面。`args`

当你向部分对象传递额外关键词参数时，Python 会扩展并覆盖这些参数。`kwargs`

因此，可以这样称呼：`double
```python
double(10, b=3)
```

在这个例子中，Python 调用参数值为 3 的函数，而不是 2。`multiply``b`

你会看到以下输出：

```yaml
30
```

## Python 部分函数与变量[](https://www.pythontutorial.net/python-basics/python-partial-functions/#python-partial-functions-and-variables "Anchor for Python partial functions and variables")

有时，你可能需要使用变量来创建部分变量。例如：

```python
from functools import partial


def multiply(a, b):
    return a*b


x = 2
f = partial(multiply, x)

result = f(10)  # 20
print(result)

x = 3
result = f(10)  # 20
print(result)
```


输出：

```yaml
20
20
```

在这个例子中，我们将 变为 并期望 返回 而不是 20。`x``3``f(10)``30`

然而，却被反弹了。这是因为Python在以下语句中评估了的值：`f(10)``20``x`

```python
f = partial(multiply, x)
```

…但之后则不变，因此当[引用](https://www.pythontutorial.net/advanced-python/python-references/)新数（），部分函数不变。`x``3`

## 摘要[](https://www.pythontutorial.net/python-basics/python-partial-functions/#summary "Anchor for Summary")

- 使用模块中的函数在 Python 中创建部分函数。`partial``functools`