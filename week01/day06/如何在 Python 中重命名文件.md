**总结**：在本教程中，你将学习如何使用模块函数在 Python 中重命名文件。`rename()``os`

要在 Python 中重命名文件，你使用模块中的函数。`rename()``os`

以下是 rename（） 函数的基本语法：

```lua
os.rename(src, dst)
```

重命名函数会将 重新命名为 。`src``dst`

如果文件不存在，函数会报错。同样，如果已经存在，函数也会报错。`src``rename()``FileNotFound``dst``rename()``FileExistsError`

例如，以下操作使用函数将文件重命名为：`rename()``readme.txt``notes.txt`

```lua
import os

os.rename('readme.txt', 'notes.txt')
```

为了避免错误，如果文件不存在和/或文件已经存在，你可以使用以下语句：`readme.txt``notes.txt``[try...except](https://www.pythontutorial.net/python-basics/python-try-except/)`

```python
import os

try:
    os.rename('readme.txt', 'notes.txt')
except FileNotFoundError as e:
    print(e)
except FileExistsError as e:
    print(e)
```

以下显示文件不存在时的输出：`readme.txt`

```abap
[WinError 2] The system cannot find the file specified: 'readme.txt' -> 'notes.txt'
```

如果已经存在，以下图显示了输出：`notes.txt`

```sql
[WinError 183] Cannot create a file when that file already exists: 'readme.txt' -> 'notes.txt'
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-rename-file/#summary "Anchor for Summary")

- 使用该函数重命名文件。`os.rename()`