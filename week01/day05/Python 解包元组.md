
## 审查 Python 元组[](https://www.pythontutorial.net/python-basics/python-unpacking-tuple/#reviewing-python-tuples "Anchor for Reviewing Python tuples")

Python 用逗号（）定义[元组](https://www.pythontutorial.net/python-basics/python-tuples/)，而不是括号。例如，以下定义了一个包含两个元素的元组：`,``()`

```python
1,2 
```

Python 使用括号使元组更清晰：

```python
(1, 2)
```

Python 还使用括号来创建空元组：

```python
()
```

此外，你可以这样使用构造函数：`tuple()`

```python
tuple()
```

要定义一个只有一个元素的元组，你仍然需要使用逗号。以下示例说明了如何定义一个元素元组：

```python
1,
```
它相当于以下内容：

```python
(1, )
```

注意以下是[整数](https://www.pythontutorial.net/advanced-python/python-integers/)，而非元组：

```python
(1)
```

## 拆包元组[](https://www.pythontutorial.net/python-basics/python-unpacking-tuple/#unpacking-a-tuple "Anchor for Unpacking a tuple")

解包元组意味着将元组的元素拆分为单个[变量](https://www.pythontutorial.net/python-basics/python-variables/)。例如：

```python
x, y = (1, 2)
```

左侧：

```python
x, y
```

是两个变量和的元组。`x``y`

右侧也是两个整数和的元组。`1``2`

该表达式将右侧（1， 2）的元组元素分配给左侧的每个变量（x， y），基于每个元素的相对位置。

在上述例子中，将取 ，且 将取 。`x``1``y``2`

再举一个例子：

```python
x, y ,z = 10, 20, 30
```

右侧是三个整数、 、 的元组。你可以快速查看其类型如下：`10``20``30`

```python
numbers = 10, 20, 30
print(type(numbers))
```

输出：

```python
<class 'tuple'>
```

在上述例子中，变量 、 和 分别取值 、 和 。`x``y``z``10``20``30`

## 使用解包元组交换两个变量的值[](https://www.pythontutorial.net/python-basics/python-unpacking-tuple/#using-unpacking-tuple-to-swap-values-of-two-variables "Anchor for Using unpacking tuple to swap values of two variables")

传统上，交换两个变量的值时，会使用类似这样的临时变量：

```python
x = 10
y = 20

print(f'x={x}, y={y}')

tmp = x
x = y
y = tmp

print(f'x={x}, y={y}')
```
输出：

```python
x=10, y=20
x=20, y=10   
```

在 Python 中，你可以使用解包元组语法来实现相同的结果：
以下表达式交换两个变量 x 和 y 的值。

```python
x, y = y, x
```

在此表达式中，Python 先计算右侧，然后将左侧变量赋值到右侧。

## ValueError：数值太多无法解析[](https://www.pythontutorial.net/python-basics/python-unpacking-tuple/#valueerror-too-many-values-to-unpack "Anchor for ValueError: too many values to unpack")

以下示例将元组的元素拆包为变量。但这会导致一个错误：

```python
x, y = 10, 20, 30
```

错误：

```python
ValueError: too many values to unpack (expected 2)
```

这个误差是因为右侧返回三个值，而左侧只有两个变量。

为了解决这个问题，你可以添加一个变量：`_`

```python
x, y, _ = 10, 20, 30
```
该变量在 Python 中是一个正则变量。按照惯例，它被称为虚拟变量。`_`

通常，你不在意时用虚拟变量解包，之后再用它的值。

## 使用*操作符进行扩展拆包[](https://www.pythontutorial.net/python-basics/python-unpacking-tuple/#extended-unpacking-using-the-operator "Anchor for Extended unpacking using the * operator")

有时候，你不想把元组里的每一项都拆包。例如，你可能想拆解第一和第二元素。在这种情况下，你可以使用操作符。例如：`*`

```python
r, g, *other = (192, 210, 100, 0.5)
```

输出：

```python
192
210
[100, 0.5]
```

在这个例子中，Python 将 映射到 。此外，Python 会把剩余元素和打包成列表，并将其赋值到变量上。`192``r``210``g``100``0.5``other`

请注意，在拆包任务的左侧，你只能使用一次操作符。`*`

以下示例会导致错误：

```python
x, y, *z, *t = (10, 20, 30, '10:30')
```

错误：

```python
SyntaxError: two starred expressions in assignment
```

## 使用右侧的*操作符[](https://www.pythontutorial.net/python-basics/python-unpacking-tuple/#using-the-operator-on-the-right-hand-side "Anchor for Using the * operator on the right hand side")

Python 允许你使用右侧的操作符。假设你有两个元组：`*`

```python
odd_numbers = (1, 3, 5)
even_numbers = (2, 4, 6)
```

以下示例使用该操作符来解包这些元组并将其合并为一个元组：`*`

```python
odd_numbers = (1, 3, 5)
even_numbers = (2, 4, 6)

numbers = (*odd_numbers, *even_numbers)
print(numbers)
```

输出：

```python
(1, 3, 5, 2, 4, 6)
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-unpacking-tuple/#summary "Anchor for Summary")

- Python 使用逗号（）来定义元组，而不是括号。`,`
- 解包元组意味着将元组的单个元素分配给多个变量。
- 使用该操作符将解包赋值的剩余元素分配到列表中，并赋值到变量。`*`