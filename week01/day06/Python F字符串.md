## Python F字符串简介[](https://www.pythontutorial.net/python-basics/python-f-strings/#introduction-to-the-python-f-strings "Anchor for Introduction to the Python F-strings")

Python 3.6引入了f字符串，让你可以更快更优雅地格式化文本字符串。f串提供了一种方式，可以用比方法更清晰的语法，将[变量](https://www.pythontutorial.net/python-basics/python-variables/)和表达式嵌入字符串字面量中。`format()`

例如：

```python
name = 'John'
s = f'Hello, {name}!'
print(s)
```

输出：

```python
Hello, John!
```

它是如何运作的。

- 首先，[定义](https://www.pythontutorial.net/python-basics/python-variables/)一个变量，值为 。`'John'`
- 然后，将变量放入字串中的卷括中。注意你需要在字符串前加上字母，表示它是 f 弦。如果你用大写字母（）。`name``{}``f``F`
- 第三，打印字符串s。

需要注意的是，Python 在运行时会评估 f 字符串中的变量和表达式。它用 f 字符串中的变量和表达式替换它们的值。`{name}`

## Curly braces

## 使用f字符串格式化数字[](https://www.pythontutorial.net/python-basics/python-f-strings/#format-numbers-using-f-strings "Anchor for Format numbers using f-strings")

以下示例使用f字符串将整数格式化为十六进制：

```perl
number = 16
s = f'{number:x}'
print(s)  # 10
```

以下示例使用f字符串将数字格式化为科学符号：

```perl
number = 0.01
s = f'{number:e}'
print(s)  # 1.000000e-02
```

如果你想在数字开头填充零，可以使用如下 f 字符串格式：

```perl
number = 200
s = f'{number: 06}'
print(s)  # 00200
```

06 是结果数值字符串的总数，包括前置零。

为了指定小数点数，你也可以使用f字符串：

```perl
number = 9.98567
s = f'{number: .2f}'
print(s)  # 9.99
```

,000,000,000
```

要将数字格式化为百分比，可以使用以下 f 字符串格式：

```perl
number = 0.1259
s = f'{number: .2%}'
print(s)  # 12.59%

s = f'{number: .1%}'
print(s)  # 12.5%
```


Python 有更[复杂的格式规则，你可以通过以下链接查阅](https://docs.python.org/3/library/string.html#format-specification-mini-language)。

## 摘要[](https://www.pythontutorial.net/python-basics/python-f-strings/#summary "Anchor for Summary")

- Python f字符串为文本字符串提供了一种优雅的格式化方式。
- Python 在运行时替换嵌入在 f 字符串中卷括号内的表达式的结果。`{}`