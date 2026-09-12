# Python 模块（module）

一个 `.py` 文件就可以看成一个 Python 模块。

例如：

```text
pricing.py
```

模块名就是：

```text
pricing
```

模块的意义是把代码按功能拆开，避免所有函数、变量都堆在一个文件里。

## 示例

`pricing.py`：

```python
def get_net_price(price, tax_rate):
    return price * (1 + tax_rate)
```

`main.py`：

```python
import pricing

result = pricing.get_net_price(100, 0.1)
print(result)
```

这里：

```text
pricing                  → 模块
pricing.get_net_price()  → 调用模块里的函数
```

## 常见导入方式

### 导入整个模块

```python
import pricing

pricing.get_net_price(...)
```

优点是来源清楚，看到 `pricing.xxx` 就知道函数来自哪个模块。

### 只导入需要的对象

```python
from pricing import get_net_price

get_net_price(...)
```

### 起别名

```python
from pricing import get_net_price as calculate_price
```

也可以给模块起别名：

```python
import numpy as np
```

## 不推荐 `import *`

```python
from pricing import *
```

这种写法会把很多名字直接放进当前文件，容易产生名称冲突，也不容易看出函数来自哪里。

实际项目中尽量显式导入。

## 导入模块时会发生什么

第一次导入模块时，Python 会执行该模块顶层代码。

因此模块通常把“真正运行程序”的代码放进：

```python
if __name__ == "__main__":
    ...
```

例如：

```python
def add(a, b):
    return a + b


if __name__ == "__main__":
    print(add(1, 2))
```

直接运行这个文件时，测试代码会执行；被其他文件 `import` 时不会执行这部分。

## 什么时候开始需要模块

代码只有几十行时，一个文件还能看。

项目变大后通常会按职责拆分：

```text
main.py        程序入口
config.py      配置
database.py    数据库相关
models.py      数据结构
services.py    业务逻辑
```

以后做 FastAPI、RAG、Agent 项目时，模块化会非常常见。

## 记忆

```text
模块 = 一个承担某类功能的 .py 文件
import = 把其他模块中的代码拿来使用
```

当前阶段重点会写 `import module` 和 `from module import name` 即可。