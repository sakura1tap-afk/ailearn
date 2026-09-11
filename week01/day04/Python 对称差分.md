## 集合对称差导论[](https://www.pythontutorial.net/python-basics/python-symmetric-difference/#introduction-to-the-symmetric-difference-of-sets "Anchor for Introduction to the symmetric difference of sets")

两个[集合](https://www.pythontutorial.net/python-basics/python-set/)之间的对称差是指一组元素，它们属于任一集合，但不在它们的[交](https://www.pythontutorial.net/python-basics/python-set-intersection/)集中。

假设你有以下和集合：`s1``s2`

```ini
s1 = {'Python', 'Java', 'C++'}
s2 = {'C#', 'Java', 'C++'}
```

和集合的对称差返回如下集合：`s1``s2`

```abap
{'C#', 'Python'}
```

从输出中可以清楚看到，返回集合中的元素要么在 in，要么在 set，但不在它们的交集中。`s1``s2`

下图展示了和集合的对称差异：`s1``s2`

![两个集合的Python对称差](https://www.pythontutorial.net/wp-content/uploads/2020/10/Symmetric-Difference-Python.png)

在Python中，你可以使用集合法或对称差算子（）求出两个或多个集合的对称差。`symmetric_difference()``^`

### 使用 symmetric_difference（） 方法求集合的对称差[](https://www.pythontutorial.net/python-basics/python-symmetric-difference/#using-the-symmetric_difference-method-to-find-the-symmetric-difference-of-sets "Anchor for Using the symmetric_difference() method to find the symmetric difference of sets")

该类型具有返回两个或多个集合对称差的方法：`Set``symmetric_difference()`

```ini
new_set = set1.symmetric_difference(set2, set3,...)
```

例如，下述求出 和 集合的对称差：`s1``s2`

```perl
s1 = {'Python', 'Java', 'C++'}
s2 = {'C#', 'Java', 'C++'}

s = s1.symmetric_difference(s2)

print(s)
```
输出：

```abap
{'C#', 'Python'}
```

注意，该方法返回的是新集合，而不会修改原始集合。`symmetric_difference()`
### 利用对称差算子（^）求集合的对称差[#](https://www.pythontutorial.net/python-basics/python-symmetric-difference/#using-the-symmetric-difference-operator-to-find-the-symmetric-difference-of-sets "Anchor for Using the symmetric difference operator(^) to find the symmetric difference of sets")
除了使用集合法外，你还可以使用对称差算子（）来求出两个或多个集合之间的对称差：`symmetric_difference()``^`

```ini
new_set = set1 ^ set2 ^...
```

以下示例展示了如何将对称差分算子（）应用于 和 集合：`^``s1``s2`

```perl
s1 = {'Python', 'Java', 'C++'}
s2 = {'C#', 'Java', 'C++'}

s = s1 ^ s2

print(s)
```

### symmetric_difference（）方法与对称差分算子（^）[](https://www.pythontutorial.net/python-basics/python-symmetric-difference/#the-symmetric_difference-method-vs-symmetric-difference-operator "Anchor for The symmetric_difference() method vs symmetric difference operator (^)")

该方法接受一个或多个可[迭代](https://www.pythontutorial.net/python-basics/python-iterables/)，可是[字符串](https://www.pythontutorial.net/python-basics/python-string/)、[列表](https://www.pythontutorial.net/python-basics/python-list/)或[字典](https://www.pythontutorial.net/python-basics/python-dictionary/)。`symmetric_difference()`

如果可迭代函数不是集合，方法会先将它们转换为集合，然后返回它们的对称差。
然而，对称差算子（）仅适用于集合。如果你用它来配合非集合的迭代函数，会出现错误。
错误：

```typescript
TypeError: unsupported operand type(s) for ^: 'set' and 'list'
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-symmetric-difference/#summary "Anchor for Summary")

- 两个或多个集合之间的对称差是一组元素，这些元素在所有集合中都存在，但不在它们的交集中。
- 使用集合法或对称差算子（）来求两个或多个集合的对称差。`symmetric_difference()``^`