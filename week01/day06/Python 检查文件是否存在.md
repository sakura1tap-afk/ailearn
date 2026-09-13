# Python 检查文件是否存在

现代 Python 项目更推荐用 `pathlib.Path`。

```python
from pathlib import Path

path = Path("readme.txt")

print(path.exists())   # 路径是否存在
print(path.is_file())  # 是否存在，并且是文件
print(path.is_dir())   # 是否存在，并且是目录
```

## 三个方法不要混

```text
exists()  → 这个路径存在吗
is_file() → 它是文件吗
is_dir()  → 它是目录吗
```

例如：

```python
from pathlib import Path

path = Path("data/users.txt")

if path.is_file():
    print("文件存在")
else:
    print("文件不存在")
```

## 旧代码里也常见 os.path

```python
import os

os.path.exists("readme.txt")
os.path.isfile("readme.txt")
os.path.isdir("data")
```

这套写法仍然有效，读代码时要认识。

## 是否一定要先检查

不一定。

如果下一步本来就可能失败，有时直接配合异常处理更自然：

```python
try:
    with open("readme.txt", encoding="utf-8") as f:
        print(f.read())
except FileNotFoundError:
    print("文件不存在")
```

所以实际开发中常见两种思路：

```text
先判断状态 → Path.is_file()
直接执行   → 失败后捕获 FileNotFoundError
```

当前阶段两种都能看懂即可。