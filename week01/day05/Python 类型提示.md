# Python 类型提示（Type Hints）

类型提示的作用不是“限制 Python 变量只能是什么类型”，而是**告诉人和工具：这里预计应该是什么类型。**

Python 仍然是动态类型语言。

## 1. 最基本的写法

```python
def greet(name: str) -> str:
    return f"Hello {name}"
```

这里：

```text
name: str  → 希望 name 是字符串
-> str     → 希望函数返回字符串
```

但 Python 运行时不会强制执行：

```python
greet(123)
```

这段代码仍然可能运行。

所以类型提示更像：

```text
代码说明书 + IDE 提示 + 静态检查依据
```

## 2. 变量也可以写类型提示

```python
name: str = "Tom"
age: int = 18
price: float = 9.9
active: bool = True
```

通常简单变量不必强行写，函数参数和返回值更值得标注。

## 3. 容器类型

现代 Python 常直接写：

```python
names: list[str] = ["Tom", "Alice"]
scores: dict[str, int] = {"Tom": 78}
skills: set[str] = {"Python", "Git"}
point: tuple[int, int] = (10, 20)
```

意思分别是：

```text
list[str]       → 字符串列表
dict[str, int]  → key 是字符串，value 是整数
set[str]        → 字符串集合
tuple[int, int] → 两个整数构成的元组
```

## 4. 一个参数允许多种类型

Python 3.10+ 可以写：

```python
def add(x: int | float, y: int | float) -> int | float:
    return x + y
```

意思是：

```text
x 可以是 int 或 float
y 可以是 int 或 float
```

## 5. 可能返回 `None`

```python
def find_user(name: str) -> str | None:
    ...
```

表示：

```text
可能返回 str
也可能返回 None
```

这种写法在后端代码里非常常见。

## 6. 函数没有返回值

```python
def log(message: str) -> None:
    print(message)
```

`-> None` 表示这个函数主要做事情，而不是返回业务结果。

## 7. 静态类型检查工具

像 `mypy`、Pyright、Pylance 之类的工具可以根据类型提示提前发现问题。

例如：

```python
def greet(name: str) -> str:
    return f"Hello {name}"

greet(123)
```

Python 运行时未必阻止，但静态检查工具会提醒：

```text
这里期望 str，却传入了 int
```

## 8. 为什么以后做 FastAPI 很重要

类型提示在 FastAPI 中不是装饰品。

例如：

```python
def get_user(user_id: int) -> dict:
    ...
```

框架、IDE、数据校验工具都能利用这些类型信息。

所以现在不要求背完 `typing` 模块，而是先建立这个直觉：

> 类型提示是在给代码写“接口说明”。

## 当前阶段记住

```python
name: str
age: int

def func(x: int) -> str:
    ...
```

以及：

```text
类型提示不会让 Python 变成静态类型语言
它主要帮助阅读、IDE、检查工具和框架理解代码
```

目前不用急着背复杂的 `Literal`、`Final`、`TypeAlias` 等写法，后面遇到真实项目再补。