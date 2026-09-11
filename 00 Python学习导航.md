---
tags:
  - python/导航
---

# Python 学习导航

保留 week/day 作为**学习日期记录**，用下面的顺序作为**复习路线**。序号表示建议阅读顺序，不表示每一篇都是下一篇的必备前置；每篇顶部另有“前置知识”。

从 [[01 Python知识图谱]] 看知识依赖；从 [[02 易混概念与练习复盘]] 找容易出错的地方。整理范围与校正依据见 [[99 本次整理说明]]。

> [!tip] 每次怎么学
> 先看本篇重点 → 不熟的前置知识点回去看 → 阅读原笔记、运行示例 → 回答页末自查 → 顺着下一篇继续。
> 基础已经熟悉时，可以直接从薄弱知识点进入，不必每次从头复习。

## 建议复习顺序


### 基础

- **01** · [[python基础|Python 基础语法]] · `day01`
- **02** · [[python注释|Python 注释]] · `day01`
- **03** · [[python变量|Python 变量]] · `day01`
- **04** · [[python常量|Python 常量约定]] · `day01`
- **05** · [[python数字|Python 数字]] · `day01`
- **06** · [[python算术|Python 算术运算符]] · `day01`
- **07** · [[python赋值操作符|Python 复合赋值运算符]] · `day01`
- **08** · [[python字符串|Python 字符串]] · `day01`
- **09** · [[python布尔|Python 布尔值与真值判断]] · `day01`
- **10** · [[类型转换|Python 类型转换]] · `day01`
- **11** · [[python比较|Python 比较运算符]] · `day01`
- **12** · [[Python 逻辑运算符|Python 逻辑运算符]] · `day01`

### 流程控制

- **13** · [[python if语句|Python if 条件分支]] · `day02`
- **14** · [[Python三进制算符|Python 三元表达式（条件表达式）]] · `day02`
- **15** · [[Python范围循环|Python for 与 range]] · `day02`
- **16** · [[Python while|Python while 循环]] · `day02`
- **17** · [[Python break|Python break]] · `day02`
- **18** · [[Python continue|Python continue]] · `day02`
- **19** · [[Python pass|Python pass]] · `day02`

### 函数

- **20** · [[Python 函数|Python 函数]] · `day02`
- **21** · [[Python 默认参数|Python 默认参数]] · `day02`
- **22** · [[Python 关键词参数|Python 关键字参数]] · `day02`
- **23** · [[Python 函数文档字符串|Python 函数文档字符串]] · `day02`

### 序列

- **24** · [[Python 列表|Python 列表]] · `day02`
- **25** · [[Python元组|Python 元组]] · `day03`
- **26** · [[Python 中解包列表|Python 序列解包]] · `day03`
- **27** · [[Python 列表切片|Python 列表切片]] · `day03`
- **28** · [[For 循环|Python for 遍历列表与 enumerate]] · `day03`
- **29** · [[查找列表中元素的索引|Python 列表查找与成员判断]] · `day03`
- **30** · [[Python 迭代|Python 可迭代对象与迭代器]] · `day03`

### 函数应用

- **31** · [[Python Lambda表达式|Python lambda 表达式]] · `day02`
- **32** · [[Python 排序列表|Python list.sort 原地排序]] · `day03`
- **33** · [[Python sorted|Python sorted 返回新列表]] · `day03`
- **34** · [[Python map（） 函数转换列表元素|Python map 转换元素]] · `day03`
- **35** · [[Python中筛选列表元素|Python filter 筛选元素]] · `day03`
- **36** · [[Python的reduce（） 函数将列表简化为单一值|Python reduce 累积归约]] · `day03`
- **37** · [[Python 递归函数|Python 递归函数]] · `day02`

### 练习

- **38** · [[今日练习|Day02 今日练习与错题复盘]] · `day02`

> [!note] 几处跨日期的安排
> 列表知识和 day03 的 for 遍历要放在列表练习之前；lambda 的循环示例也依赖列表和遍历，所以放到后面。递归作为函数的分支专题，可以稍后复习；练习本身不依赖递归。

## 按原来的日期回顾

| 原目录 | 内容 | 复习时注意 |
| --- | --- | --- |
| week01/day01 | 语法、变量、数值、字符串、布尔、运算与转换 | 先搞清楚“值是什么类型”，再看条件判断 |
| week01/day02 | 分支、循环、函数、列表、练习 | 练习会用到 day03 的遍历、查找和排序 |
| week01/day03 | 元组、解包、切片、遍历、迭代器、排序与数据处理 | 先理解普通 for，再看 map/filter/reduce |

## 后续知识链（建议，尚未算作已学）

现有列表知识 → 列表推导式 → 字典与集合 → 模块与导入 → 异常处理 → 文件与 JSON → 虚拟环境和包管理 → NumPy 数组 → Pandas 数据整理 → 机器学习入门。

这是一条面向 AI 数据处理的建议路线，可以随着你的学习目标调整。整理时出现了一个空白的 [[Python 列表解析]] 页面，可作为“列表推导式（list comprehension）”的记录入口；暂未改动它的正文。

## 以后新增笔记

继续放在对应 week/day 下即可。每篇补一句重点、1–3 个前置知识链接和一个自查问题，再把新笔记接到本页合适的位置。只有已经有内容的笔记才加入正式复习路线。
