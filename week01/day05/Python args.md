**总结**：在本教程中，你将学习 Python 参数以及如何用它们来定义变量函数。`*args`

Python 对函数参数使用了同样的概念。例如：

```python
def add(x, y, *args):
    total = x + y
    for arg in args:
        total += arg

    return total


result = add(10, 20, 30, 40)
print(result)
```

输出：

```python
100
```

## Python *args 参数介绍[](https://www.pythontutorial.net/python-basics/python-args/#introduction-to-the-python-args-parameter "Anchor for Introduction to the Python *args parameter")

当函数前置参数为星号（）时，它可以接受变量数的参数。你可以向参数传递零个、一个或多个参数。`*``*args`

在 Python 中，这些参数 like 被称为变数参数。具有变数参数的函数称为变动函数。`*args`

注意，你不需要为变动参数命名。例如，你可以使用任何有意义的名称，如 、 、 、 等。`args``*numbers``*strings``*lists`

然而，按照惯例，Python 使用变异参数。`*args`

让我们来看一下下面的例子：

```python
def add(*args):
    print(args)

add()
```

输出：

```python
()
```

以下展示了论元的类型及其内容：`args`

```python
def add(*args):
    print(type(args))
    print(args)

add()
```

输出

```python
<class 'tuple'>
()
```

由于我们不向函数传递任何参数，输出显示一个空元组。`add()`

以下函数传递三个参数：`add()`

```python
def add(*args):
    print(args)


add(1,2,3)
```
输出：

```python
(1, 2, 3)
```

另外，你还需要用[`for`循环](https://www.pythontutorial.net/python-basics/python-for-loop-list/)来遍历元组的元素。

以下展示了如何将该元组的所有数字加到函数中：`args``add()`

```python
def add(*args):
    total = 0
    for arg in args:
        total += arg
    return total


total = add(1, 2, 3)
print(total)
```


输出：

```python
6
```

## Python *args 参数穷尽了位置参数[](https://www.pythontutorial.net/python-basics/python-args/#python-args-argument-exhausts-positional-arguments "Anchor for Python *args argument exhausts positional arguments")

如果你使用该论证，就不能添加更多的立场论证。不过，你可以使用[关键词参数](https://www.pythontutorial.net/python-basics/python-keyword-arguments/)。`*args`

以下示例因参数后方使用位置论元而产生错误：`*arg`

```python
def add(x, y, *args, z):
    return x + y + sum(args) + z


add(10, 20, 30, 40, 50)
```
错误：

```python
TypeError: add() missing 1 required keyword-only argument: 'z'
```
要解决这个问题，你需要在参数后面使用[关键词](https://www.pythontutorial.net/python-basics/python-keyword-arguments/)参数，具体如下：`*args`

```python
def add(x, y, *args, z):
    return x + y + sum(args) + z


result = add(10, 20, 30, 40, z=50)
print(result)
```
输出：

```python
150
```

## 拆解论证[](https://www.pythontutorial.net/python-basics/python-args/#unpacking-arguments "Anchor for Unpacking arguments")

下文函数接受两个参数，返回一个坐标为x和y坐标的点的字符串表示：`point`

```python
def point(x, y):
    return f'({x},{y})'
```

如果你把元组传递给函数，会出现错误：`point`

```python
a = (0, 0)
origin = point(a)
```

错误：

```python
TypeError: point() missing 1 required positional argument: 'y'
```

要解决这个问题，你需要在元组前加上如下操作符：`a``*`

```python
def point(x, y):
    return f'({x},{y})'


a = (0, 0)
origin = point(*a)
print(origin)
```


输出：

```python
(0,0)
```


当参数前加上运算符 时，Python 会解包元组并将其元素分配到 和 参数。`a``*``x``y`

## 摘要[](https://www.pythontutorial.net/python-basics/python-args/#summary "Anchor for Summary")

- 对于接受变量数的函数，使用Python参数。`*arg`
- 该论证耗尽了位置论元，因此你只能在它之后使用关键词论元。`*args`