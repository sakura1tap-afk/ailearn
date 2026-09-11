## Python 集合类型介绍[](https://www.pythontutorial.net/python-basics/python-set/#introduction-to-the-python-set-type "Anchor for Introduction to the Python Set type")

Python 集合是一个无序的不可变元素列表。它的意思是：

- 集合中的元素是无序的。
- 集合中的元素是唯一的。集合不允许重复元素。
- 集合中的元素不能被更改。例如，它们可以是[数字](https://www.pythontutorial.net/python-basics/python-numbers/)、[字符串](https://www.pythontutorial.net/python-basics/python-string/)和[元组](https://www.pythontutorial.net/python-basics/python-tuples/)，但不能是[列表](https://www.pythontutorial.net/python-basics/python-tuples/)或[词典](https://www.pythontutorial.net/python-basics/python-dictionary/)。
在 Python 中定义集合时，使用大括号 。例如：`{}`

```ini
skills = {'Python programming', 'Databases', 'Software design'}
```

注意词典也使用卷括号，但其元素是键值对。

要定义空集，不能像这样使用卷括号：

```ini
empty_set = {}
```

…因为它定义了一个空字典。

因此，你需要使用内置函数：`set()`

```ini
empty_set = set()
```
空集合在[布尔](https://www.pythontutorial.net/python-basics/python-boolean/)上下文中被评估为 False。例如：

```dart
skills = set()

if not skills:
    print('Empty sets are falsy')
```

事实上，你可以把[迭代](https://www.pythontutorial.net/python-basics/python-iterables/)函数传递给函数来创建一个集合。例如，你可以像这样传递一个可迭代列表给函数：`set()``set()`

```dart
skills = set(['Problem solving','Critical Thinking'])
print(skills)
```

[试试看吧](https://www.pythontutorial.net/playground/?q=c2tpbGxzID0gc2V0KFsnUHJvYmxlbSBzb2x2aW5nJywnQ3JpdGljYWwgVGhpbmtpbmcnXSkKcHJpbnQoc2tpbGxzKQ%3D%3D)

输出：

```abap
{'Critical Thinking', 'Problem solving'}
```
注意，元素的原始顺序可能无法保持。

如果可迭代存在重复元素，函数会将它们移除。例如：`set()`

```dart
characters = set('letter')
print(characters)
```
输出：

```abap
{'r', 'l', 't', 'e'}
```

在这个例子中，字符串有两个 e 和 t 字符，集合（）会分别去除它们。`'letter'`
## Getting sizes of a set

要计算集合中的元素数量，使用内置函数。`len()`

```javascript
len(set)
```

例如：

```yaml
ratings = {1, 2, 3, 4, 5}
size = len(ratings)

print(size)    
```

输出：

```yaml
5
```
## 检查元素是否属于集合[](https://www.pythontutorial.net/python-basics/python-set/#checking-if-an-element-is-in-a-set "Anchor for Checking if an element is in a set")

要检查集合是否包含元素，使用运算符：`in`

```javascript
element in set
```

## 向集合添加元素[](https://www.pythontutorial.net/python-basics/python-set/#adding-elements-to-a-set "Anchor for Adding elements to a set")

要向集合添加元素，使用以下方法：`add()`

```pgsql
set.add(element)
```

例如：

```dockerfile
skills = {'Python programming', 'Software design'}
skills.add('Problem solving')

print(skills)
```