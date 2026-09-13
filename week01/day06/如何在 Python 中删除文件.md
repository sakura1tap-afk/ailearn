# Python 删除文件

删除文件最常见的两种写法：

## `os.remove()`

```python
import os

os.remove("readme.txt")
```

文件不存在时会抛出 `FileNotFoundError`。

可以配合异常处理：

```python
import os

try:
    os.remove("readme.txt")
except FileNotFoundError:
    print("文件不存在")
```

## `pathlib.Path.unlink()`

现代代码也常写：

```python
from pathlib import Path

Path("readme.txt").unlink()
```

如果希望文件不存在时不报错：

```python
Path("readme.txt").unlink(missing_ok=True)
```

## 当前重点

```text
os.remove(path)   → 删除文件
Path.unlink()     → 删除文件
```

删除属于破坏性操作。实际项目中执行批量删除前，先确认路径和筛选条件。