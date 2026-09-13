## 总结[](https://www.pythontutorial.net/python-basics/python-read-text-file/#tldr "Anchor for TL;DR")

以下演示了如何将文件中的所有文本读取成字符串：`readme.txt`

```python
with open('readme.txt') as f:
    lines = f.readlines()
```

## Python 中读取文本文件的步骤[](https://www.pythontutorial.net/python-basics/python-read-text-file/#steps-for-reading-a-text-file-in-python "Anchor for Steps for reading a text file in Python")

要在 Python 中阅读文本文件，你只需按照以下步骤操作：

- 首先，使用该函数打开一个文本文件进行阅读。`open()`
- 其次，使用文件 ， ， 或文件对象的方法从文本文件中读取文本。`read()``readline()``readlines()`
- 第三，使用文件法关闭文件。`close()`
这是一个可选参数。它是字符串，用来指定你想以何种方式打开文件。下表显示了打开文本文件的可用模式：`mode`

|模式|描述|
|---|---|
|`'r'`|打开用于阅读文本的文件|
|`'w'`|打开文本文件来写文本|
|`'a'`|打开一个文字文件来添加文字|
例如，要打开一个与程序同文件夹中名称的文件，使用以下代码：`the-zen-of-python.txt`

```python
 f = open('the-zen-of-python.txt','r')
```

### 2）文本阅读方法[](https://www.pythontutorial.net/python-basics/python-read-text-file/#2-reading-text-methods "Anchor for 2) Reading text methods")

文件对象为你提供了三种从文本文件读取文本的方法：

- `read(size)`——根据可选大小读取文件的部分内容，并返回该内容的字符串。如果省略大小，方法会从上次读到文件末尾。如果文件的末尾被到达，方法返回一个空字符串。`read()``read()`
- `readline()`– 从文本文件读取一行，并返回该行字符串。如果文件的末尾被到达，返回一个空字符串。`readline()`
- `readlines()`——将文本文件的所有行读入字符串列表。如果你有一个小文件，想操作整个文件的文本，这种方法非常有用。
### 3）闭（）方法[](https://www.pythontutorial.net/python-basics/python-read-text-file/#3-close-method "Anchor for 3) close() method")

你打开的文件会一直保持开着，直到你用该方法关闭它。`close()`

关闭不再使用的文件非常重要，原因如下：

- 首先，当你在脚本中打开文件时，文件系统通常会锁定它，直到关闭它之前，其他程序或脚本都无法使用。
- 其次，你的文件系统有有限数量的文件描述符，你能创建的描述符数量有限，否则它们会用完。虽然这个数字可能很高，但打开大量文件可能会耗尽你的文件系统资源。
- 第三，打开大量文件可能导致多个[进程](https://www.pythontutorial.net/python-concurrency/differences-between-processes-and-threads/)同时修改一个文件时出现竞态，导致各种意外行为。

以下展示了如何调用关闭文件的方法：`close()`

```python
f.close()
```

要自动关闭文件而不调用该方法，使用如下语句：`close()``with`

```python
with open(path_to_file) as f:
    contents = f.readlines()
```

实际上，你会用该语句自动关闭文件。`with`

你看到文件中每行后面都有空行的原因是，文本文件中的每行都有一个换行字符（n）。要去除空行，可以用这个方法。例如：`strip()`

```python
with open('the-zen-of-python.txt') as f:
    [print(line.strip()) for line in f.readlines()]
```

以下示例展示了如何使用 逐行读取文本文件：`readline()`

```python
with open('the-zen-of-python.txt') as f:
    while True:
        line = f.readline()
        if not line:
            break
        print(line.strip())
```

输出：

```python
Explicit is better than implicit.
Complex is better than complicated.
Flat is better than nested.
...
```
## 一种更简洁的方式逐行阅读文本文件[](https://www.pythontutorial.net/python-basics/python-read-text-file/#a-more-concise-way-to-read-a-text-file-line-by-line "Anchor for A more concise way to read a text file line by line")

该函数返回一个[可迭代](https://www.pythontutorial.net/python-basics/python-iterables/)对象的文件对象。因此，你可以用循环来遍历文本文件的行，如下：`open()``for`

```python
with open('the-zen-of-python.txt') as f:
    for line in f:
        print(line.strip())
```

这是一种更简洁的逐行阅读文本文件的方法。
## 读取UTF-8文本文件[](https://www.pythontutorial.net/python-basics/python-read-text-file/#read-utf-8-text-files "Anchor for Read UTF-8 text files")

前面示例中的代码在ASCII文本文件上运行良好。然而，如果你涉及的是日语、中文和韩语等其他语言，文本文件就不是简单的ASCII文本文件。而且很可能是一个UTF-8文件，使用了不仅仅是标准ASCII文本字符的多个字符。

要打开 UTF-8 文本文件，你需要把 传递给函数，指示它从文件中预期 UTF-8 字符。`encoding='utf-8'``open()`

演示时，你将使用以下包含一些日语引言的文件。`[quotes.txt](https://www.pythontutorial.net/wp-content/uploads/2020/10/quotes.txt)`

以下展示了如何循环播放文件：`quotes.txt`

```python
with open('quotes.txt', encoding='utf8') as f:
    for line in f:
        print(line.strip())
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-read-text-file/#summary "Anchor for Summary")

- 使用该模式中的函数打开文本文件进行阅读。`open()``'r'`
- 使用、 或 方法来读取文本文件。`read()``readline()``readlines()`
- 每次用方法或语句读取完文件后，务必关闭文件。`close()``with`
- 用 来读取 UTF-8 文本文件。`encoding='utf-8'`