# Python 重命名文件

使用 `os.rename()`：

```python
import os

os.rename("readme.txt", "notes.txt")
```

```text
src → 原路径
dst → 新路径
```

原文件不存在时会抛出 `FileNotFoundError`。

现代代码也常用 `pathlib`：

```python
from pathlib import Path

Path("readme.txt").rename("notes.txt")
```

`rename()` 也可以把文件移动到另一个已存在的目录：

```python
Path("readme.txt").rename("docs/readme.txt")
```

## 当前重点

```text
os.rename(src, dst)
Path(src).rename(dst)
```

真正需要注意的是确认原路径和目标路径，避免误移动文件。