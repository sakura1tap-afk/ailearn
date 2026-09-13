## Python 反斜线介绍[](https://www.pythontutorial.net/python-basics/python-backslash/#introduction-to-the-python-backslash "Anchor for Introduction to the Python backslash")

在 Python 中，反斜杠（）是一个特殊字符。如果你在另一个字符前面使用反斜线，它会改变该字符的含义。

例如，是字面上的字符。但如果你在字母前面使用反斜杠字符，它就会变成制表符字符（）。`t``t``t`

一般来说，反斜线有两个主要目的。

首先，反斜杠字符是特殊字符序列的一部分，如制表符或换行字符。`t``n`

以下示例打印了一个带有换行字符的字符串：

```go
print('Hello,n World')
```


输出：

```plaintext
Hello,
World
```

n 是一个字符，不是两个字符。例如：

```perl
s = 'n'
print(len(s)) # 1
```

## F弦中的反斜线[](https://www.pythontutorial.net/python-basics/python-backslash/#backslash-in-f-strings "Anchor for Backslash in f-strings")

PEP-498 规定，[f 字符串](https://www.pythontutorial.net/python-basics/python-f-strings/)不能将反斜杠字符作为表达式的一部分放入卷括号内。`{}`

以下示例将导致错误：

```perl
colors = ['red','green','blue']
s = f'The RGB colors are:n {'n'.join(colors)}'
print(s)
```


错误：

```typescript
SyntaxError: f-string expression part cannot include a backslash
```

要解决这个问题，你需要先把字符串在列表中连接起来，再放入大括号：`colors`

```abap
colors = ['red','green','blue']
rgb = 'n'.join(colors)
s = f"The RGB colors are:n{rgb}"
print(s)
```
输出：

```yaml
The RGB colors are:
red
green
blue
```

## 原始弦中的反斜线[](https://www.pythontutorial.net/python-basics/python-backslash/#backslash-in-raw-strings "Anchor for Backslash in raw strings")

[原始字符串](https://www.pythontutorial.net/python-basics/python-raw-strings/)将反斜杠字符（）视为字面字符。以下示例将反斜杠字符视为字面字符，而非特殊字符：

```python
s = r'n'
print(s)
```

[试试看吧](https://www.pythontutorial.net/playground/?q=cyA9IHInXG4nDQpwcmludChzKQ)

输出：

```abap
n
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-backslash/#summary "Anchor for Summary")

- Python 反斜线字符（）是用作特殊序列（如 和 ）的一部分的特殊字符。`t``n`
- 使用Python反斜杠（）来跳脱字符串中的其他特殊字符。
- F字串不能包含反斜杠，即表达式的一部分，位于大括号内。`{}`
- 原始字符串将反斜杠（）视为字面字符。