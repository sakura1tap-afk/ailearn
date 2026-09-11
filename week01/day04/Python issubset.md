## Python issubset（） 方法简介[](https://www.pythontutorial.net/python-basics/python-issubset/#introduction-to-the-python-issubset-method "Anchor for Introduction to the Python issubset() method")

假设你有两个集合A和B。如果A的所有元素也是B的元素，则A是集合B的子集。那么，集合B是集合A的超集。

下文文图说明集合A是集合B的子集：

![Python issubset：集合 A 是集合 B 的子集](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-issubset.png)

集合A和集合B可以相等。如果集合A**和集合B不**相等，则A是B的**真**子集。

在 Python 中，你可以使用 Set 方法检查一个集合是否是另一个集合的子集：`issubset()`

```css
set_a.issubset(set_b)
```

如果 是 的子集，则方法返回 。否则，返回 。`set_a``set_b``issubset()``True``False`

根据定义，集合也是自身的一个子集。以下示例返回：`True`

```yaml
numbers = {1, 2, 3, 4, 5}

print(numbers.issubset(numbers))
```
输出：

```yaml
True
```
## 使用子集算子[](https://www.pythontutorial.net/python-basics/python-issubset/#using-subset-operators "Anchor for Using subset operators")

除了使用该方法外，你还可以使用子集算子（）来检查某个集合是否是另一个集合的子集：`issubset()``<=`

```yaml
numbers = {1, 2, 3, 4, 5}
scores = {1, 2, 3}

result = scores <= numbers
print(result)  # True

result = numbers <= numbers
print(result)  # True
```

真子集算子（）检查 是否是 的真子集：`<``set_a``set_b`

```nginx
set_a < set_b
```
在这个例子中，集合不是自身的真子集，因此算符返回。`numbers``<``False`

## 摘要[](https://www.pythontutorial.net/python-basics/python-issubset/#summary "Anchor for Summary")

- 如果集合的所有元素也是该集合的元素，则称该集合是该集合的子集`A``B``A``B`
- 如果一个集合是另一个集合的子集，则使用集合方法返回。`issubset()``True`
- 此外，使用子集算子（<=）或真子集算子（<）来检查某个集合是另一个集合的子集还是真子集。