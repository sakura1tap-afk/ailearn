# Python 列出目录中的文件

## `os.walk()`

```python
import os

for root, dirs, files in os.walk("data"):
    print(root)
    print(dirs)
    print(files)
```

每一轮得到：

```text
root  → 当前目录路径
dirs  → 子目录名列表
files → 文件名列表
```

`os.walk()` 会递归进入子目录。

只找 `.html`：

```python
import os

for root, _, files in os.walk("web"):
    for filename in files:
        if filename.endswith(".html"):
            print(os.path.join(root, filename))
```

这里 `_` 表示这个值存在，但当前不使用。

## pathlib 写法

```python
from pathlib import Path

for path in Path("web").rglob("*.html"):
    print(path)
```

如果只是递归寻找某类文件，`Path.rglob()` 通常更简洁。

## 当前重点

```text
os.walk()    → 遍历整个目录树
Path.rglob() → 按模式递归寻找文件
```

以后批量处理文档、图片、日志或 RAG 数据文件时会经常遇到。