# Python 目录操作

目录操作可以使用 `os`，现代项目也经常使用 `pathlib`。

## 查看当前工作目录

```python
import os

print(os.getcwd())
```

当前工作目录决定了相对路径从哪里开始解析。

## 创建目录

使用 `pathlib`：

```python
from pathlib import Path

Path("data").mkdir(exist_ok=True)
```

创建多层目录：

```python
Path("data/raw/input").mkdir(parents=True, exist_ok=True)
```

## 判断目录

```python
from pathlib import Path

path = Path("data")

path.exists()
path.is_dir()
```

## 拼接路径

推荐：

```python
from pathlib import Path

path = Path("data") / "users" / "tom.txt"
```

这样不用自己考虑 Windows 的 `\` 和 Linux/macOS 的 `/`。

旧代码也常见：

```python
import os

path = os.path.join("data", "users", "tom.txt")
```

## 重命名与删除目录

```python
from pathlib import Path

Path("old_dir").rename("new_dir")
Path("empty_dir").rmdir()
```

`rmdir()` 只能删除空目录。

## 递归遍历

```python
import os

for root, dirs, files in os.walk("data"):
    print(root, files)
```

## 当前重点

```text
Path.exists() → 路径是否存在
Path.is_dir() → 是否是目录
Path.mkdir()  → 创建目录
Path / "xxx" → 拼接路径
os.walk()     → 递归遍历目录
```

以后做文件处理、模型数据、RAG 文档加载时都会用到路径和目录操作。