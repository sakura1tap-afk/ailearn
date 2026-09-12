---
tags:
  - python/导航
---

# Python 学习导航

这个仓库保留 `week/day` 作为学习时间线，同时提供一条更适合复习的知识路线。

当前进度：**Week01 / Day05**。已经从基础语法进入到 **函数参数、异常处理、模块与包、类型提示**。

优先入口：
- [[01 Python知识图谱]]：看知识之间怎么连接。
- [[02 易混概念与练习复盘]]：看当前最容易犯的错误。
- [[week01/day03/Day03 列表与迭代|Day03 列表与迭代]]：列表处理、迭代、排序、map/filter/reduce。
- [[week01/day04/Day04 字典与集合|Day04 字典与集合]]：字典、集合、集合运算与循环 else。
- [[week01/day05/Day05 函数参数、异常与模块|Day05 函数参数、异常与模块]]：`*args/**kwargs`、异常、模块、包、类型提示。

> [!tip] 建议学习方式
> 新知识先弄清“解决什么问题”，再记语法。看懂不算掌握，关闭笔记后能自己写出来才算。

## 1. 基础语法｜Day01

- [[python基础|Python 基础语法]]
- [[python注释|Python 注释]]
- [[python变量|Python 变量]]
- [[python常量|Python 常量约定]]
- [[python数字|Python 数字]]
- [[python算术|Python 算术运算符]]
- [[python赋值操作符|Python 复合赋值运算符]]
- [[python字符串|Python 字符串]]
- [[python布尔|Python 布尔值与真值判断]]
- [[类型转换|Python 类型转换]]
- [[python比较|Python 比较运算符]]
- [[Python 逻辑运算符|Python 逻辑运算符]]

## 2. 流程控制与函数｜Day02

### 条件与循环

- [[python if语句|Python if 条件分支]]
- [[Python三进制算符|Python 三元表达式（条件表达式）]]
- [[Python范围循环|Python for 与 range]]
- [[Python while|Python while 循环]]
- [[Python break|Python break]]
- [[Python continue|Python continue]]
- [[Python pass|Python pass]]

### 函数

- [[Python 函数|Python 函数]]
- [[Python 默认参数|Python 默认参数]]
- [[Python 关键词参数|Python 关键字参数]]
- [[Python 函数文档字符串|Python 函数文档字符串]]
- [[Python Lambda表达式|Python lambda 表达式]]
- [[Python 递归函数|Python 递归函数]]

### 列表

- [[Python 列表|Python 列表]]
- [[week01/day02/今日练习|Day02 手写练习]]

Day02 手写重点：列表求和、筛选偶数、查找目标、去重、冒泡排序与第二大元素。

## 3. 序列、迭代与数据处理｜Day03

先看：[[week01/day03/Day03 列表与迭代|Day03 列表与迭代]]

### 序列结构

- [[Python元组|Python 元组]]
- [[Python 中解包列表|Python 序列解包]]
- [[Python 列表切片|Python 列表切片]]
- [[Python 列表解析|Python 列表推导式]]

### 遍历与查找

- [[For 循环|Python for 遍历列表与 enumerate]]
- [[Python 迭代|Python 可迭代对象与迭代器]]
- [[查找列表中元素的索引|Python 列表查找与成员判断]]

### 排序 / 转换 / 筛选 / 归约

- [[Python 排序列表|Python list.sort 原地排序]]
- [[Python sorted|Python sorted 返回新列表]]
- [[Python map（） 函数转换列表元素|Python map 转换元素]]
- [[Python中筛选列表元素|Python filter 筛选元素]]
- [[Python的reduce（） 函数将列表简化为单一值|Python reduce 累积归约]]
- [[week01/day03/今日练习|Day03 手写练习]]

## 4. 字典、集合与循环 else｜Day04

先看：[[week01/day04/Day04 字典与集合|Day04 字典与集合]]

### 字典

- [[Python 词典|Python 字典]]
- [[Python 词典理解|Python 字典推导式]]

### 集合

- [[Python 集合|Python 集合]]
- [[Python 集合理解|Python 集合推导式]]
- [[Python集合合并|Python 集合并集]]
- [[Python 集交集|Python 集合交集]]
- [[Python集合差集|Python 集合差集]]
- [[Python 对称差分|Python 集合对称差]]
- [[Python issubset|Python 子集判断]]
- [[Python issuperset|Python 超集判断]]
- [[Python 不相交集|Python 不相交判断]]

### 循环 else

- [[Python for…else|Python for...else]]
- [[Python while else|Python while...else]]

## 5. 函数参数、异常与模块｜Day05

先看：[[week01/day05/Day05 函数参数、异常与模块|Day05 函数参数、异常与模块]]

### 参数与解包

- [[week01/day05/Python args|Python *args]]
- [[week01/day05/Python kwargs|Python **kwargs]]
- [[week01/day05/Python 解包元组|Python 元组与解包]]

### 异常处理

- [[week01/day05/Python try…except|Python try...except]]
- [[week01/day05/Python try…except…finally|Python try...except...finally]]

### 模块与代码组织

- [[week01/day05/Python 模块|Python 模块]]
- [[week01/day05/Python 包|Python 包]]
- [[week01/day05/Python 模块搜索路径|Python 模块搜索路径]]
- [[week01/day05/Python 私有函数|Python 私有函数约定]]

### 类型与补充

- [[week01/day05/Python 类型提示|Python 类型提示]]
- [[week01/day05/Python do…while 模拟|Python 模拟 do...while]]
- [[week01/day05/Python 部分函数|Python partial 部分函数]]

## 6. 当前学习状态

### 已经开始形成手写能力

- `for + if + append + return`
- 基础函数与参数
- 列表遍历、查找、筛选
- 字典 `key -> value` 与 `items()`
- 集合交集、差集、子集 / 超集判断
- 列表推导式、`filter()`、`sorted(key=...)`
- 基础冒泡排序

### 目前需要重点巩固

- 根据问题判断该选 `list / dict / set`
- 跟踪变量里实际装的是什么数据
- `return` 的位置和返回对象
- `*args / **kwargs` 的“收集”与“解包”区别
- `try...except` 在真实失败场景中的使用
- 模块、包、虚拟环境之间的关系
- 类型提示只是提示，不是运行时强制类型

## 7. 接下来的建议知识链

Day05 巩固后：

```text
文件读写
→ JSON
→ pip / venv
→ 面向对象基础
→ requests / httpx
→ pytest
→ FastAPI
```

这条路线优先服务于 **Python 后端 + AI 应用开发**。目标不是“学完 Python 所有特性”，而是尽快形成能读代码、写代码和进入工程实践的能力。
