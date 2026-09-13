# Python 原始字符串 raw string

原始字符串在字符串前加 `r` 或 `R`：

```python
path = r"C:\Users\Tom\Desktop"
```

它的核心作用是：**让反斜杠尽量按字面意义保留，而不是当作转义序列处理。**

## 为什么有用

普通字符串里：

```python
text = "hello\nworld"
print(text)
```

`\n` 会被解释为换行。

而：

```python
text = r"hello\nworld"
print(text)
```

会直接显示：

```text
hello\nworld
```

## 常见场景

### Windows 路径

```python
path = r"E:\Python\project\data.txt"
```

这样不用把每个反斜杠都写成 `\\`。

不过现代 Python 项目更推荐用 `pathlib.Path` 处理路径：

```python
from pathlib import Path

path = Path("data") / "users.txt"
```

### 正则表达式

正则表达式本身也大量使用反斜杠，因此经常写：

```python
pattern = r"\d+"
```

## 一个限制

原始字符串不能以奇数个反斜杠结束。

## 当前重点

```text
普通字符串 → 反斜杠可能触发转义
r"..."     → 更适合表示包含大量反斜杠的文本
```

raw string 仍然是普通的 `str`，不是新的数据类型。