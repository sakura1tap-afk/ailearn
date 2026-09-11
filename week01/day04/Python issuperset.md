
在本教程中，你将学习如何使用Python方法检查一个集合是否是另一个[集合](https://www.pythontutorial.net/python-basics/python-set/)的超集。`issuperset()`

## Python issuperset 方法简介[](https://www.pythontutorial.net/python-basics/python-issuperset/#introduction-to-python-issuperset-method "Anchor for Introduction to Python issuperset method")

假设你有两个集合：A 和 B。如果 A 是 B 的超集，则称 B 的所有元素都是 A 的元素。

如果A是B的超集，那么B是A的一个子集。要检查一个集合是否是另一个集合的子集，可以使用该方法。`[issubset()](https://www.pythontutorial.net/python-basics/python-issubset/)`

如果集合A和集合B不相等，则集合A是集合B的**真**超集。

逻辑上，集合是自身的超集。

下图说明集合A是集合B的超集，因为集合B中的元素1、2、3也属于集合A：

![Python 超集示例](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-issuperset.png)

在 Python 中，你使用集合方法来检查一个集合是否是另一个集合的超集：`issuperset()`

```python
set_a.issuperset(set_b)
```

如果 是 的超集，则返回 。否则，返回 。`issuperset()``True``set_a``set_b``False`

## Python issuperset（） 方法示例[](https://www.pythontutorial.net/python-basics/python-issuperset/#python-issuperset-method-examples "Anchor for Python issuperset() method examples")

以下示例使用了 来检查数字集合是否是分数集合的超集：`issuperset()`

```python
numbers = {1, 2, 3, 4, 5}
scores = {1, 2, 3}

result = numbers.issuperset(scores)#True

print(result)
```

## 使用超集算符[](https://www.pythontutorial.net/python-basics/python-issuperset/#using-superset-operators "Anchor for Using superset operators")

>= 算符判断一个集合是否是另一个集合的超集：

```python
set_a >= set_b
```

如果 是 的超集，则算符返回。否则，返回 。例如：`>=``True``set_a``set_b``False`

```python
numbers = {1, 2, 3, 4, 5}
scores = {1, 2, 3}

result = numbers >= scores
print(result)  # True

result = numbers >= numbers
print(result)  # True
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-issuperset/#summary "Anchor for Summary")

- 如果集合B的所有元素都是集合A的元素，则该集合A是集合B的超集。
- 使用Python方法检查一个集合是否是另一个集合的超集。`issuperset()`
- 使用超集算子（）或真超集算子（）来检查一个集合是另一个集合的超集还是真超集。`>=``>`