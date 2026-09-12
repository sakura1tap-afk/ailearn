# Day05｜函数参数、异常与模块

Day05 的知识看起来很多，但核心可以分成四组：

```text
函数参数增强
→ *args / **kwargs / 解包

异常处理
→ try / except / finally

代码组织
→ 模块 / 包 / 模块搜索路径 / 内部函数约定

代码可读性
→ 类型提示
```

`do...while` 模拟和 `partial` 属于补充知识，当前优先级较低。

## 1. `*args` 与 `**kwargs`

### `*args`

接收任意数量的**位置参数**，函数内部得到元组：

```python
def add(*args):
    return sum(args)

add(1, 2, 3)
```

```text
args = (1, 2, 3)
```

### `**kwargs`

接收任意数量的**关键字参数**，函数内部得到字典：

```python
def show(**kwargs):
    print(kwargs)

show(name="Tom", age=18)
```

```text
kwargs = {"name": "Tom", "age": 18}
```

最重要的对照：

```text
*args    → tuple
**kwargs → dict
```

定义函数时星号表示**收集参数**；调用函数时星号表示**解包数据**。

关联：[[Python args]]、[[Python kwargs]]、[[Python 解包元组]]

## 2. 异常处理

异常是程序运行时发生的问题，例如：

```text
ValueError
TypeError
KeyError
ZeroDivisionError
FileNotFoundError
```

基本结构：

```python
try:
    # 可能失败
except ValueError:
    # 失败后怎么处理
```

重点不是“把错误藏起来”，而是：

> 明确知道某一步可能失败，并规定失败后的处理方式。

`finally` 无论是否出现异常都会执行，常用于清理资源。

```python
try:
    ...
except SomeError:
    ...
finally:
    ...
```

关联：[[Python try…except]]、[[Python try…except…finally]]

## 3. 模块与包

### 模块 module

一个 `.py` 文件就是一个模块：

```text
pricing.py → pricing 模块
```

使用：

```python
import pricing
```

### 包 package

包用文件夹组织多个模块：

```text
app/
├─ main.py
├─ api/
├─ services/
└─ models/
```

当前阶段可以简单理解：

```text
.py 文件      → 模块
模块的文件夹  → 包
```

关联：[[Python 模块]]、[[Python 包]]

## 4. 模块搜索路径

`import` 并不是全硬盘乱找文件。

Python 会沿 `sys.path` 查找模块：

```python
import sys
print(sys.path)
```

以后遇到：

```text
ModuleNotFoundError
```

优先检查：

```text
模块是否存在
名字是否拼错
虚拟环境是否正确
依赖是否安装
项目目录结构是否正确
```

关联：[[Python 模块搜索路径]]

## 5. 内部函数约定

Python 没有严格的 `private` 函数。

以下划线开头通常表示“内部实现，不建议外部使用”：

```python
def _helper():
    ...
```

这是约定，不是权限限制。

关联：[[Python 私有函数]]

## 6. 类型提示

类型提示用于告诉人、IDE、检查工具和框架：输入和返回值预期是什么。

```python
def get_user(user_id: int) -> dict[str, str]:
    ...
```

常见写法：

```python
name: str
count: int
items: list[str]
data: dict[str, int]
value: str | None
```

Python 运行时通常不会自动强制这些类型。

以后 FastAPI 会大量使用类型提示。

关联：[[Python 类型提示]]

## 7. 补充知识

### 模拟 `do...while`

Python 没有原生 `do...while`，通常用：

```python
while True:
    ...
    if 结束条件:
        break
```

关联：[[Python do…while Loop Statement Emulation]]

### `partial`

提前固定函数的一部分参数，生成一个更方便调用的新函数：

```python
from functools import partial
```

当前了解即可。

关联：[[Python 部分函数]]

## 8. 当前优先级

建议按这个顺序掌握：

```text
★★★★★ try / except
★★★★★ 模块与 import
★★★★☆ *args / **kwargs
★★★★☆ 类型提示
★★★☆☆ 包与模块搜索路径
★★★☆☆ 解包
★★☆☆☆ 私有函数约定
★☆☆☆☆ do...while 模拟
★☆☆☆☆ partial
```

当前目标不是把每个特性都背下来，而是能够回答：

```text
这个语法解决什么问题？
什么时候我会想到使用它？
它产生的结果是什么类型？
```
