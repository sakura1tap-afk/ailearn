## 使用 open（） 函数创建新的文本文件[](https://www.pythontutorial.net/python-basics/python-create-text-file/#using-the-open-function-to-create-a-new-text-file "Anchor for Using the open() function to create a new text file")

要创建新的文本文件，你需要使用这个函数。该函数有许多参数。不过，我们将重点关注前两个参数：`open()``open()`

```ini
f = open(path_to_file, mode)
```

在这个语法中，参数指定你想创建的文本文件路径。`path_to_file`

创建新文本文件时，您可以使用以下一种模式：

- `'w'`——打开一个写作文件。如果该文件不存在，函数会创建一个新文件。否则，它会覆盖现有文件的内容。`open()`
- `'x'`—— 打开一个专属创建的文件。如果文件存在，函数会触发错误（）。否则，它会生成文本文件。`open()``FileExistsError`

例如，以下步骤创建一个名为 的新文件，并写入一些文本：`readme.txt`

```abap
with open('readme.txt', 'w') as f:
    f.write('Create a new text file!')
```

该脚本会在脚本文件所在的同一目录中创建一个名为该名称的文件。如果你想在指定的目录中创建文件，例如，你需要在创建文件前确保该目录的存在。否则，你会有[例外](https://www.pythontutorial.net/python-oop/python-exceptions/)。例如：`readme.txt``docs/readme.text``docs`

```python
with open('docs/readme.txt', 'w') as f:
    f.write('Create a new text file!')
```

错误：

```yaml
FileNotFoundError: [Errno 2] No such file or directory: 'docs/readme.txt'
```

在这个例子中，Python [会触发异常](https://www.pythontutorial.net/python-oop/python-raise-exception/)，因为该目录不存在。因此，它无法在该目录中创建该文件。要解决这个问题，你需要先创建目录，然后在那个文件夹里创建文件。`docs``readme.txt``docs``readme.txt`

此外，你也可以用 try-except 语句处理异常，具体如下：

```python
try:
    with open('docs/readme.txt', 'w') as f:
        f.write('Create a new text file!')
except FileNotFoundError:
    print("The 'docs' directory does not exist")
```

输出：

```plaintext
The 'docs' directory does not exist
```

如果你不想创建新的文本文件，以防它已经存在，可以在调用函数时使用以下模式：`'x'``open()`

```python
with open('readme.txt', 'x') as f:
    f.write('Create a new text file!')
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-create-text-file/#summary "Anchor for Summary")

- 使用带有 or 模式的函数创建新的文本文件。`open()``'w'``'x'`