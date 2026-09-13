## Introduction##  to the Python try…except…else statement

该语句有一个可选子句，语法如下：`[try](https://www.pythontutorial.net/python-basics/python-try-except/)``else`

```abap
try:
    # code that may cause errors
except:
    # code that handle exceptions
else:
    # code that executes when no exception occurs
```
该声明的运作方式如下：`try...except...else`

- 如果子句中出现异常，Python 跳过子句中剩余的语句，并执行该语句。`try``try``except`
- 如果该条款中没有例外，该条款将被执行。`try``else`

当你包含该条款时，该条款在该条款之后和之前执行。`[finally](https://www.pythontutorial.net/python-basics/python-try-except-finally/)``else``try``finally`

## 摘要[](https://www.pythontutorial.net/python-basics/python-try-except-else/#summary "Anchor for Summary")

- 使用 Python 语句为你提供了一种在异常情况下控制程序流程的方法。`try...except...else`
- 如果条款中没有例外，则该条款执行。`else``try`
- 如果是这样，该条款在该条款之后和之前执行。`else``try``finally`