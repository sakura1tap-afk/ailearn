# Python 私有函数约定

Python 没有像某些语言那样严格的 `private` 函数机制。

实际开发中，通常用**下划线前缀**表示：

> 这个函数是模块内部使用的，不建议外部直接调用。

例如：

```python
def send(email, message):
    print(f"send to {email}: {message}")


def _attach_file(filename):
    print(f"attach: {filename}")
```

这里：

```text
send()         → 对外使用的函数
_attach_file() → 内部辅助函数
```

## 下划线不是强制权限

即使函数名以 `_` 开头，其他模块仍然可以显式访问：

```python
import mail

mail._attach_file("a.txt")
```

Python 不会阻止你这么做。

所以 `_name` 更准确的含义是：

> 这是内部实现细节，请不要依赖它。

这是一种约定，不是真正的访问控制。

## `__all__`

模块可以定义：

```python
__all__ = ["send"]
```

它主要影响：

```python
from mail import *
```

哪些名字会被导入。

例如：

```python
__all__ = ["send"]


def send():
    ...


def attach_file():
    ...
```

使用：

```python
from mail import *
```

时只会导入 `send`。

但这同样**不会让 `attach_file()` 变成真正不可访问的私有函数**。

## 实际项目怎么做

当前阶段记住：

```text
普通函数名   → 对外可用
_函数名      → 内部实现，外部尽量别用
__all__      → 控制 import * 暴露哪些名字
```

另外，实际开发通常不推荐大量使用：

```python
from module import *
```

所以 `__all__` 目前了解即可。

真正重要的是养成 `_helper()` 表示内部辅助函数的阅读习惯。