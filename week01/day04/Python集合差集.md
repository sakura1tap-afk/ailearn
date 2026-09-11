## Python 集合差异介绍[](https://www.pythontutorial.net/python-basics/python-set-difference/#introduction-to-the-python-set-difference "Anchor for Introduction to the Python Set difference")

这两个[集合](https://www.pythontutorial.net/python-basics/python-set/)之间的差异导致一个新的集合，其中包含第一个集合中没有的元素。

假设你有以下和集合：`s1``s2`

```ini
s1 = {'Python', 'Java', 'C++'}
s2 = {'C#', 'Java', 'C++'}
```

和集合的差值得到以下一个元素的集合：`s1``s2`

```abap
{'Python'}
```

…因为只有第一个集合的元素不存在于第二个集合中。`'Python'`

集合差不是交换的。和集合的差值返回如下集合：`s2``s1`

```abap
{'C#'}
```

下图展示了和集合之间的区别：`s1``s2`

![Python 集合差异](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-Set-Difference.png)

以下维恩图展示了集合和的区别：`s2``s1`

![Python 集合差异示例](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-Set-Difference-Example.png)

在 Python 中，你可以使用集合法或集合差算子（）来求取集合之间的差值。`difference()``-`

### 1）使用Python的集合差（）方法来求得集合之间的差值[](https://www.pythontutorial.net/python-basics/python-set-difference/#1-using-python-set-difference-method-to-find-the-difference-between-sets "Anchor for 1) Using Python Set difference() method to find the difference between sets")

该类型有一种方法返回两个或多个集合之间的差值：`Set``difference()`

```r
set1.difference(s2, s3, ...)
```

例如，你可以使用集合法来求出和集合之间的差值：`difference()``s1``s2`

```perl
s1 = {'Python', 'Java', 'C++'}
s2 = {'C#', 'Java', 'C++'}
s = s1.difference(s2)

print(s)
```


输出：

```abap
{'Python'}
```

### 2）使用Python集合差算符（-）求得集合间的差[](https://www.pythontutorial.net/python-basics/python-set-difference/#2-using-python-set-difference-operator-to-find-the-difference-between-sets "Anchor for 2)
除了方法，Python 还提供了集合差算子（），可以让你找到集合之间的差。`difference()``-`

```ini
s = s1 - s2
```

以下示例使用差分算子（）来求出和集合之间的差值：`-``s1``s2`

```perl
s1 = {'Python', 'Java', 'C++'}
s2 = {'C#', 'Java', 'C++'}
s = s1 - s2

print(s)
```
### 集合差分法（-）法与集合差算子（-）[](https://www.pythontutorial.net/python-basics/python-set-difference/#the-set-difference-method-vs-set-difference-operator "Anchor for The set difference() method vs set difference operator (-)")

集合方法可以接受一个或多个[可迭代（](https://www.pythontutorial.net/python-basics/python-iterables/)[例如字符串、](https://www.pythontutorial.net/python-basics/python-string/)[列表](https://www.pythontutorial.net/python-basics/python-list/)、[词典](https://www.pythontutorial.net/python-basics/python-dictionary/)），而集合差算符（）只允许集合。`difference()``-`

当你把迭代函数传给集合方法时，它会先把可迭代函数转换成集合，然后再做差分运算。`difference()`
## 摘要[](https://www.pythontutorial.net/python-basics/python-set-difference/#summary "Anchor for Summary")

- 两个集合之间的差异会导致一个新的集合，包含第一个集合中没有的元素。
- 使用集合法或集合差算子（）来求取集合之间的差值。`difference()``-`