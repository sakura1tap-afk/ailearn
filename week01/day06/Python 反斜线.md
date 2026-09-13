# Python 反斜杠与转义字符

反斜杠 `\` 在字符串里常用来表示**转义序列**。

常见写法：

```python
"\n"   # 换行
"\t"   # 制表符
"\\"   # 一个反斜杠
"\""   # 双引号
"\'"   # 单引号
```

例如：

```python
print("Hello\nPython")
```

输出：

```text
Hello
Python
```

## 为什么 Windows 路径容易出问题

如果写：

```python
path = "C:\new\test"
```

其中的 `\n`、`\t` 可能被当成换行和制表符。

常见解决方式：

```python
path = r"C:\new\test"
```

或者使用 `pathlib`：

```python
from pathlib import Path

path = Path("C:/new/test")
```

## 和原始字符串的关系

普通字符串：

```python
"\n"
```

表示一个换行字符。

原始字符串：

```python
r"\n"
```

表示两个普通字符：反斜杠和字母 `n`。

关联：[[Python 原始字符串]]

## 当前重点

不要把反斜杠单独当成复杂知识点。只需要形成这个直觉：

```text
\ + 某些字符 → 可能具有特殊含义
```

看到路径、正则表达式或转义问题时，再想到 raw string 或 `pathlib`。