# Python 类型提示（type hints）

Python 是动态类型语言，但可以给变量、参数和返回值添加**类型提示**，帮助人、IDE、静态检查工具和框架理解代码。

```python
def greet(name: str) -> str:
    return f"Hello, {name}"
```

这里：

```text
name: str → 参数预期是字符串
-> str    → 函数预期返回字符串
```

## 类型提示不会强制运行时类型

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

print(greet(123))
```

Python 本身不一定会因为传入 `123` 就拒绝运行。

所以类型提示更像：

> 一份机器也能读懂的代码说明书。

## 常见写法

### 基础类型

```python
name: str = "Tom"
age: int = 18
price: float = 19.9
active: bool = True
```

### 函数参数和返回值

```python
def add(a: int, b: int) -> int:
    return a + b
```

没有返回值：

```python
def log(message: str) -> None:
    print(message)
```

### 容器类型

现代 Python 常直接写：

```python
names: list[str] = ["Tom", "Alice"]
scores: dict[str, int] = {"Tom": 78}
tags: set[str] = {"python", "git"}
point: tuple[int, int] = (10, 20)
```

### 一个值可能有多种类型

Python 3.10+：

```python
def parse(value: int | float) -> float:
    return float(value)
```

一个值可能是字符串，也可能是 `None`：

```python
def find_user(user_id: int) -> str | None:
    ...
```

这种写法以后在 FastAPI、Pydantic、数据库代码中会非常常见。

## 静态类型检查

像 `mypy`、Pyright/Pylance 这类工具可以根据类型提示提前发现问题。

例如：

```python
def add(a: int, b: int) -> int:
    return a + b

add("1", 2)
```

静态检查工具会提醒：第一个参数应该是 `int`。

## 为什么 AI / 后端开发里很重要

类型提示能让这些东西更清楚：

```text
函数需要什么输入
函数会返回什么
API 请求和响应的数据结构
配置对象的字段类型
IDE 自动补全
框架自动生成校验和文档
```

FastAPI 就大量依赖类型提示来理解接口参数。

## 当前阶段先掌握这些

```python
name: str
count: int
items: list[str]
data: dict[str, int]
value: str | None

def func(x: int) -> str:
    ...
```

暂时不用急着深挖 `TypeVar`、`Protocol`、泛型等高级类型系统。

## 记忆

```text
类型提示 = 给变量和函数标注“预期是什么类型”

它主要帮助：
人 + IDE + 静态检查器 + 框架
```

它不是 Python 运行时的强制类型限制。