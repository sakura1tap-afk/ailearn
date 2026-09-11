## Python 入门 while else 语句[](https://www.pythontutorial.net/python-basics/python-while-else/#introduction-to-python-while-else-statement "Anchor for Introduction to Python while else statement")

在 Python 中，该语句可能包含一个可选子句：`[while](https://www.pythontutorial.net/python-basics/python-while/)``else`

```objectivec
while condition:
    # code block to run
else:
    # else clause code block
```

在此语法中，每次迭代开始时检查 。语句内部的代码块只要 为 ，就会执行。`condition``while``condition``True`

当 变为 且循环正常运行时，子句将执行。然而，如果循环被 a 或 语句提前终止，子句将无法执行。`condition``False``else``[break](https://www.pythontutorial.net/python-basics/python-break/)``return``else`

以程图展示了该条款：`while...else`

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-while-else.png)

如果你熟悉其他编程语言，比如[JavaScript](https://www.javascripttutorial.net/javascript-while-loop/)、Java或C#，你会发现这个从句在循环语境中相当奇怪。`else`

然而，这条款在某些情况下非常有用。让我们来看一个使用该陈述的例子。`while...else``while...else`

Python If...else语句实例

假设我们有以下水果列表，每个水果是一个由名称和键组成的词典：`fruit``qty`

```ini
basket = [
    {'fruit': 'apple', 'qty': 20},
    {'fruit': 'banana', 'qty': 30},
    {'fruit': 'orange', 'qty': 10}
]
```

我们想做一个允许用户输入水果名称的程序。根据输入名称，我们会从列表中搜索，如果水果在列表中，会显示它的数量。`basket`

如果找不到水果，我们允许用户输入该水果的数量并将其添加到列表中。

以下程序是首次尝试：

```abap
basket = [
    {'fruit': 'apple', 'qty': 20},
    {'fruit': 'banana', 'qty': 30},
    {'fruit': 'orange', 'qty': 10}
]

fruit = input('Enter a fruit:')

index = 0
found_it = False

while index < len(basket):
    item = basket[index]
    # check the fruit name
    if item['fruit'] == fruit:
        found_it = True
        print(f"The basket has {item['qty']} {item['fruit']}(s)")
        break

    index += 1

if not found_it:
    qty = int(input(f'Enter the qty for {fruit}:'))
    basket.append({'fruit': fruit, 'qty': qty})
    print(basket)
```

工作原理：

- 首先，通过函数提示用户输入。`input()`
- 其次，将 初始化为零，并标记为 。该索引将用于访问列表。如果找到水果名称，旗帜将设置为 。`index``found_it``False``index``found_it``True`
- 第三，遍历列表，检查水果名称是否与输入名称匹配。如果是，将标志设置为 ，显示水果数量，然后使用语句退出循环。`found_it``True``break`
- 最后，检查循环后的标志，如果是 ，则将新水果加入列表。`found_it``found_it``False`
以下是使用该语句的新版本程序：`while else`

```abap
basket = [
    {'fruit': 'apple', 'qty': 20},
    {'fruit': 'banana', 'qty': 30},
    {'fruit': 'orange', 'qty': 10}
]

fruit = input('Enter a fruit:')

index = 0

while index < len(basket):
    item = basket[index]
    # check the fruit name
    if item['fruit'] == fruit:
        print(f"The basket has {item['qty']} {item['fruit']}(s)")
        found_it = True
        break

    index += 1
else:
    qty = int(input(f'Enter the qty for {fruit}:'))
    basket.append({'fruit': fruit, 'qty': qty})
    print(basket)
```

在该程序中，子句取代了环后必须有旗帜和语句的需求。`else``found_it``if`

如果找不到该水果，循环将正常终止，并执行子句以添加一个新的水果到列表中。`while``else`

然而，如果找到了果实，循环将被命题遇到并提前终止。在这种情况下，该条款不会被执行。`while``break``else`

## 摘要[](https://www.pythontutorial.net/python-basics/python-while-else/#summary "Anchor for Summary")

- 语句中的子句将在循环的 时执行，循环正常运行且未遇到 or 语句。`else``while else``condition``while``False``break``return`
- 每当你需要在循环中设置标志时，试试 Python 语句。`while else``while`