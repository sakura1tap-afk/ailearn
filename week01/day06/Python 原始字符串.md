## Python 原始字符串介绍[](https://www.pythontutorial.net/python-basics/python-raw-strings/#introduction-to-the-python-raw-strings "Anchor for Introduction to the Python raw strings")

在 Python 中，当你在字符串前加上字母 或 ，比如 和 时，该字符串就变成了原始字符串。与普通字符串不同，原始字符串将反斜杠（）视为字面字符。`r``R``r'...'``R'...'`

当你处理带有许多反斜杠的字符串时，原始字符串非常有用，比如Windows上的[正则表达式](https://www.pythontutorial.net/python-regex/python-regular-expressions/)或目录路径。

为了表示制表符和换行等特殊字符，Python 使用[反斜杠](https://www.pythontutorial.net/python-basics/python-backslash/)（）表示转义序列的开始。例如：

```python
s = 'langtvernPythont3'
print(s)
```


输出：

```python
lang    ver
Python  3
```

然而，原始字符串将反斜杠（）视为字面字符。例如：

```python
s = r'langtvernPythont3'
print(s)
```


输出：

```python
langtvernPythont3
```

原始字符串类似于其普通字符串，但反斜杠（）以双反斜杠表示：`\`

```python
s1 = r'langtvernPythont3'
s2 = 'lang\tver\nPython\t3'

print(s1 == s2) # True
```


在普通字符串中，Python 将一个转义序列计为单个字符：

```python
s = 'n'
print(len(s)) # 1
```


然而，在原始字符串中，Python 将反斜杠（）计为一个字符：

```python
s = r'n'
print(len(s)) # 2
```

由于反斜杠（）逃逸出单引号（）或双引号（），原始字符串不能以奇数个反斜杠结尾。`'``"`

例如：

```python
s = r''
```

错误：

```python
SyntaxError: EOL while scanning string literal
```

或者

```python
s = r'\'
```

错误：

```python
SyntaxError: EOL while scanning string literal
```

### 在Windows上使用原始字符串处理文件路径[](https://www.pythontutorial.net/python-basics/python-raw-strings/#use-raw-strings-to-handle-file-path-on-windows "Anchor for Use raw strings to handle file path on Windows")

Windows 操作系统使用反斜杠来分隔路径。例如：

```python
c:usertasksnew
```

如果你把这条路径当作普通字符串使用，Python 会报出一些错误：

```python
dir_path = 'c:usertasksnew'
```

错误：

```python
SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated uXXXX escape
```

Python 把路径中的 u 当作 Unicode 的转义，但无法解码。

如果你逃避了第一个反斜线，你会遇到其他问题：

```python
dir_path = 'c:\usertasksnew'
print(dir_path)
```

输出：

```python
c:user asks
ew
```

在这个例子中，是制表符，是新行。`t``n`

为了简化操作，你可以把路径转换成像这样一个原始字符串：

```python
dir_path = r'c:usertasksnew'
print(dir_path)
```


## 把普通字符串转换成原始字符串[](https://www.pythontutorial.net/python-basics/python-raw-strings/#convert-a-regular-string-into-a-raw-string "Anchor for Convert a regular string into a raw string")

要将普通字符串转换为原始字符串，可以使用内置的 repr（） 函数。例如：

```python
s = 'n'
raw_string = repr(s)

print(raw_string)
```

输出：

```python
'n'
```

注意，结果的原始字符串在字符串的开头和结尾都有引号。去除它们时，可以用切片：

```python
s = 'n'
raw_string = repr(s)[1:-1]
print(raw_string)
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-raw-strings/#summary "Anchor for Summary")

- 在字面字符串前加上字母 r 或 R，将其变成原始字符串。
- 原始字符串把反斜线当作字面字符来处理。