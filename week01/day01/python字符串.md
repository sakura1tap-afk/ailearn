---
aliases:
  - "Python 字符串"
tags:
  - python/基础
week: week01
day: day01
review_order: 8
---

# Python 字符串

> [!abstract] 本篇重点
> **字符串不可变；索引从 0 开始，切片不包含结束位置。**
>
> 前置知识：[[python变量|Python 变量]]
> 所属知识链：[[00 Python学习导航]] · [[01 Python知识图谱]]

## 在 Python 字符串中使用带有 f 字符串的变量

有时，你想使用字符串中[变量](https://www.pythontutorial.net/python-basics/python-variables/)的值。

例如，在字符串变量 `message` 中插入变量 `name` 的值：

```python
name = 'John'
message = 'Hi'
```

在字符串引号前加 `f`，并用花括号 `{}` 包住变量或表达式。

```python
name = 'John'
message = f'Hi {name}'
print(message)
```

## 连接 Python 字符串
当你把字符串文字放在一起时，Python 会自动把它们[串接](https://www.pythontutorial.net/python-string-methods/python-string-concatenation/)成一个字符串。例如：

```python
greeting = 'Good ' 'Morning!'
print(greeting)
```

输出：

```text
Good Morning!
```

要连接[两个字符串变量](https://www.pythontutorial.net/python-basics/python-string-concatenation/)，使用运算符：`+`

```python
greeting = 'Good '
time = 'Afternoon'

greeting = greeting + time + '!'
print(greeting)
```
输出：

```text
Good Afternoon!
```

## 访问字符串元素

由于字符串是字符[序列](https://www.pythontutorial.net/advanced-python/python-sequences/)，你可以通过索引访问其元素。字符串中的第一个字符索引为零。

以下示例展示了如何使用索引访问元素：

```python
str = "Python String"
print(str[0]) # P
print(str[1]) # y
```

工作原理：

- 首先，创建一个变量，包含字符串 。`"Python String"`
- 然后，通过方括号和索引访问字符串的第一个和第二个字符。`[]`

如果你使用负索引，Python 会返回从字符串末尾开始的字符。例如：

```python
str = "Python String"
print(str[-1])  # g
print(str[-2])  # n
```

下图展示了字符串的索引：`"Python String"`

```text
+---+---+---+---+---+---+---+---+---+---+---+---+---+
| P | y | t | h | o | n |   | S | t | r | i | n | g | 
+---+---+---+---+---+---+---+---+---+---+---+---+---+
  0   1   2   3   4   5   6   7   8   9   10  11  12
-13  -12  -11  -10 -9  -8  -7  -6  -5  -4  -3  -2  -1
```

## 计算字符串长度

要计算字符串长度，你使用函数。例如：`len()`

```python
str = "Python String"
str_len = len(str)
print(str_len)
```

## 字符串切片

[切片](https://www.pythontutorial.net/advanced-python/python-slicing/)可以让你从字符串中得到子字符串。例如：

```python
str = "Python String"
print(str[0:2])
```

[试试看吧](https://www.pythontutorial.net/playground/?q=c3RyID0gIlB5dGhvbiBTdHJpbmciCnByaW50KHN0clswOjJdKQ%3D%3D)

输出：

```text
Py
```

返回一个子串，包含索引0（包含）到2（排除）的字符。`str[0:2]`
切片的语法如下：

```python
string[start:end]
```

在这里的正向切片中，包含 `start` 位置的字符，不包含 `end` 位置的字符。

## Python 字符串是不可变的

想修改字符串时，你需要从现有字符串创建一个新的字符串。例如：

```python
str = "Python String"
new_str = 'J' + str[1:]
print(new_str)
```
## f-string 格式化字符串

f-string允许你在字符串文字中嵌入变量和表达式。例如：

```python
name = 'Anthony'
message = f'Hello, {name}!'
print(message)
```

在这个例子中：

- 首先，使用字母 f 表示字符串字面是 f-字符串。`f''`
- 其次，在花括号中放置一个变量`{name}`

求值时，Python 用变量的值 `Anthony` 替换占位符 `{name}`，这称为字符串插值。

## 摘要

- 在 Python 中，字符串是一系列字符。另外，Python 字符串是不可变的。
- 使用引号，无论是单引号还是双引号，来创建字符串文字。
- 使用反斜杠字符来转义字符串中的引号
- 用原始字符串逃离反斜线字符。`r'...'`
- 使用f字符串在字面字符串中插入替代变量。
- 把字面上的字符串放在一起，把它们串接起来。并且使用+运算符来串接字符串变量。
- 用函数来计算字符串的长度。`len()`
- 使用 `text[n]` 访问字符串 `text` 在索引 n 处的字符。
- 使用切片技术从字符串中提取子字符串。
- 使用 f 字符串将变量嵌入字符串文字中。

---
原教程：[PythonTutorial](https://www.pythontutorial.net/python-basics/python-string/)

## 知识链与自查

- **学完可接着看**：[[python布尔|Python 布尔值与真值判断]]、[[类型转换|Python 类型转换]]、[[python比较|Python 比较运算符]]、[[Python 列表|Python 列表]]、[[Python 列表切片|Python 列表切片]]。
- **按顺序复习 · 上一篇**：[[python赋值操作符|Python 复合赋值运算符]]。
- **按顺序复习 · 下一篇**：[[python布尔|Python 布尔值与真值判断]]。
- **自查**：`"Python"[0:2]` 与 `"Python"[-1]` 分别得到什么？
