**总结**：在本教程中，你将学习不相交集合以及如何使用Python方法检查两个集合是否相交。`isdisjoint()`
## Python 互交集介绍[](https://www.pythontutorial.net/python-basics/python-disjoint-sets/#introduction-to-python-disjoint-sets "Anchor for Introduction to Python disjoint sets")

当两个[集合](https://www.pythontutorial.net/python-basics/python-set/)没有共同元素时，称为不相交。换句话说，两个不相交集[是空集](https://www.pythontutorial.net/python-basics/python-set-intersection/)的集合。

例如，和集合互不相交，因为它们没有共同元素。`{1,3,5}``{2,4,6}`

以下维恩图展示了这些不相交的集合：

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-disjoint-sets.png)

在 Python 中，你使用 Set 方法检查两个集合是否互不相交：`isdisjoint()`

```python
set_a.isdisjoint(set_b)
```

如果 和 不相交，则该方法返回。否则，返回 。`isdisjoint()``True``set_a``set_b``False`

该方法也接受任何可迭代，而不仅仅是集合。`isdisjoint()`

如果你传递一个列表、元组或词典，方法会在检查前将其转换为集合。`isdisjoint()`

## Python isdisjoint（） 方法示例[](https://www.pythontutorial.net/python-basics/python-disjoint-sets/#python-isdisjoint-method-examples "Anchor for Python isdisjoint() method examples")

以下示例使用了该方法来检查集合和集合是否相交：`isdisjoint()``odd_numbers``even_numbers`

```python
odd_numbers = {1, 3, 5}
even_numbers = {2, 4, 6}

result = odd_numbers.isdisjoint(even_numbers)

print(result)
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-disjoint-sets/#summary "Anchor for Summary")

- 如果两个集合没有共同元素，则称它们互不相交。
- 使用Python集合方法检查两个集合是否不相交。`isdisjoint()`