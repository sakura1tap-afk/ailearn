# Python 字典（dict）

> 文件名保留原来的“词典”，正文统一使用 Python 社区更常见的中文术语：**字典**。

字典用 **键（key）→ 值（value）** 保存数据。

```python
person = {
    "name": "Tom",
    "age": 18,
    "active": True
}
```

## 1. 读取值

### 方括号

```python
print(person["name"])
```

如果键不存在，会抛出 `KeyError`。

### get()

```python
print(person.get("name"))
print(person.get("city"))
print(person.get("city", "unknown"))
```

`get()` 在键不存在时默认返回 `None`，也可以提供默认值。

## 2. 新增和修改

字典使用同一种写法新增或修改：

```python
person["city"] = "Beijing"  # 新增
person["age"] = 19           # 修改
```

## 3. 删除

```python
del person["active"]
```

如果需要更灵活的删除，后面还会遇到 `pop()`。

## 4. 成员判断

```python
"name" in person
```

注意：对字典使用 `in`，默认判断的是 **键** 是否存在。

## 5. 遍历字典

### 遍历键

```python
for key in person:
    print(key)
```

也可以显式写：

```python
for key in person.keys():
    print(key)
```

### 遍历值

```python
for value in person.values():
    print(value)
```

### 同时遍历键和值

```python
for key, value in person.items():
    print(key, value)
```

`items()` 提供的是 `(key, value)` 形式的数据，所以这里复用了之前学过的 [[Python 中解包列表|序列解包]]。

## 6. 键和值的限制

- 值可以是几乎任意 Python 对象。
- 键必须是可哈希（hashable）的对象，例如字符串、数字、部分元组。
- 列表和字典本身通常不能直接作为键。

初学阶段先记：**最常见的键就是字符串。**

## 7. 插入顺序

现代 Python 中，字典会保留键值对的插入顺序。但字典的核心用途仍然是“通过键找值”，不要把它当作依赖数字下标访问的列表。

## 8. 一道小例子

```python
scores = {
    "Tom": 78,
    "Alice": 95,
    "Bob": 88
}

for name, score in scores.items():
    if score >= 80:
        print(name, score)
```

## 易错点

- “dictionary” 翻译成 **字典**，不是“词典”。
- “key” 翻译成 **键**，不是“密钥”。
- `person["x"]` 和 `person.get("x")` 在键不存在时行为不同。
- `for x in person` 中的 `x` 是键。

## 自查

不用运行代码，回答：

```python
user = {"name": "Kong", "age": 23}
```

1. 怎么安全读取不存在的 `email` 并给默认值 `"none"`？
2. 怎么把 `age` 改成 24？
3. 怎么同时遍历名字和年龄？

关联：[[00 Day04整理版]]、[[Python 词典理解]]
