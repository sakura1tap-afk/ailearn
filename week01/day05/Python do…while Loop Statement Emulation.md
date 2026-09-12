与循环不同，循环语句至少执行一次迭代。它在每次迭代结束时检查 ，并执行代码块直到 。`[while](https://www.pythontutorial.net/python-basics/python-while/)``do...while``condition``condition``False`

以下是 Python 循环的伪代码：`do...while`

```perl
do
    # code block
while condition
```

遗憾的是，Python 不支持这个循环。不过，你可以用循环和语句来模拟循环语句。`do...while``while``[break](https://www.pythontutorial.net/python-basics/python-break/)``do...while`

首先，在循环中指定 as，如下：`condition``True``while`

```python
while True:
    # code block
```

这使得代码块首次得以执行。然而，由于条件总是 ，它会形成一个不定循环。这不是我们预料中的。`True`

第二，设置一个条件以打破循环：`while`

```python
while True:
    # code block

    # break out of the loop
    if condition
        break
```

在这种语法中，代码块总是首次至少执行一个，并且每次迭代结束时检查该条件。

## Python do…while loop emulation example
假设你需要开发一个数字猜测游戏，逻辑如下：

- 首先，生成一个范围内的随机数，例如0到10。
- 然后，反复提示用户输入一个数字。如果输入的数字比随机数字大或小，给用户提示。如果输入的数字等于随机数，循环停止。

以下程序使用循环来开发猜数游戏：`while`

```python
from random import randint

# determine the range
MIN = 0
MAX = 10

# generate a secret number
secret_number = randint(MIN, MAX)

# initialize the attempt
attempt = 0

# The first attempt
input_number = int(input(f'Enter a number between {MIN} and {MAX}:'))
attempt += 1

if input_number > secret_number:
    print('It should be smaller.')
elif input_number < secret_number:
    print('It should be bigger.')
else:
    print(f'Bingo! {attempt} attempt(s)')

# From the second attempt
while input_number != secret_number:

    input_number = int(input(f'Enter a number between {MIN} and {MAX}:'))
    attempt += 1

    if input_number > secret_number:
        print('It should be smaller.')
    elif input_number < secret_number:
        print('It should be bigger.')
    else:
        print(f'Bingo! {attempt} attempt(s)')
```

以下是示例运行：

```bash
Enter a number between 0 and 10:5
It should be bigger.
Enter a number between 0 and 10:7
It should be bigger.
Enter a number between 0 and 10:8
Bingo! 3 attempt(s)
```

由于循环在每次迭代开始时检查条件，因此需要重复提示用户输入和检查数字的代码两次，一次在循环前，一次在循环内。`while`

为了避免重复代码，你可以用循环来模拟循环，具体如下：`while``do while`

```python
from random import randint

# determine the range
MIN = 0
MAX = 10

# generate a secret number
secret_number = randint(MIN, MAX)

# initialize the attempt
attempt = 0

while True:
    attempt += 1

    input_number = int(input(f'Enter a number between {MIN} and {MAX}:'))

    if input_number > secret_number:
        print('It should be smaller.')
    elif input_number < secret_number:
        print('It should be bigger.')
    else:
        print(f'Bingo! {attempt} attempt(s)')
        break
```
它是如何运作的。

- 首先，移除循环前的代码。`while`
- 其次，通过使用该陈述，添加条件，如果输入的数字等于随机数，则停止循环。`break`
## 摘要[](https://www.pythontutorial.net/python-basics/python-do-while/#summary "Anchor for Summary")

- Python 不支持 do-while 循环语句。
- 用循环和语句来模拟 Python 中的循环。`while``break``do...while`