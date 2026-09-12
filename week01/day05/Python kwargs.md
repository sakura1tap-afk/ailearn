# Python `**kwargs`

`**kwargs` 用来让函数接收**任意数量的关键字参数**。

```python
def show_user(**kwargs):
    print(kwargs)

show_user(name="Tom", age=18)
```

输出：

```python
{'name': 'Tom', 'age': 18}
```

在函数内部，`kwargs` 是一个字典 `dict`。

## 什么时候用

当你不知道调用者会传多少个“名称=值”参数时，可以使用 `**kwargs`。

```python
def create_user(**kwargs):
    for key, value in kwargs.items():
        print(key, value)
```

调用：

```python
create_user(name="Alice", age=20, city="Beijing")
```

## 和普通参数一起使用

```python
def send_message(message, **kwargs):
    print(message)
    print(kwargs)

send_message("hello", user="Tom", urgent=True)
```

此时：

```text
message = "hello"
kwargs = {"user": "Tom", "urgent": True}
```

## 调用函数时的 `**`

定义函数时：

```python
def func(**kwargs):
```

`**` 表示把多个关键字参数**收集成字典**。

调用函数时：

```python
config = {
    "host": "localhost",
    "port": 8000
}

func(**config)
```

`**` 表示把字典**解包成关键字参数**。

例如：

```python
def connect(host, port):
    print(host, port)

config = {"host": "localhost", "port": 8000}
connect(**config)
```

等价于：

```python
connect(host="localhost", port=8000)
```

## `*args` 和 `**kwargs` 对比

```text
*args    → 不定数量的位置参数 → tuple
**kwargs → 不定数量的关键字参数 → dict
```

常见组合：

```python
def func(a, *args, **kwargs):
    ...
```

当前阶段重点不是强行使用它们，而是能看懂第三方库、框架和别人写的函数签名。