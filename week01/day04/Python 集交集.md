
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