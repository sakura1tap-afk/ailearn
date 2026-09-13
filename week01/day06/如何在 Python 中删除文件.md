**总结**：在这个教程中，你将学习如何使用模块中的函数删除 Python 中的文件。`remove()``os`

删除文件时，你需要使用内置模块的功能。例如，以下操作使用删除文件的函数：`` `remove()` ```os``os.remove()``readme.txt`

```python
import os

os.remove('readme.txt')
```

如果文件不存在，函数会发出错误：`readme.txt``os.remove()`

```python
FileNotFoundError: [WinError 2] The system cannot find the file specified: 'readme.txt'
```

为了避免错误，你可以在删除前[检查文件是否存在](https://www.pythontutorial.net/python-basics/python-check-if-file-exists/)，如下：

```python
import os

filename = 'readme.txt'
if os.path.exists(filename):
    os.remove(filename)
```

或者，如果文件不存在，你可以用该语句捕捉异常：`[try...except](https://www.pythontutorial.net/python-basics/python-try-except/)`

```python
import os

try:
    os.remove('readme.txt')
except FileNotFoundError as e:
    print(e)
```

## 摘要[#](https://www.pythontutorial.net/python-basics/python-delete-file/#summary "Anchor for Summary")

- 用操作系统。函数用来删除文件。`remove()`