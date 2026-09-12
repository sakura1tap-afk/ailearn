# Python 包（package）

当项目里只有几个 `.py` 文件时，用模块就够了。

模块越来越多以后，可以把相关模块放进同一个文件夹，这个文件夹就可以作为一个 **包（package）** 来组织代码。

例如：

```text
project/
├─ main.py
└─ sales/
   ├─ __init__.py
   ├─ order.py
   ├─ delivery.py
   └─ billing.py
```

这里：

```text
sales            → 包
order.py         → 模块
sales.order      → 包里的模块
```

## 导入包里的模块

```python
import sales.order

sales.order.create_order()
```

或者：

```python
from sales.order import create_order

create_order()
```

## `__init__.py`

在常见项目结构中，包目录里通常会放一个：

```text
__init__.py
```

它可以：

- 明确表示这个目录是 Python 包。
- 放置包初始化代码。
- 控制包对外暴露哪些对象。

Python 3 也支持没有 `__init__.py` 的 namespace package（命名空间包），但当前学习和普通项目中，先按“包目录里有 `__init__.py`”理解即可。

## 子包

包里面还可以继续放文件夹：

```text
app/
├─ api/
│  ├─ routes/
│  └─ dependencies/
├─ services/
└─ models/
```

这些子目录可以继续作为子包组织代码。

## 模块和包的关系

```text
模块 module  → 一个 .py 文件
包 package   → 用文件夹组织多个模块/子包
```

可以把它理解成：

```text
文件   → 模块
文件夹 → 包
```

这个比喻足够应付当前阶段。

## 实际项目为什么需要包

以后一个后端项目可能有：

```text
app/
├─ main.py
├─ api/
├─ services/
├─ database/
├─ schemas/
└─ utils/
```

如果所有代码都塞进 `main.py`，很快就会变得难维护。

包的主要价值就是：**把不同职责的代码分类组织起来。**

## 关于 `import *`

尽量避免：

```python
from sales import *
```

实际开发更推荐显式写清楚你需要哪个模块或函数。

## 记忆

```text
.py 文件      → 模块
模块的文件夹  → 包
import        → 使用其他模块/包里的代码
```

当前阶段先建立目录结构和导入关系的直觉，不需要深挖 `__all__`。