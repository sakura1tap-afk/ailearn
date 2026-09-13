**总结**：在这个教程中，你将学习如何使用 和 函数来检查文件是否存在。`os.path.exists()``pathlib.is_file()`

处理文件时，你通常会想先确认文件是否存在，然后再做其他操作，比如[读取文件](https://www.pythontutorial.net/python-basics/python-read-text-file/)或[写入数据](https://www.pythontutorial.net/python-basics/python-write-text-file/)。

要检查文件是否存在，可以使用模块中的函数：`exists()``os.path`

```pgsql
from os.path import exists

file_exists = exists(path_to_file)
```

或者，你也可以使用模块中类的方法：`is_file()``Path``pathlib`

```pgsql
from pathlib import Path

path = Path(path_to_file)

path.is_file()
```

## 使用 os.path.exists（） 函数检查文件是否存在[](https://www.pythontutorial.net/python-basics/python-check-if-file-exists/#checking-if-a-file-exists-using-os-path-exists-function "Anchor for Checking if a file exists using os.path.exists() function")

要检查文件是否存在，你只需将标准库中的文件路径传递给函数。`exists()``os.path`

首先，导入标准库：`os.path`

```swift
import os.path
```

其次，调用函数：`exists()`

```lua
os.path.exists(path_to_file)
```

如果文件存在，函数返回 。否则，返回 。`exists()``True``False`

如果文件和程序在同一个文件夹里，那就只是文件名。`path_to_file`

但事实并非如此，你需要通过文件的完整路径。例如：

```pgsql
/path/to/filename
```

即使你在Windows上运行这个程序，也应该用斜杠（）来分隔路径。它能在Windows、macOS和Linux上运行。`/`

以下示例使用了检查文件是否存在于与程序相同的文件夹中的函数：`exists()``readme.txt`

```lua
import os.path

file_exists = os.path.exists('readme.txt')

print(file_exists)
```

如果文件存在，你会看到以下输出：`readme.txt`

```yaml
True
```

否则，你会在屏幕上看到：`False`

```yaml
False
```

为了让调用函数更短更直观，你可以导入该函数并将其重命名为函数，如下：`exists()``file_exists()`

```pgsql
from os.path import exists as file_exists

file_exists('readme.txt')
```
w## 使用 pathlib 模块检查文件是否存在[](https://www.pythontutorial.net/python-basics/python-check-if-file-exists/#checking-if-a-file-exists-using-the-pathlib-module "Anchor for Checking if a file exists using the pathlib module")

该模块允许你使用面向对象的方法操作文件和目录。如果你不熟悉面向对象编程，可以看看[Python面向对象编程](https://www.pythontutorial.net/python-oop/)部分。`pathlib`

Python 自 3.4 版本起引入了该模块。所以你应该有Python 3.4或更高版本才能使用这个模块。`[pathlib](https://www.pythontutorial.net/python-standard-library/python-path/)`

首先，从模块导入该类：`Path``pathlib`

```pgsql
from pathlib import Path
```

然后，实例化一个新的类实例，并用你想检查是否存在的文件路径初始化它：`Path`

```pgsql
path = Path(path_to_file)
```

最后，使用以下方法检查文件是否存在：`is_file()`

```lua
path.is_file()
```

如果文件不存在，方法返回 。否则，返回 。`is_file()``False``True`

以下示例展示了如何使用模块中的类来检查该文件是否存在于程序的同一文件夹中：`Path``pathlib``readme.txt`

```python
from pathlib import Path

path_to_file = 'readme.txt'
path = Path(path_to_file)

if path.is_file():
    print(f'The file {path_to_file} exists')
else:
    print(f'The file {path_to_file} does not exist')
```

如果文件存在，你会看到以下输出：`readme.txt`

```perl
The file readme.txt exists
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-check-if-file-exists/#summary "Anchor for Summary")

- 使用函数或方法检查文件是否存在`os.path.exists()``Path.is_file()`