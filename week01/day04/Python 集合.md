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
## 从集合中移除元素[](https://www.pythontutorial.net/python-basics/python-set/#removing-an-element-from-a-set "Anchor for Removing an element from a set")

要从集合中移除元素，使用以下方法：`remove()`

```csharp
set.remove(element)
```

如果你移除一个集合中不存在的元素，会出现错误（）。例如：`KeyError`
为避免错误，你应使用操作符检查元素是否在集合中，然后再移除它：`in`
为了更方便，这套有个方法可以让你移除某个元素。如果元素不在列表中，也不会触发错误：`discard()`

```pgsql
set.discard(element)
```

## 从集合中返回元素[](https://www.pythontutorial.net/python-basics/python-set/#returning-an-element-from-a-set "Anchor for Returning an element from a set")

要从集合中移除和返回元素，使用该方法。`pop()`

由于集合中的元素没有特定的顺序，该方法从集合中移除一个未指定元素。`pop()`

如果你多次执行以下代码，每次都会显示不同的值：

```go
skills = {'Problem solving', 'Software design', 'Python programming'}
skill = skills.pop()

print(skill)
```

### 从集合中移除所有元素[](https://www.pythontutorial.net/python-basics/python-set/#removing-all-elements-from-a-set "Anchor for Removing all elements from a set")

要从集合中移除所有元素，使用以下方法：`clear()`

```python
set.clear()
```

## Frozen a set

要使集合不可变，可以使用内置的函数 。它会从现有集合返回一个新的不可变集合。例如：`frozenset()``frozenset()`

```python
skills = {'Problem solving', 'Software design', 'Python programming'}
skills = frozenset(skills)
```

之后，如果你尝试修改集合中的元素，会收到错误：

```python
skills = {'Problem solving', 'Software design', 'Python programming'}
skills = frozenset(skills)

skills.add('Django')
```
错误：

```python
AttributeError: 'frozenset' object has no attribute 'add'
```
## 循环于集合元素[](https://www.pythontutorial.net/python-basics/python-set/#looping-through-set-elements "Anchor for Looping through set elements")

由于集合是可迭代的，你可以用for循环来遍历其元素。例如：

```go
skills = {'Problem solving', 'Software design', 'Python programming'}

for skill in skills:
    print(skill)
```
输出：

```nginx
Software design
Python programming
Problem solving
```

要访问循环中当前元素的索引，可以使用内置函数：`enumerate()`

```abap
skills = {'Problem solving', 'Software design', 'Python programming'}

for index, skill in enumerate(skills):
    print(f"{index}.{skill}")
```

默认情况下，索引从零开始。要改变这个条件，你将起始值传递给函数的第二个参数。例如：`enumerate()`

```abap
skills = {'Problem solving', 'Software design', 'Python programming'}

for index, skill in enumerate(skills, 1):
    print(f"{index}.{skill}")
```
输出：

```css
1.Python programming
2.Problem solving
3.Software design
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-set/#summary "Anchor for Summary")

- 集合是一组**无序**的**不可变元素**。