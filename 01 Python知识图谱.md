---
tags:
  - python/导航
---

# Python 知识图谱

返回 [[00 Python学习导航]]。

```mermaid
flowchart TD
    A[基础语法 / 变量 / 类型] --> B[if / for / while]
    B --> C[函数与参数]
    C --> D[list / tuple]
    D --> E[dict / set]
    D --> F[切片 / 解包 / 推导式]
    F --> G[sort / sorted / map / filter / reduce]
    C --> H[*args / **kwargs]
    C --> I[类型提示]
    B --> J[异常处理]
    J --> K[try / except / else / finally]
    C --> L[模块 / 包]
    A --> M[f-string / 转义 / raw string]
    J --> N[文件读写]
    N --> O[文本 / CSV / pathlib / os]
    L --> P[pip / PyPI]
    P --> Q[venv / 项目依赖]
    C --> R[面向对象]
    R --> S[class / object / self / __init__]
    S --> T[继承 / super / 重写]
    O --> U[真实 Python 项目]
    Q --> U
    T --> U
    U --> V[HTTP / FastAPI / 数据库 / LLM]
```

## 稳定问题映射

```text
遍历数据         → for
筛选数据         → if / filter / 推导式
转换数据         → 表达式 / map
排序数据         → sort / sorted
累计结果         → 累加器 / reduce
键值对应         → dict
去重与集合关系   → set
不固定位置参数   → *args
不固定关键字参数 → **kwargs
运行时失败       → try / except
拆分代码         → module / package
第三方依赖       → pip
项目隔离         → venv
外部数据         → 文件 / CSV / JSON
路径操作         → pathlib / os
对象建模         → class
```

## Day05 主线

[[week01/day05/Day05 函数参数、异常与模块|Day05 函数参数、异常与模块]]

```text
函数参数
→ *args / **kwargs / 解包
→ 异常处理
→ 模块 / 包
→ 类型提示
```

## Day06 主线

[[week01/day06/Day06 文件处理、环境与面向对象|Day06 文件处理、环境与面向对象]]

```text
f-string / raw string
→ 文件读写
→ CSV
→ pathlib / os
→ pip / venv
→ class / object
→ inheritance
```

## OOP 快速映射

```text
class       → 类 / 模板
object      → 对象 / 实例
__init__    → 初始化实例
self        → 当前实例
attribute   → 属性
method      → 方法
inheritance → 继承
super()     → 调用父类实现
override    → 方法重写
```

到 Day06 为止，Python 基础骨架已经够用了。接下来判断标准应该从“有没有看过这个语法”变成：

> 实际问题出现时，我能不能知道该用哪个工具？