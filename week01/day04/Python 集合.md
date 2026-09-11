# Python 集合（set）

集合适合处理 **去重、成员判断、集合关系**。

```python
skills = {"Python", "Git", "SQL"}
```

## 1. 集合的核心特点

- 元素不重复。
- 不通过数字下标访问元素。
- 集合本身通常可以修改。
- 放进集合的元素必须可哈希，例如数字、字符串、部分元组通常可以；列表、字典不能直接作为集合元素。

## 2. 创建集合

```python
nums = {1, 2, 3}
```

空集合：

```python
empty = set()
```

注意：

```python
{}
```

是空字典，不是空集合。

把其他可迭代对象转成集合：

```python
set([1, 1, 2, 3])
# {1, 2, 3}
```

这也是最常见的快速去重方式之一，但会失去原列表的顺序语义。

## 3. 成员判断

```python
"Python" in skills
"Java" not in skills
```

## 4. 添加元素

```python
skills.add("Docker")
```

集合没有 `append()`，添加单个元素用 `add()`。

## 5. 删除元素

### remove()

```python
skills.remove("Git")
```

如果元素不存在，会抛出 `KeyError`。

### discard()

```python
skills.discard("Java")
```

元素不存在也不会报错。

### pop()

```python
item = skills.pop()
```

集合没有可依赖的固定位置，所以不要把 `pop()` 理解成“删除最后一个元素”。

### clear()

```python
skills.clear()
```

清空集合。

## 6. 长度与遍历

```python
len(skills)
```

集合可迭代：

```python
for skill in skills:
    print(skill)
```

但不要依赖遍历顺序。

## 7. frozenset

`frozenset` 是不可变集合：

```python
fixed = frozenset({1, 2, 3})
```

它不能再 `add()` / `remove()`。

初学阶段知道它存在即可。

## 8. 集合真正厉害的地方

Day04 后面的内容都建立在 set 上：

```text
并集 union
交集 intersection
差集 difference
对称差 symmetric difference
子集 issubset
超集 issuperset
不相交 isdisjoint
```

统一复习见 [[Day04 字典与集合]]。

## 9. 和之前去重练习的连接

之前你写过：

```python
result = []
for num in nums:
    if num not in result:
        result.append(num)
```

这种写法可以 **保留原顺序**。

而：

```python
set(nums)
```

更短，但得到的是集合，不再是原来的有序列表结构。

因此“去重”不是永远无脑用 `set()`，要先看题目是否要求保留顺序。

## 自查

1. 为什么空集合不能写成 `{}`？
2. `remove()` 和 `discard()` 有什么区别？
3. 为什么列表不能直接放进集合？
4. 如果题目要求“去重但保持原顺序”，直接 `set(nums)` 合适吗？

关联：[[Python 集合理解]]、[[Python集合合并]]、[[Python 集交集]]、[[Python集合差集]]
