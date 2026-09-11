## 集合并集简介[](https://www.pythontutorial.net/python-basics/python-set-union/#introduction-to-the-set-union "Anchor for Introduction to the set union")

两个[集合](https://www.pythontutorial.net/python-basics/python-set/)的并返回一个包含两个集合不同元素的新集合。

假设你有以下集合：

```ini
s1 = {'Python', 'Java'}
s2 = {'C#', 'Java'}
```

s1和s2集合的并返回如下集合：

```abap
{'Java','Python', 'C#'}
```

通常，你用维恩图来说明两个集合的并集。例如：

![Python Set Union Example](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-Set-Union-Example.png)

## 使用union（）方法的并集[](https://www.pythontutorial.net/python-basics/python-set-union/#union-sets-using-union-method "Anchor for Union sets using union() method")

在 Python 中，要合并两个或更多集合，你使用以下方法：`union()`

```rust
new_set = set.union(another_set, ...)
```
以下示例展示了如何将 和 集合合并：`s1``s2`

```perl
s1 = {'Python', 'Java'}
s2 = {'C#', 'Java'}

s = s1.union(s2)

print(s)
```
## 使用|算符[](https://www.pythontutorial.net/python-basics/python-set-union/#union-sets-using-the-operator "Anchor for Union sets using the | operator")

Python 为你提供了集合并集操作符，可以将两个集合合并：`|`

```ini
new_set = set1 | set2
```

## union（） 方法与集合 union 算子[](https://www.pythontutorial.net/python-basics/python-set-union/#the-union-method-vs-set-union-operator "Anchor for The union() method vs. set union operator")

该方法接受一个或多个[可迭代，](https://www.pythontutorial.net/python-basics/python-iterables/)将可迭代映射为集合，并执行并集。`union()`

以下示例展示了如何将[列表](https://www.pythontutorial.net/python-basics/python-list/)传递给该方法：`union()`

```yaml
rates = {1, 2, 3}
ranks = [2, 3, 4]

ratings = rates.union(ranks)

print(ratings)
```

[试试看吧](https://www.pythontutorial.net/playground/?q=cmF0ZXMgPSB7MSwgMiwgM30KcmFua3MgPSBbMiwgMywgNF0KCnJhdGluZ3MgPSByYXRlcy51bmlvbihyYW5rcykKCnByaW50KHJhdGluZ3Mp)

输出：

```yaml
{1, 2, 3, 4}
```

然而，并集算符（）只允许集合，不允许像方法那样的可重复集合。`|``union()`

以下示例会导致错误：

```ini
rates = {1, 2, 3}
ranks = [2, 3, 4]

ratings = rates | ranks
```

[试试看吧](https://www.pythontutorial.net/playground/?q=cmF0ZXMgPSB7MSwgMiwgM30KcmFua3MgPSBbMiwgMywgNF0KCnJhdGluZ3MgPSByYXRlcyB8IHJhbmtz)

错误：

```typescript
TypeError: unsupported operand type(s) for |: 'set' and 'list'
```

总之，该方法接受可迭代，而并算符只允许集合。`union()`

## 摘要[](https://www.pythontutorial.net/python-basics/python-set-union/#summary "Anchor for Summary")

- 两个或多个集合的并集返回两个集合的不同值。
- 使用方法或集合并算符（）来合并两个或更多集合。`union()``|`
- 该方法接受一个或多个可遍历映射，而集合联集算符（）仅接受集合。`union()``|`