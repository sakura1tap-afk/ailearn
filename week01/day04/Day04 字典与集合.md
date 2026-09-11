# Day04｜字典、集合与循环 else

这一天的重点是字典与集合。前者适合按“键 → 值”组织数据，后者适合去重、成员判断和集合关系运算；同时补充 `for...else` 与 `while...else`。

## 1. 字典 dict

字典保存的是 **键值对（key-value pairs）**：

```python
person = {
    "name": "Tom",
    "age": 18,
    "active": True
}
```

### 读取值

```python
person["name"]
person.get("name")
```

区别：
- `person["xxx"]`：键不存在会抛出 `KeyError`。
- `person.get("xxx")`：键不存在默认返回 `None`。
- `person.get("xxx", default)`：可以指定默认值。

### 新增 / 修改

```python
person["city"] = "Beijing"   # 新增
person["age"] = 19            # 修改
```

### 删除

```python
del person["age"]
```

### 遍历

```python
for key in person:
    print(key)

for value in person.values():
    print(value)

for key, value in person.items():
    print(key, value)
```

`items()` 产生的是 `(key, value)` 形式的数据，因此可以直接解包。

Python 里通常把 `dictionary` 译作“字典”，`key` 译作“键”。

关联：[[Python 词典]]

## 2. 字典推导式 dictionary comprehension

基本形式：

```python
{key_expr: value_expr for item in iterable if condition}
```

例如：

```python
scores = {"Tom": 78, "Alice": 95, "Bob": 42}
passed = {name: score for name, score in scores.items() if score >= 60}
```

结果：

```python
{"Tom": 78, "Alice": 95}
```

和列表推导式一样，先确保普通 `for` 写法会写，再使用推导式简化。

关联：[[Python 词典理解]]

## 3. 集合 set

集合特点：
- 元素不重复。
- 没有可依赖的固定位置，不通过下标访问。
- 集合本身是可变的，可以 `add()` / `remove()`。
- 放进集合的元素必须是可哈希的，例如数字、字符串、元组通常可以；列表、字典不能直接作为集合元素。

```python
skills = {"Python", "Git", "SQL"}
```

空集合一定要写：

```python
empty = set()
```

`{}` 是空字典，不是空集合。

### 常用操作

```python
skills.add("Docker")
skills.remove("Git")     # 不存在会 KeyError
skills.discard("Java")   # 不存在也不会报错
"Python" in skills
len(skills)
```

关联：[[Python 集合]]

## 4. 集合推导式 set comprehension

基本形式：

```python
{expression for item in iterable if condition}
```

例如得到 1～10 中偶数的平方：

```python
result = {x ** 2 for x in range(1, 11) if x % 2 == 0}
```

关联：[[Python 集合理解]]

## 5. 并集 union

取两个集合中出现过的所有元素：

```python
a | b
a.union(b)
```

示例：

```python
{1, 2, 3} | {3, 4, 5}
# {1, 2, 3, 4, 5}
```

关联：[[Python集合合并]]

## 6. 交集 intersection

只保留两个集合共同拥有的元素：

```python
a & b
a.intersection(b)
```

```python
{1, 2, 3} & {2, 3, 4}
# {2, 3}
```

关联：[[Python 集交集]]

## 7. 差集 difference

`a - b` 表示：属于 `a`，但不属于 `b` 的元素。

```python
a - b
a.difference(b)
```

注意差集有方向：

```python
a - b != b - a
```

关联：[[Python集合差集]]

## 8. 对称差 symmetric difference

只保留“只出现在其中一个集合”的元素，共同元素被排除：

```python
a ^ b
a.symmetric_difference(b)
```

关联：[[Python 对称差分]]

## 9. 子集 issubset()

如果 `a` 的所有元素都包含在 `b` 中：

```python
a.issubset(b)
# 或
a <= b
```

例如：

```python
{1, 2}.issubset({1, 2, 3})   # True
```

关联：[[Python issubset]]

## 10. 超集 issuperset()

如果 `a` 包含 `b` 的全部元素：

```python
a.issuperset(b)
# 或
a >= b
```

关联：[[Python issuperset]]

## 11. 不相交 isdisjoint()

如果两个集合没有任何共同元素：

```python
a.isdisjoint(b)
```

例如：

```python
{1, 2}.isdisjoint({3, 4})  # True
```

关联：[[Python 不相交集]]

## 12. for...else

`else` 不是“if 的 else”，而是属于 `for` 循环。

```python
for item in items:
    if condition:
        break
else:
    print("循环没有被 break 打断")
```

核心规则：
- 循环正常结束：执行 `else`。
- 遇到 `break` 提前退出：不执行 `else`。
- 空可迭代对象也属于“正常结束”，因此会执行 `else`。

典型用途：查找一个元素，找到了就 `break`；整个循环都没找到，再进入 `else`。

关联：[[Python for…else]]

## 13. while...else

规则和 `for...else` 一样：

```python
while condition:
    if something:
        break
else:
    print("while 正常结束，没有 break")
```

- 条件变为 `False`，循环正常结束：执行 `else`。
- `break`：跳过 `else`。

关联：[[Python while else]]

## 14. Day04 重点

优先做到：

1. 能独立创建、读取、修改、遍历字典。
2. 能使用 `items()` 写 `for key, value in dict.items()`。
3. 知道集合最核心价值是 **去重 + 成员判断 + 集合运算**。
4. 能分清 `union / intersection / difference / symmetric_difference`。
5. 知道 `issubset / issuperset / isdisjoint` 在判断什么。
6. 能解释 `for...else` 为什么只有“没有 break”时才执行 `else`。

> [!tip] 和前几天知识的连接
> 字典遍历用到了 [[Python 中解包列表|解包]]；字典/集合推导式沿用了 [[Python 列表解析|列表推导式]] 的思路；集合去重可以和之前的 `remove_duplicates()` 练习对照。
