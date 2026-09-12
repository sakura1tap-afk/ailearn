## 语法错误[](https://www.pythontutorial.net/python-basics/python-try-except/#syntax-errors "Anchor for Syntax errors")

当你写出无效的Python代码时，会出现语法错误。例如：

```python
current = 1
if current < 10
current += 1
```

如果你尝试运行这段代码，会出现以下错误：

```bash
File "d:/python/try-except.py", line 2
    if current < 10
                  ^
SyntaxError: invalid syntax
```

在这个例子中，Python 解释器在 [`if` 语句](https://www.pythontutorial.net/python-basics/python-if/)后面缺少冒号（）时检测到了错误。`:`

Python解释器会显示出错误发生位置的文件名和行号，方便你修复。

## 例外情况[](https://www.pythontutorial.net/python-basics/python-try-except/#exceptions "Anchor for Exceptions")

即使你的代码语法有效，执行时也可能出现错误。

在 Python 中，执行过程中发生的错误称为**异常**。异常的原因主要来自代码执行的环境。例如：

- [读取](https://www.pythontutorial.net/python-basics/python-read-text-file/)一个不[存在](https://www.pythontutorial.net/python-basics/python-check-if-file-exists/)的文件。
- 连接到离线的远程服务器。
- 糟糕的用户输入。

当异常发生时，程序不会自动处理。这会导致错误信息。

例如，以下程序计算销售增长：

```python
# get input net sales
print('Enter the net sales for')

previous = float(input('- Prior period:'))
current = float(input('- Current period:'))

# calculate the change in percentage
change = (current - previous) * 100 / previous

# show the result
if change > 0:
    result = f'Sales increase {abs(change)}%'
else:
    result = f'Sales decrease {abs(change)}%'

print(result)
```

它是如何运作的。

- 首先，提示用户输入两个数字：前一期和当前期的净销售额。
- 然后，计算销售增长的百分比并展示结果。

当你运行程序并输入为当前期间的净销售额时，Python 解释器会输出以下结果：`120'`

```bash
Enter the net sales for
- Prior period:100
- Current period:120'
Traceback (most recent call last):
  File "d:/python/try-except.py", line 5, in <module>
    current = float(input('- Current period:'))
ValueError: could not convert string to float: "120'"
```

Python 解释器显示了一个包含异常详细信息的追溯：

- 指向导致异常的源代码文件（）的路径。`d:/python/try-except.py`
- 导致异常的那行代码 （`line 5`)
- 导致该异常的陈述`current = float(input('- Current period:'))`
- 例外类型`ValueError`
- 错误提示：`ValueError: could not convert string to float: "120'"`

由于无法将字符串转换为数字，Python 解释器发出了异常。`float()``120'``ValueError`

在 Python 中，异常有不同类型，如 、 、 等。`TypeError``NameError`

## 处理异常[](https://www.pythontutorial.net/python-basics/python-try-except/#handling-exceptions "Anchor for Handling exceptions")

为了让程序更稳健，你需要在异常发生后处理它。换句话说，你需要发现异常并通知用户，以便他们修复。

处理这个问题的一个好方法是不展示 Python 解释器返回的内容。相反，你会用更易用的错误信息替换那个错误信息。

为此，您可以使用Python语句：`try...except`

```python
try:
    # code that may cause error
except:
    # handle errors
```
该声明的运作方式如下：`try...except`

- 该条款中的语句先执行。`try`
- 如果没有例外，则跳过该子句，完成语句的执行。`except``try`
- 如果在子句中的任何语句发生异常，则**跳过剩余的子句**，执行该子句。`try``except`

以程图展示了该陈述：`try...except`

![Python try...except](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-try-except.png)

所以，要用语句处理异常，你要把可能引发异常的代码放在子句里，把处理异常的代码放在子句里。`try...except``try``except`

```python
except:
    print('Error! Please enter a number for net sales.')
```

如果你再次运行程序并输入净销售额（不是数字），程序会发出你在区块中指定的消息：`except`

```bash
Enter the net sales for
- Prior period:100
- Current period:120'
Error! Please enter a number for net sales.
```

## 捕捉特定例外[](https://www.pythontutorial.net/python-basics/python-try-except/#catching-specific-exceptions "Anchor for Catching specific exceptions")

当你将上一期的净销售额输入为零时，你会看到以下提示：

```bash
Enter the net sales for
- Prior period:0
- Current period:100
Error! Please enter a number for net sales.
```

在这种情况下，前一期和当前期的净销售额都是数字，但程序仍然会发出错误信息。必须有另一个例外。

该语句允许你处理特定的异常。要捕捉选中的异常，你需要在关键词后方放置异常类型：`try...except``except`

```python
try:
    # code that may cause an exception
except ValueError as error:
    # code to handle the exception
```

例如：

```python
try:
    # get input net sales
    print('Enter the net sales for')

    previous = float(input('- Prior period:'))
    current = float(input('- Current period:'))

    # calculate the change in percentage
    change = (current - previous) * 100 / previous

    # show the result
    if change > 0:
        result = f'Sales increase {abs(change)}%'
    else:
        result = f'Sales decrease {abs(change)}%'

    print(result)
except ValueError:
    print('Error! Please enter a number for net sales.')
```

当你运行程序并输入净销售的字符串时，也会收到同样的错误信息。

但是，如果你将上一期的净销售额输入零：

```bash
Enter the net sales for
- Prior period:0
- Current period:100
```

…你会收到以下错误信息：

```bash
Traceback (most recent call last):
  File "d:/python/try-except.py", line 9, in <module>
    change = (current - previous) * 100 / previous
ZeroDivisionError: float division by zero
```

这次你得到了例外。除以零例外的原因是以下陈述：`ZeroDivisionError`

```python
change = (current - previous) * 100 / previous
```

原因是 的值为零。`previous`

## 处理多重异常[](https://www.pythontutorial.net/python-basics/python-try-except/#handling-multiple-exceptions "Anchor for Handling multiple exceptions")

通过指定多个子句，允许你处理多个例外：`try...except``except`

```python
try:
    # code that may cause an exception
except Exception1 as e1:
    # handle exception
except Exception2 as e2:
    # handle exception
except Exception3 as e3:
    # handle exception 
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-try-except/#summary "Anchor for Summary")

- 用Python语句优雅地处理异常。`try...except`
- 尽量在块中设置具体例外。`except`
- 利用该语句来捕捉其他异常情况。`except Exception`