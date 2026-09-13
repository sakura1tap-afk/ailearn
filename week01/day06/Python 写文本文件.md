## 总结[](https://www.pythontutorial.net/python-basics/python-write-text-file/#tldr "Anchor for TL;DR")

以下图展示了如何将字符串写入文本文件：

```abap
with open('readme.txt', 'w') as f:
    f.write('readme')
```

## 写入文本文件的步骤[](https://www.pythontutorial.net/python-basics/python-write-text-file/#steps-for-writing-to-text-files "Anchor for Steps for writing to text files")

要用 Python 写入文本文件，请遵循以下步骤：

- 首先，打开文本文件以便使用该函数写入（或附加）。`open()`
- 其次，使用或方法写入文本文件。`write()``writelines()`
- 第三，用该方法关闭文件。`close()`

以下是该函数的基本语法：`open()`

```ini
f = open(file, mode)
```

该函数接受许多参数。但你会专注于前两个：`open()`

- 参数指定了你想打开写入的文本文件路径。`file`
- 参数指定你想打开文本文件的模式。`mode`

写入文本文件时，您可以使用以下一种模式：

|模式|描述|
|---|---|
|`'w'`|打开一个文本文件进行写作。如果文件存在，函数一打开就会截断所有内容。如果该文件不存在，函数会创建一个新文件。|
|`'a'`|打开一个用于添加文本的文本文件。如果文件存在，函数会在文件末尾附加内容。|
|‘+’|打开一个文本文件进行更新（包括阅读和写入）。|

该函数返回一个文件对象，该对象具有两种有用的写入文本的方法：和。`open()``write()``writelines()`

- 该方法将字符串写入文本文件。`write()`
- 该方法一次将字符串列表写入文件。`writelines()`

该方法接受[可递代](https://www.pythontutorial.net/python-basics/python-iterables/)对象，而不仅仅是[列表](https://www.pythontutorial.net/python-basics/python-list/)，因此你可以向方法传递字符串元[组](https://www.pythontutorial.net/python-basics/python-tuples/)、字符串[集合](https://www.pythontutorial.net/python-basics/python-set/)等。`writelines()``writelines()`

要写入文本文件的行，你需要手动添加一个新的行字符：

```abap
f.write('n')
f.writelines('n')
```

## 编写文本文件示例[](https://www.pythontutorial.net/python-basics/python-write-text-file/#writing-text-file-examples "Anchor for Writing text file examples")

以下示例展示了如何使用该函数将文本列表写入文本文件：`write()`

```abap
lines = ['Readme', 'How to write text files in Python']
with open('readme.txt', 'w') as f:
    for line in lines:
        f.write(line)
        f.write('n')
```

如果readme.txt文件不存在，函数会创建一个新文件。`open()`

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-write-text-file-write-method-1.png)

以下演示如何将文本字符串列表写入文本文件：

```abap
lines = ['Readme', 'How to write text files in Python']
with open('readme.txt', 'w') as f:
    f.writelines(lines)
```

如果你把列表中的每个元素都当作一行，你需要像这样与换行字符串接：

```abap
lines = ['Readme', 'How to write text files in Python']
with open('readme.txt', 'w') as f:
    f.write('n'.join(lines))
```

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-write-text-file-write-method.png)

## 录文本文件[](https://www.pythontutorial.net/python-basics/python-write-text-file/#appending-text-files "Anchor for Appending text files")

要添加文本文件，你需要打开该文本文件进行添加模式。以下示例为文件添加新行：`readme.txt`

```abap
more_lines = ['', 'Append text files', 'The End']

with open('readme.txt', 'a') as f:
    f.write('n'.join(more_lines))
```

输出：

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-write-text-file-appending-mode.png)

## 写入UTF-8文本文件[](https://www.pythontutorial.net/python-basics/python-write-text-file/#writing-to-a-utf-8-text-file "Anchor for Writing to a UTF-8 text file")

如果你用前面示例的代码写入 UTF-8 字符到文本文件，会出现类似这样的错误：

```rust
UnicodeEncodeError: 'charmap' codec can't encode characters in position 0-44: character maps to <undefined>
```

要打开文件并写入 UTF-8 字符，你需要将参数传递给函数。`encoding='utf-8'``open()`

以下示例展示了如何将UTF-8字符写入文本文件：

```abap

quote = '成功を収める人とは人が投げてきたレンガでしっかりした基盤を築くことができる人のことである。'

with open('quotes.txt', 'w', encoding='utf-8') as f:
    f.write(quote)
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-write-text-file/#summary "Anchor for Summary")

- 使用带有 or 模式的功能打开文本文件进行添加。`open()``w``a`
- 写入完成后务必关闭文件，或打开文件时使用语句。`close()``with`
- 使用和方法写入文本文件。`write()``writelines()`
- 将 传递给将 UTF-8 字符写入文件的函数。`encoding='utf-8'``open()`