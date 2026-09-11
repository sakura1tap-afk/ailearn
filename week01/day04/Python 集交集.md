
## 总结：[](https://www.pythontutorial.net/python-basics/python-set-intersection/#tldr "Anchor for TL;DR")

在 Python 中，你可以使用集合方法`intersection()`或集合交算符（&）来交两个或多个[集合](https://www.pythontutorial.net/python-basics/python-set/)：

```ini
new_set = set1.intersection(set2, set3)
new_set = set1 & set2 & set3
```

交集（）方法和 & 算符的表现相同。
## Python 集合交叉点简介[](https://www.pythontutorial.net/python-basics/python-set-intersection/#introduction-to-python-set-intersection "Anchor for Introduction to Python set intersection")

当两个或多个[集合](https://www.pythontutorial.net/python-basics/python-set/)相交时，你会得到一个由所有集合中都存在元素组成的新集合。

假设你有两个集合和：`s1``s2`

```ini
s1 = {'Python', 'Java','C++'}
s2 = {'C#', 'Java', 'C++' }
```

这两个集合的交集返回一个包含两个元素和的新集合：`'Java'``'C++'`

```ini
s = {'Java', 'C++'}
```

…因为它们是两套中唯一存在的元素。

下图展示了两个集合和2的交集：`s1``s`

![Python 集合交集示例](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-Set-Intersection.png)

集合交集有许多有用的应用。例如，你可以用“集合交叉点”在社交网络应用中查找两位朋友的共同收藏，或者在人力资源应用中搜索两位或以上员工的共同技能。

在 Python 中，你可以使用集合方法或集合交算符（）来交两个或多个集合。`intersection()``&`

### 使用 Python 集合 交集（）方法来交两个或多个集合[](https://www.pythontutorial.net/python-basics/python-set-intersection/#using-python-set-intersection-method-to-intersect-two-or-more-sets "Anchor for Using Python set intersection() method to intersect two or more sets")

这个例子展示了如何使用集合法来交两个或多个集合：`intersection()`

```ini
new_set = set1.intersection(set2, set3, ...)
```

以下展示了如何利用该方法来交集 s1 和 s2：`intersection()`

```perl
s1 = {'Python', 'Java', 'C++'}
s2 = {'C#', 'Java', 'C++'}

s = s1.intersection(s2)

print(s)
```

### 使用Python集合交集（&）算子来交集两个或多个集合[](https://www.pythontutorial.net/python-basics/python-set-intersection/#using-python-set-intersection-operator-to-intersect-two-or-more-sets "Anchor for Using Python set intersection (&) operator to intersect two or more sets")

Python 为你提供了集合交算符（），允许你与两个或多个集合相交：`&`

```ini
new_set = s1 & s2 & s3 & ...
```

以下示例使用集合交算符（）来交集 s1 和 s2：`&`

```perl
s1 = {'Python', 'Java', 'C++'}
s2 = {'C#', 'Java', 'C++'}

s = s1 & s2

print(s)
```
### 集合交汇法与集合交算符（&）[](https://www.pythontutorial.net/python-basics/python-set-intersection/#set-intersection-method-vs-set-intersection-operator "Anchor for Set intersection() method vs set intersection operator (&)")

集合交算符只允许集合，而集合方法`intersection()`则可以接受任何[可迭代，](https://www.pythontutorial.net/python-basics/python-iterables/)如[字符串](https://www.pythontutorial.net/python-basics/python-string/)、[列表](https://www.pythontutorial.net/python-basics/python-list/)和[字典](https://www.pythontutorial.net/python-basics/python-dictionary/)。

如果你把迭代函数传给方法，它会在交集前把可迭代函数转换成集合。`intersection()`

然而，如果与可迭代函数一起使用集合交算符（），则会产生错误。`&`

以下示例使用了将集合与列表相交的方法：`intersection()`

```yaml
numbers = {1, 2, 3}
scores = [2, 3, 4]

numbers = numbers.intersection(scores)

print(numbers)
```

输出：

```yaml
{2, 3}
```

如果你用集合交算符（）代替，会出现错误：`&`

```yaml
numbers = {1, 2, 3}
scores = [2, 3, 4]

numbers = numbers & scores

print(numbers)
```

输出：

```typescript
TypeError: unsupported operand type(s) for &: 'set' and 'list'
```
## 摘要[](https://www.pythontutorial.net/python-basics/python-set-intersection/#summary "Anchor for Summary")

- 两个或多个集合的交集返回所有集合中都存在的元素。
- 使用方法或集合交算符（）来相交两个或多个集合。`intersection()``&`