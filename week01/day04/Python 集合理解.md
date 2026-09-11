## Python 集合理解导论[](https://www.pythontutorial.net/python-basics/python-set-comprehension/#introduction-to-python-set-comprehension "Anchor for Introduction to Python Set comprehension")

假设你有以下[集合](https://www.pythontutorial.net/python-basics/python-set/)，由三个标签组成：

```python
tags = {'Django', 'Pandas', 'Numpy'}
```

要将集合中的标签转换为另一组小写标签，可以使用以下 [`for`](https://www.pythontutorial.net/python-basics/python-for-range/)循环：

```python
tags = {'Django', 'Pandas', 'Numpy'}

lowercase_tags = set()
for tag in tags:
    lowercase_tags.add(tag.lower())

print(lowercase_tags)
```

输出：

```python
{'django', 'numpy', 'pandas'}
```

工作原理：

- 首先，遍历集合中的每个元素。`tags`
- 其次，将每个标签转换为小写，并添加新的集合（`lowercase_tags`)

或者你可以用内置函数配合λ表达式：`map()`

```python
tags = {'Django', 'Pandas', 'Numpy'}
lowercase_tags = set(map(lambda tag: tag.lower(), tags))

print(lowercase_tags)
```
为了让代码更简洁，Python 提供了以下集合理解语法：

```python
{expression for element in set if condition}
```

集合理解允许你基于现有集合创建新的集合。

集合理解包含以下步骤：

- 首先，遍历集合的元素。
- 其次，对每个元素应用 an`expression`
- 第三，创建一组由表达式生成的新元素。
- 注意集合理解返回的是新集合，而不是修改原集合。
回到前面的例子，你可以通过以下集合理解来转换集合中的所有标签：`tags`

```python
tags = {'Django', 'Pandas', 'Numpy'}
lowercase_tags = {tag.lower() for tag in tags}

print(lowercase_tags)
```

输出：

```abap
{'numpy', 'pandas', 'django'}
```

这个语法看起来比for循环更简洁，也比函数更优雅。`map()`

## Python 集合理解与if子句示例[](https://www.pythontutorial.net/python-basics/python-set-comprehension/#python-set-comprehension-with-an-if-clause-example "Anchor for Python Set comprehension with an if clause example")

假设你想将集合中除 .`tags``Numpy`

为此，你可以在集合理解中添加一个条件，如下：

```python
tags = {'Django', 'Pandas', 'Numpy'}
new_tags = {tag.lower() for tag in tags if tag != 'Numpy'}

print(new_tags)
```

[试试看吧](https://www.pythontutorial.net/playground/?q=dGFncyA9IHsnRGphbmdvJywgJ1BhbmRhcycsICdOdW1weSd9Cm5ld190YWdzID0ge3RhZy5sb3dlcigpIGZvciB0YWcgaW4gdGFncyBpZiB0YWcgIT0gJ051bXB5J30KCnByaW50KG5ld190YWdzKQ%3D%3D)

输出：

```python
{'django', 'pandas'}
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-set-comprehension/#summary "Anchor for Summary")

- 使用Python集合理解，通过对现有集合的每个元素应用表达式，基于现有集合创建新集合。