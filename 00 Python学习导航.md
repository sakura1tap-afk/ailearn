---
tags:
  - python/导航
---

# Python 学习导航

这个仓库保留 `week/day` 作为真实学习时间线，同时提供更适合复习的知识入口。

当前进度：**Week01 / Day06**。已经从基础语法推进到 **文件处理、pip / venv、路径操作与面向对象基础**。

## 优先入口

- [[01 Python知识图谱]]：看知识之间怎么连接。
- [[02 易混概念与练习复盘]]：看容易犯的错误和当前薄弱点。
- [[week01/day03/Day03 列表与迭代|Day03 列表与迭代]]
- [[week01/day04/Day04 字典与集合|Day04 字典与集合]]
- [[week01/day05/Day05 函数参数、异常与模块|Day05 函数参数、异常与模块]]
- [[week01/day06/Day06 文件处理、环境与面向对象|Day06 文件处理、环境与面向对象]]

> [!tip] 学习原则
> 先弄清“这个东西解决什么问题”，再记语法。教程看完不是终点，能在小项目里主动想到并使用才算真正掌握。

## Day01｜基础语法

- [[python基础|Python 基础语法]]
- [[python变量|变量]]
- [[python数字|数字]]
- [[python字符串|字符串]]
- [[python布尔|布尔]]
- [[python比较|比较运算]]
- [[Python 逻辑运算符|逻辑运算]]
- [[类型转换|类型转换]]

## Day02｜流程控制、函数与列表

- [[python if语句|if 条件分支]]
- [[Python范围循环|for / range]]
- [[Python while|while]]
- [[Python break|break]] / [[Python continue|continue]] / [[Python pass|pass]]
- [[Python 函数|函数]]
- [[Python 默认参数|默认参数]]
- [[Python 关键词参数|关键字参数]]
- [[Python Lambda表达式|lambda]]
- [[Python 递归函数|递归]]
- [[Python 列表|列表]]
- [[week01/day02/今日练习|Day02 手写练习]]

## Day03｜序列、迭代与数据处理

- [[Python元组|元组]]
- [[Python 中解包列表|序列解包]]
- [[Python 列表切片|切片]]
- [[Python 列表解析|列表推导式]]
- [[For 循环|for / enumerate]]
- [[Python 迭代|可迭代对象与迭代器]]
- [[Python 排序列表|list.sort()]] / [[Python sorted|sorted()]]
- [[Python map（） 函数转换列表元素|map()]]
- [[Python中筛选列表元素|filter()]]
- [[Python的reduce（） 函数将列表简化为单一值|reduce()]]
- [[week01/day03/今日练习|Day03 手写练习]]

## Day04｜字典、集合与循环 else

- [[Python 词典|字典]]
- [[Python 词典理解|字典推导式]]
- [[Python 集合|集合]]
- [[Python 集合理解|集合推导式]]
- [[Python集合合并|并集]] / [[Python 集交集|交集]] / [[Python集合差集|差集]] / [[Python 对称差分|对称差]]
- [[Python issubset|子集]] / [[Python issuperset|超集]] / [[Python 不相交集|不相交]]
- [[Python for…else|for...else]] / [[Python while else|while...else]]
- [[week01/day04/今日练习|Day04 手写练习]]

## Day05｜函数参数、异常与模块

- [[week01/day05/Python args|*args]]
- [[week01/day05/Python kwargs|**kwargs]]
- [[week01/day05/Python 解包元组|解包]]
- [[week01/day05/Python try…except|try...except]]
- [[week01/day05/Python try…except…finally|finally]]
- [[week01/day05/Python 模块|模块]]
- [[week01/day05/Python 包|包]]
- [[week01/day05/Python 模块搜索路径|模块搜索路径]]
- [[week01/day05/Python 私有函数|内部函数约定]]
- [[week01/day05/Python 类型提示|类型提示]]

## Day06｜文件、环境与面向对象

先看：[[week01/day06/Day06 文件处理、环境与面向对象|Day06 文件处理、环境与面向对象]]

### 字符串

- [[week01/day06/Python F字符串|f-string]]
- [[week01/day06/Python 反斜线|转义字符]]
- [[week01/day06/Python 原始字符串|raw string]]

### 文件与目录

- [[week01/day06/Python 读取文本文件|读取文本文件]]
- [[week01/day06/Python 写文本文件|写文本文件]]
- [[week01/day06/Python 创建文本文件|创建文本文件]]
- [[week01/day06/Python 读取 CSV 文件|读取 CSV]]
- [[week01/day06/Python 写 CSV 文件|写 CSV]]
- [[week01/day06/Python 检查文件是否存在|检查文件是否存在]]
- [[week01/day06/如何在 Python 中操作目录|目录操作]]
- [[week01/day06/如何在 Python 中从目录中列出文件|列出目录文件]]
- [[week01/day06/如何在 Python 中删除文件|删除文件]]
- [[week01/day06/如何在 Python 中重命名文件|重命名文件]]

### 项目环境

- [[week01/day06/Python pip|pip / PyPI]]
- [[week01/day06/Python 虚拟环境|venv 虚拟环境]]

### 面向对象

- [[week01/day06/Python 类|类与对象]]
- [[week01/day06/Python 面向对象编程|面向对象编程]]

## 当前已经建立的主线能力

```text
变量与基础类型
→ 条件与循环
→ 函数
→ list / tuple / dict / set
→ 遍历 / 筛选 / 排序 / 推导式
→ 异常处理
→ 模块与包
→ 文件与目录
→ pip / venv
→ OOP 基础
```

## 当前仍需要重点巩固

- 根据问题主动选择 `list / dict / set`
- 跟踪变量里实际装的是什么
- `return / break / else` 的控制流
- `*args / **kwargs` 的收集与解包
- 异常处理的实际场景感
- `with open()` 的文件读写模式
- pip、虚拟环境和项目依赖之间的关系
- Python 的 `class / self / __init__` 实际写法

## 下一阶段

Day06 之后不建议继续无限横向刷 Python 语法教程。

更适合转向：

```text
Python 综合小练习
→ JSON / HTTP
→ pytest
→ FastAPI
→ 数据库
→ LLM API
```

目标从“知道 Python 有什么”切换到“拿 Python 做东西”。