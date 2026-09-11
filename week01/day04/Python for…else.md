## Python 入门......else 语句[](https://www.pythontutorial.net/python-basics/python-for-else/#introduction-to-the-python-for-else-statement "Anchor for Introduction to the Python for...else statement")

在 Python 中，[`for`](https://www.pythontutorial.net/python-basics/python-for-range/)语句可以有一个可选的从句，如果你来自 Java 或 C# 等其他语言，可能不太熟悉。`else`

以下显示了该语句与该子句的语法：`for``else`

```yaml
for item in iterables:
    # Process item
    if condition:
        break  # Terminate the loop prematurely
else:
    # Executed if the loop completes without a break
```

在该语法中：

- 只有**当**循环对 中的所有项都不碰到语句时，Python 才会执行该块。`else``for``iterables``break`
- 如果 Python 遇到一个语句，它会完全跳过该块。`break``else`
- 如果没有物品，Python **会立即**执行该块。`iterables``else`

与语句不同，语句不会提前结束循环。因此，如果循环正常完成，else块将执行。`break``[continue](https://www.pythontutorial.net/python-basics/python-continue/)`

以程图展示了该陈述的逻辑：`for...else`

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/python-for-else.png)如果你知道如何有效应用，这条款在某些情况下非常有用。`else`

## Python for…else example

假设你有一个人物[列表](https://www.pythontutorial.net/python-basics/python-list/)，每个人是一个词[典](https://www.pythontutorial.net/python-basics/python-dictionary/)，包含如下：`name``age`

```ini
people = [{'name': 'John', 'age': 25},
        {'name': 'Jane', 'age': 22},
        {'name': 'Peter', 'age': 30},
        {'name': 'Jenifer', 'age': 28}]
```

你想通过名字搜索一个人。

如果列表中包含该人，你希望显示该人的信息。否则，你需要显示一个信息，说明找不到该名字。

为此，你可以想出这样的程序：

```python
people = [{'name': 'John', 'age': 25},
        {'name': 'Jane', 'age': 22},
        {'name': 'Peter', 'age': 30},
        {'name': 'Jenifer', 'age': 28}]

name = 'Maria'

found = False
for person in people:
    if person['name'] == name:
        found = True
        print(person)
        break

if not found:
    print(f'{name} not found!')
```

[试试看吧](https://www.pythontutorial.net/playground/?q=cGVvcGxlID0gW3snbmFtZSc6ICdKb2huJywgJ2FnZSc6IDI1fSwKICAgICAgICB7J25hbWUnOiAnSmFuZScsICdhZ2UnOiAyMn0sCiAgICAgICAgeyduYW1lJzogJ1BldGVyJywgJ2FnZSc6IDMwfSwKICAgICAgICB7J25hbWUnOiAnSmVuaWZlcicsICdhZ2UnOiAyOH1dCgpuYW1lID0gJ01hcmlhJwoKZm91bmQgPSBGYWxzZQpmb3IgcGVyc29uIGluIHBlb3BsZToKICAgIGlmIHBlcnNvblsnbmFtZSddID09IG5hbWU6CiAgICAgICAgZm91bmQgPSBUcnVlCiAgICAgICAgcHJpbnQocGVyc29uKQogICAgICAgIGJyZWFrCgppZiBub3QgZm91bmQ6CiAgICBwcmludChmJ3tuYW1lfSBub3QgZm91bmQhJyk)

输出：

```pgsql
Maria not found!
```

工作原理：

- 首先，初始化一个变量，使用要搜索的人物名（）。`Maria`
- 然后，将旗帜（）设置为 。如果输入名与列表中的某个人匹配，将其值设为 ，显示该人的信息，并使用语句退出循环。`found``False``True``break`
- 最后，检查旗帜并显示一条信息。`found`

不过，如果你用这个语句，程序会短得多。`for else`

以下是使用该语句的新版本程序：`for else`

```python
people = [{'name': 'John', 'age': 25},
        {'name': 'Jane', 'age': 22},
        {'name': 'Peter', 'age': 30},
        {'name': 'Jenifer', 'age': 28}]

name = 'Maria'

for person in people:
    if person['name'] == name:
        print(person)
        break
else:
    print(f'{name} not found!')
```


通过使用语句，程序在循环后不需要使用 a 和 语句。`for else``flag``[if](https://www.pythontutorial.net/python-basics/python-if/)`

在这个新程序中，如果输入名与列表中的人匹配，它会显示该人的信息，并通过该语句退出循环。`break`

当循环遇到该语句时，子句不会执行。`break``else`

## 对空列表进行迭代[](https://www.pythontutorial.net/python-basics/python-for-else/#iterating-over-an-empty-list "Anchor for Iterating over an empty list")

以下示例使用语句遍历列表并显示该列表为空：`for...else`

```abap
people  = []

for person in people:
    print(person)
else:
    print("The list is empty.")
```

输出：

```php
The list is empty.
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-for-else/#summary "Anchor for Summary")

- 如果循环没有遇到语句，或者 iterables 对象是空的，可以用 Python 语句来执行代码块。`for...else``break`