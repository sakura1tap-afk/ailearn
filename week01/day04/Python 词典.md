
## Python 词典类型的介绍[](https://www.pythontutorial.net/python-basics/python-dictionary/#introduction-to-the-python-dictionary-type "Anchor for Introduction to the Python Dictionary type")

Python 词典是一组键值对，每个键对应一个值。

键值对中的值可以是[数字](https://www.pythontutorial.net/python-basics/python-numbers/)、[字符串](https://www.pythontutorial.net/python-basics/python-string/)、[列表](https://www.pythontutorial.net/python-basics/python-list/)、[元组](https://www.pythontutorial.net/python-basics/python-tuples/)，甚至是另一个词典。事实上，你可以在 Python 中使用任何有效类型的值作为键值对的值。

键值对中的键必须是不可变的。换句话说，密钥不能更改，例如数字、字符串、元组等。

### 1）使用方括号符号[](https://www.pythontutorial.net/python-basics/python-dictionary/#1-using-square-bracket-notation "Anchor for 1) Using square bracket notation")

要访问与键关联的值，请将键放入方括号内：

```python
dict[key]
```

### 2）使用 get（） 方法[#](https://www.pythontutorial.net/python-basics/python-dictionary/#2-using-the-get-method "Anchor for 2) Using the get() method")
## 添加新的键值对[](https://www.pythontutorial.net/python-basics/python-dictionary/#adding-new-key-value-pairs "Anchor for Adding new key-value pairs")
如果密钥不存在，方法返回而不是抛出 。注意，这意味着没有值存在。`get()``None``KeyError``None`

当密钥不存在时，方法还会通过将默认值传递给第二个参数来返回默认值。`get()`

如果键不存在于字典中，以下示例返回该字符串：`'000-00-0000'``ssn``person`

```python
person = {
    'first_name': 'John',
    'last_name': 'Doe',
    'age': 25,
    'favorite_colors': ['blue', 'green'],
    'active': True
}

ssn = person.get('ssn', '000-00-0000')
print(ssn)
```

[试试看吧](https://www.pythontutorial.net/playground/?q=cGVyc29uID0gewogICAgJ2ZpcnN0X25hbWUnOiAnSm9obicsCiAgICAnbGFzdF9uYW1lJzogJ0RvZScsCiAgICAnYWdlJzogMjUsCiAgICAnZmF2b3JpdGVfY29sb3JzJzogWydibHVlJywgJ2dyZWVuJ10sCiAgICAnYWN0aXZlJzogVHJ1ZQp9Cgpzc24gPSBwZXJzb24uZ2V0KCdzc24nLCAnMDAwLTAwLTAwMDAnKQpwcmludChzc24p)

输出：

```python
000-00-0000
```

由于词典具有动态结构，你可以随时添加新的键值对。

要向词典添加新的键值对，你需要在方括号内指定词典名称，后面跟着新键和新值。

以下示例为词典添加了一个新的键值对：`person`

```python
person['gender'] = 'Famale'
```

## 修改键值对中的值[](https://www.pythontutorial.net/python-basics/python-dictionary/#modifying-values-in-a-key-value-pair "Anchor for Modifying values in a key-value pair")

要修改与键关联的值，你需要用方括号指定字典名称（键）并指定与键关联的新值：

```python
dict[key] = new_value
```

## 移除键值对[](https://www.pythontutorial.net/python-basics/python-dictionary/#removing-key-value-pairs "Anchor for Removing key-value pairs")

要通过键去除键值对，使用以下语句：`del`

```python
del dict[key]
```
## 在词典中循环[](https://www.pythontutorial.net/python-basics/python-dictionary/#looping-through-a-dictionary "Anchor for Looping through a dictionary")

要检查字典，可以用循环遍历其键值对、键或值。`for`

注意，自从 Python 3.7 起，当你循环字典时，键值对会按插入顺序出现。

### 循环词典中所有键值对[](https://www.pythontutorial.net/python-basics/python-dictionary/#looping-all-key-value-pairs-in-a-dictionary "Anchor for Looping all key-value pairs in a dictionary")

Python 词典提供了一个方法，它返回一个对象，该对象包含列表中的键值对的元组列表。`items()`

例如：

```python
person = {
    'first_name': 'John',
    'last_name': 'Doe',
    'age': 25,
    'favorite_colors': ['blue', 'green'],
    'active': True
}

print(person.items())
```

输出：

```python
dict_items([('first_name', 'John'), ('last_name', 'Doe'), ('age', 25), ('favorite_colors', ['blue', 'green']), ('active', True)])
```
要遍历字典中所有键值对，使用一个双变量循环，解[压列表中的每个元组](https://www.pythontutorial.net/python-basics/python-unpack-list/)：`for``key``value`

```python
person = {
    'first_name': 'John',
    'last_name': 'Doe',
    'age': 25,
    'favorite_colors': ['blue', 'green'],
    'active': True
}

for key, value in person.items():
    print(f"{key}: {value}")
```
### 在字典中循环所有键[](https://www.pythontutorial.net/python-basics/python-dictionary/#looping-through-all-the-keys-in-a-dictionary "Anchor for Looping through all the keys in a dictionary")

有时候，你只是想循环字典里的所有按键。在这种情况下，你可以用循环配合方法。`for``keys()`

该方法返回一个包含字典中密钥列表的对象。`keys()`

例如：

```python
person = {
    'first_name': 'John',
    'last_name': 'Doe',
    'age': 25,
    'favorite_colors': ['blue', 'green'],
    'active': True
}

for key in person.keys():
    print(key)
```
### 循环解析词典中的所有值[](https://www.pythontutorial.net/python-basics/python-dictionary/#looping-through-all-the-values-in-a-dictionary "Anchor for Looping through all the values in a dictionary")

该方法返回一个没有键的值列表。`values()`

要循环词典中的所有值，使用一个 for 循环，方法如下：`values()`

```python
person = {
    'first_name': 'John',
    'last_name': 'Doe',
    'age': 25,
    'favorite_colors': ['blue', 'green'],
    'active': True
}

for value in person.values():
    print(value)
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-dictionary/#summary "Anchor for Summary")

- Python 词典是一组键值对，每个键都有对应的值。
- 使用方括号或方法通过按键访问某个值。`get()`
- 使用该语句从字典中移除键的键值对。`del`
- 使用循环来遍历字典中的键、值和键值对。`for`