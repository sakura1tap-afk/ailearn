## Python 类型提示介绍[](https://www.pythontutorial.net/python-basics/python-type-hints/#introduction-to-python-type-hints "Anchor for Introduction to Python type hints")

一些编程语言具有静态类型，如C/C++。这意味着你需要事先声明函数的变量类型、参数和返回值。预定义类型允许编译器在编译和运行程序前检查代码。

Python 使用动态类型，函数的变量、参数和返回值可以是任意类型。此外，变量类型在程序运行过程中可能会变化。

一般来说，动态类型使编程变得简单，并引发了只有程序运行后才能发现的意外错误。

Python 的类型提示为你提供了可选的静态类型，以充分利用静态和动态类型的最佳优势。
除了类型外，你还可以使用其他内置类型，如 、 、 和 来进行类型提示。`str``int``float``bool``bytes`

需要注意的是，Python 解释器完全忽略类型提示。如果你把数字传递给函数，程序将不会有任何警告或错误地运行：`say_hi()`

```python
def say_hi(name: str) -> str:
    return f'Hi {name}'


greeting = say_hi(123)
print(greeting)
```

[试试看吧](https://www.pythontutorial.net/playground/?q=ZGVmIHNheV9oaShuYW1lOiBzdHIpIC0%2BIHN0cjoKICAgIHJldHVybiBmJ0hpIHtuYW1lfScKCgpncmVldGluZyA9IHNheV9oaSgxMjMpCnByaW50KGdyZWV0aW5nKQ%3D%3D)

输出：

```python
Hi 123
```

要检查语法中的类型提示，你需要使用静态类型检查工具。

## 使用静态类型检查工具：mypy[](https://www.pythontutorial.net/python-basics/python-type-hints/#using-a-static-type-checker-tool-mypy "Anchor for Using a static type checker tool: mypy")

Python 没有官方的静态类型检查工具。目前，最受欢迎的第三方工具是Mypy。由于Mypy是第三方软件包，你需要使用以下命令安装它：`pip`

```python
pip instal mypy
```

安装后，你可以用以下命令在运行程序前检查类型：`mypy`

```python
mypy app.py
```

它会显示以下信息：

```python
app.py:5: error: Argument 1 to "say_hi" has incompatible type "int"; expected "str"
Found 1 error in 1 file (checked 1 source file)
```
误差表明 的参数是，而期望类型是 。`say_hi``int``str`

如果你把参数改回字符串并再次运行，它会显示成功消息：`mypy`

```python
Success: no issues found in 1 source file
```
## 类型提示与类型推断[](https://www.pythontutorial.net/python-basics/python-type-hints/#type-hinting-type-inference "Anchor for Type hinting & type inference")

在定义变量时，你可以添加类似这样的类型提示：

```python
name: str = 'John'
```

变量的类型为。如果你给变量赋予一个非字符串的值，静态类型检查器会报错。例如：`name``str``name`

```python
name: str = 'Hello'
name = 100
```
错误：

```python
app.py:2: error: Incompatible types in assignment (expression has type "int", variable has type "str")
Found 1 error in 1 file (checked 1 source file)
```

在变量中添加类型是不必要的，因为静态类型检查器通常可以根据分配给变量的值推断类型。

在这个例子中，名称的值是字面字符串，静态类型检查器会推断出名称变量的类型为str。例如：

```python
name = 'Hello'
name = 100
```

它会报同样的错误

## 为多种类型添加类型提示[](https://www.pythontutorial.net/python-basics/python-type-hints/#adding-type-hints-for-multiple-types "Anchor for Adding type hints for multiple types")

以下函数返回两个数字的和：`add()`

```python
def add(x, y):
    return x + y
```

这些数字可以是整数或浮点数。你可以用这个模块为多种类型设置类型提示。

首先，从模块导入：`Union``typing`

```python
from typing import Union
```

其次，使用并集类型，包含 和：`Union``int``float`

```python
def add(x: Union[int, float], y: Union[int, float]) -> Union[int, float]:
    return x + y
```

以下是完整的源代码：

```python
from typing import Union


def add(x: Union[int, float], y: Union[int, float]) -> Union[int, float]:
    return x + y
```

从 Python 3.10 开始，你可以使用 X |用Y语法创建联合类型，例如：

```python
def add(x: int | float, y: int | float) -> int | float:
    return x + y
```
## 类型别名[](https://www.pythontutorial.net/python-basics/python-type-hints/#type-aliases "Anchor for Type aliases")

Python 允许你为类型分配别名，并用别名作为类型提示。例如：

```python
from typing import Union

number = Union[int, float]


def add(x: number, y: number) -> number:
    return x + y
```

在这个例子中，我们赋予类型别名，并在add（）函数中使用别名。`Union[int, float]``Number``Number`
## 为列表、词典和集合添加类型提示[](https://www.pythontutorial.net/python-basics/python-type-hints/#adding-type-hints-for-lists-dictionaries-and-sets "Anchor for Adding type hints for lists, dictionaries, and sets")

您可以使用以下内置类型来设置[列表](https://www.pythontutorial.net/python-basics/python-list/)、[字典](https://www.pythontutorial.net/python-basics/python-dictionary/)[的类型](https://www.pythontutorial.net/python-basics/python-set/)提示，并设置：

- 列表
- dict
- 场景

如果你在变量中输入提示作为列表，但后来为它分配字典，你会收到错误：

```python
ratings: list = [1, 2, 3]
ratings = {1: 'Bad', 2: 'average', 3: 'Good'}
```

错误：

```python
app.py:3: error: Incompatible types in assignment (expression has type "Dict[int, str]", variable has type "List[Any]")
Found 1 error in 1 file (checked 1 source file)
```

要指定列表、字典和集合中的值类型，您可以使用类型别名（type aliases）来自类型模块：

|类型别名|内置类型|
|---|---|
|列表|列表|
|元组|元组|
|裁决|dict|
|赛场|场景|
|冰封|冰封|
|序列|适用于列表、元组及任何其他序列数据类型。|
|制图|对于字典（dict）、set、frozenset 以及任何其他映射数据类型|
|字节串|字节、字节阵列和内存视图类型。|

例如，以下定义了一个整数列表：

```python
from typing import List

ratings: List[int] = [1, 2, 3]
```
## 无类型[](https://www.pythontutorial.net/python-basics/python-type-hints/#none-type "Anchor for None type")

如果函数没有显式返回某个值，你可以用 None 来输入提示返回值。例如：

```python
def log(message: str) -> None:
    print(message)
```

## 字面类型[](https://www.pythontutorial.net/python-basics/python-type-hints/#literal-types "Anchor for Literal Types")

如果你想允许某个变量或函数参数接受特定的文字值列表，可以使用类型。例如：

```python
from typing import Literal

def set_mode(mode: Literal['read', 'write']) -> None:
    print(f"Setting mode to {mode}")

set_mode('write')
```

## 最终变量[](https://www.pythontutorial.net/python-basics/python-type-hints/#final-variables "Anchor for Final variables")

你可以给最终变量分配一次值。如果你再次赋予一个值，就会出现错误。最后变量帮助你防止常数的意外更改。例如：

```abap
from typing import Final

HTTPS : Final[bool] = True

print(HTTPS )
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-type-hints/#summary "Anchor for Summary")

- 使用类型提示和静态类型检查工具，让你的代码更稳健。