# Python 创建文本文件

创建文本文件仍然使用 `open()`，关键看打开模式。

## `w` 模式

```python
with open("readme.txt", "w", encoding="utf-8") as f:
    f.write("Hello")
```

如果文件不存在，会创建。

如果文件已经存在，`w` 会**清空原内容再写入**。

## `x` 模式

如果你只允许创建新文件，不希望覆盖已有文件，用 `x`：

```python
with open("readme.txt", "x", encoding="utf-8") as f:
    f.write("Hello")
```

文件已经存在时会抛出：

```text
FileExistsError
```

## 目录不存在怎么办

这段代码：

```python
with open("docs/readme.txt", "w", encoding="utf-8") as f:
    ...
```

只能创建 `readme.txt`，**不会自动创建 `docs` 文件夹**。

如果父目录不存在，会出现：

```text
FileNotFoundError
```

可以先创建目录：

```python
from pathlib import Path

Path("docs").mkdir(parents=True, exist_ok=True)

with open("docs/readme.txt", "w", encoding="utf-8") as f:
    f.write("Hello")
```

## 当前重点

```text
w → 不存在就创建，存在就覆盖
x → 只允许创建新文件，已存在就报错
```

这页和 [[Python 写文本文件]] 属于同一组知识，不需要把它们当成两个完全独立的知识点。