**总结**：在这个教程中，你将学习如何使用该模块在 Python 中操作目录。`os`

## 获取当前的工作目录[](https://www.pythontutorial.net/python-basics/python-directory/#get-the-current-working-directory "Anchor for Get the current working directory")

当前的工作目录是运行 Python 脚本的目录。要获取当前的工作目录，请使用以下方法：`os.getcwd()`

```swift
import os


cwd = os.getcwd()
print(cwd)
```

要更改当前工作目录，可以使用函数：`os.chdir()`

```lua
import os


os.chdir('/script')
cwd = os.getcwd()
print(cwd)
```
## 合并并分开一条路径[](https://www.pythontutorial.net/python-basics/python-directory/#join-and-split-a-path "Anchor for Join and split a path")

要让程序在包括 Windows、Linux 和 macOS 等平台运行，你需要使用平台无关的文件和目录路径。

Python 提供了一个子模块，里面有几个有用的函数和常量，用于连接和分割路径。`os.path`

该函数将路径分量连接起来，并返回带有相应路径分隔符的路径。例如，在Windows上使用反斜线（）和在macOS或Linux上使用前斜杠（）。`join()``/`

该函数将路径拆分为没有路径分隔符的分量。这里有一个使用 和 函数的例子：`split()``join()``split()`

```lua
import os

fp = os.path.join('temp', 'python')
print(fp)  # temppython (on Windows)

pc = os.path.split(fp)
print(pc)  # ('temp', 'python')
```

## 测试路径是否为目录[](https://www.pythontutorial.net/python-basics/python-directory/#test-if-a-path-is-a-directory "Anchor for Test if a path is a directory")

要检查路径是否存在且是否是目录，可以使用函数和函数。例如：`os.path.exists()``os.path.isdir()`

```abap
import os

dir = os.path.join("C:\", "temp")
print(dir)

if os.path.exists(dir) or os.path.isdir(dir):
    print(f'The {dir} is a directory')
```

## 创建目录[](https://www.pythontutorial.net/python-basics/python-directory/#create-a-directory "Anchor for Create a directory")

要创建新目录，你用函数。而且在创建新目录之前，你应该先确认是否有目录存在。`os.mkdir()`

以下示例创建一个新目录，调用该目录。`python``c:temp`

```pgsql
import os

dir = os.path.join("C:\", "temp", "python")
if not os.path.exists(dir):
    os.mkdir(dir)
```

## 重命名目录[](https://www.pythontutorial.net/python-basics/python-directory/#rename-a-directory "Anchor for Rename a directory")

要重命名目录，你使用函数：`os.rename()`

```abap
import os

oldpath = os.path.join("C:\", "temp", "python")
newpath = os.path.join("C:\", "temp", "python3")

if os.path.exists(oldpath) and not os.path.exists(newpath):
    os.rename(oldpath, newpath)
    print("'{0}' was renamed to '{1}'".format(oldpath, newpath))
```

## 删除目录[](https://www.pythontutorial.net/python-basics/python-directory/#delete-a-directory "Anchor for Delete a directory")

要删除目录，你使用以下函数：`os.rmdir()`

```pgsql
import os

dir = os.path.join("C:\","temp","python")
if os.path.exists(dir):
    os.rmdir(dir)
    print(dir + ' is removed.')
```

## 递归遍历目录[](https://www.pythontutorial.net/python-basics/python-directory/#traverse-a-directory-recursively "Anchor for Traverse a directory recursively")

该函数允许你递归地遍历目录。该函数返回根目录、子目录和文件。`os.walk()``os.walk()`

以下示例展示了如何打印目录中的所有文件和目录：`c:temp`

```abap
import os

path = "c:\temp"
for root, dirs, files in os.walk(path):
    print("{0} has {1} files".format(root, len(files)))
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-directory/#summary "Anchor for Summary")

- 使用函数获取当前的工作目录。`os.getcwd()`
- 使用该函数将当前工作目录更改为新目录。`os.chdir()`
- 使用该函数创建一个新的目录。`os.mkdir()`
- 使用该函数重命名目录。`os.rename()`
- 使用该函数移除目录。`os.rmdir()`
- 使用函数列出目录内容。`os.walk()`