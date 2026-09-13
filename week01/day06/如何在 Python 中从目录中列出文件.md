**总结**：在这个教程中，你将学习如何使用 Python 函数在目录中列出文件。`os.walk()`

有时，你可能想列出目录中的所有文件进行处理。例如，你可能想找到某个目录的所有图片并调整它们的大小。要列出目录中的所有文件，可以使用这个函数。`os.walk()`

该函数通过从上而下或自下而上移动该树来生成目录中的文件名。该函数为目录树中的每个目录生成一个包含三个字段（、 、 和 ）的元组。`` os.`walk()` ```os.walk()``dirpath``dirnames``filenames`

注意该函数检查整个目录树。因此，你可以用它获取根目录中所有目录及其子目录中的所有文件。`os.walk()`

## ython 列表文件示例[](https://www.pythontutorial.net/python-basics/python-list-files/#python-list-file-example "Anchor for Python list file example")

假设你有一个包含以下目录和文件的文件夹：`D:web`

```python
D:web
├── assets
|  ├── css
|  |  └── style.css
|  └── js
|     └── app.js
├── blog
|  ├── read-file.html
|  └── write-file.html
├── about.html
├── contact.html
└── index.html
```

以下示例展示了如何使用该函数列出目录中的所有HTML文件：`os.walk()``D:web`

```python
import os


path = 'D:\web'

html_files = []

for dirpath, dirnames, filenames in os.walk(path):
    for filename in filenames:
        if filename.endswith('.html'):
            html_files.append(os.path.join(dirpath, filename))

for html_file in html_files:
    print(html_file)
```

输出：

```python
D:webabout.html
D:webcontact.html
D:webindex.html
D:webblogread-file.html
D:webblogwrite-file.html
```

它是如何运作的。

首先，初始化一个列表以存储HTML文件的路径：

```python
html_files = []
```

其次，调用函数来检查文件夹的目录：`os.walk()``D:web`

```python
for dirpath, dirnames, filenames in os.walk(path):
```

它存储目录，文件名则存储在该目录中。`dirpath`

第三，循环文件名，如果它们的扩展名是：`html_files``.html`

```python
# ...
for filename in filenames:
        if filename.endswith('.html'):
            html_files.append(os.path.join(dirpath, filename))
```

注意，通过将 与 连接，返回文件名的完整路径。`os.path.join()``dirpath``filename`

最后，打印输出文件列表中的文件名：`html_files`

```python
for html_file in html_files:
    print(html_file)
```

## 定义可重用列表文件函数[](https://www.pythontutorial.net/python-basics/python-list-files/#defining-a-reusable-list-files-function "Anchor for Defining a reusable list files function")

通过使用该函数，我们可以定义一个可复用的函数，如下：`os.walk()``list_files()`

```python
import os


def list_files(path, extentions=None):
    """ List all files in a directory specified by path
    Args:
        path - the root directory path
        extensions - a iterator of file extensions to include, pass None to get all files.
    Returns:
        A list of files specified by extensions
    """
    filepaths = []
    for root, _, files in os.walk(path):
        for file in files:
            if extentions is None:
                filepaths.append(os.path.join(root, file))
            else:
                for ext in extentions:
                    if file.endswith(ext):
                        filepaths.append(os.path.join(root, file))

    return filepaths


if __name__ == '__main__':
    filepaths = list_files(r'D:web', ('.html', '.css'))
    for filepath in filepaths:
        print(filepath)
```

输出：

```python
D:webabout.html
D:webcontact.html
D:webindex.html
D:webassetscssstyle.css
D:webblogread-file.html
D:webblogwrite-file.html
```

## 让列表文件更高效地运行[](https://www.pythontutorial.net/python-basics/python-list-files/#make-list-files-function-more-efficient "Anchor for Make list files function more efficient")

如果文件数量较少，这个功能就没问题。然而，当文件数量较大时，返回大量文件列表内存效率较低。`list_files()`

为了解决这个问题，你可以使用[生成器](https://www.pythontutorial.net/advanced-python/python-generators/)一次输出每个文件，而不是返回列表：

```python
import os


def list_files(path, extentions=None):
    """ List all files in a directory specified by path
    Args:
        path - the root directory path
        extensions - a iterator of file extensions to include, pass None to get all files.
    Returns:
        A list of files specified by extensions
    """
    for root, _, files in os.walk(path):
        for file in files:
            if extentions is None:
                yield os.path.join(root, file)
            else:
                for ext in extentions:
                    if file.endswith(ext):
                        yield os.path.join(root, file)


if __name__ == '__main__':
    filepaths = list_files(r'D:web', ('.html', '.css'))
    for filepath in filepaths:
        print(filepath)
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-list-files/#summary "Anchor for Summary")

- 使用递归地将文件列入目录的功能。`os.walk()`
- 定义一个可重复使用的函数，用于在目录中列出文件。`os.walk()`