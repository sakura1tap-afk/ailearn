
## Introduction to Python try…except…finally statement

该语句允许你[捕捉一个或多个子](https://www.pythontutorial.net/python-basics/python-try-except/)句中的例外，并在子句中处理它们。`try...except``try``except`

该命题还有一个可选子句：`try...except``finally`

```python
try:
    # code that may cause exceptions
except:
    # code that handle exceptions
finally:
    # code that clean up
```

无论异常是否发生，该子句始终执行。它在该条款和任何从句之后执行。`finally``try``except`

以程图展示了该条款：`try...except...finally`

![Python try catch finally statement](https://www.pythontutorial.net/wp-content/uploads/2020/10/try-except-finally.png)
## 蟒蛇试试看......只是......最后的陈述示例

以下示例使用了以下陈述：`try...except...finally`

```python
a = 10
b = 0

try:
    c = a / b
    print(c)
except ZeroDivisionError as error:
    print(error)
finally:
    print('Finishing up.')
```

输出：

```abap
division by zero
Finishing up.
```

在这个例子中，子句会引发异常，并且子句执行。`try``ZeroDivisionError``except``finally`

以下示例中的子句不会导致错误。因此，和 子句中的所有语句执行：`try``try``finally`

```python
a = 10
b = 2

try:
    c = a / b
    print(c)
except ZeroDivisionError as error:
    print(error)
finally:
    print('Finishing up.')
```

输出：

```abap
5.0
Finishing up.
```
## 蟒蛇试试看......最终陈述[](https://www.pythontutorial.net/python-basics/python-try-except-finally/#python-try-finally-statement "Anchor for Python try...finally statement")

该语句中的从句是可选的。所以你可以这样写：`catch``try...except...finally`

```python
try:
    # the code that may cause an exception
finally:
    # the code that always executes
```
通常，当你无法处理异常但想清理资源时，会使用这个语句。例如，你想关闭已打开的文件。

## 摘要[](https://www.pythontutorial.net/python-basics/python-try-except-finally/#summary "Anchor for Summary")

- 无论是否发生异常，都可以用 Python 语句执行代码块。`try...except...finally`
- 用该条款清理资源，比如关闭文件。`finally`