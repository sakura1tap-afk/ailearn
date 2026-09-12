# Day04｜字典、集合与循环 else

这一天真正要建立的不是“记住一堆方法名”，而是先弄清楚：**不同容器为什么存在、它们各自在解决什么问题。**

如果只背 `items()`、`intersection()`、`issubset()`，很容易出现“看得懂，自己写时不知道该拿谁出来用”的情况。

## 1. 先分清 list / dict / set

| 类型 | 典型写法 | 最适合干什么 | 常见添加方式 |
| --- | --- | --- | --- |
| 列表 `list` | `[10, 20, 30]` | 保存一串有顺序的数据 | `append()` |
| 字典 `dict` | `{"Tom": 78}` | 保存“键 → 值”的对应关系 | `d[key] = value` |
| 集合 `set` | `{"Python", "Git"}` | 去重、成员判断、集合关系 | `add()` |

最容易混的三个动作：

```python
nums.append(10)          # list
scores["Tom"] = 78      # dict
skills.add("Python")     # set
```

空容器也要分清：

```python
[]      # 空列表
{}      # 空字典
set()   # 空集合
```

---

## 2. 字典 dict 到底在干什么

字典保存的是 **键值对（key-value pairs）**。

```python
scores = {
    "Tom": 78,
    "Alice": 95,
    "Bob": 42
}
```

可以把它理解成一张“名字 → 成绩”的查找表：

```text
Tom    → 78
Alice  → 95
Bob    → 42
```

所以：

```python
scores["Alice"]
```

得到：

```python
95
```

如果变量里已经装着键：

```python
name = "Alice"
scores[name]
```

和 `scores["Alice"]` 是同一件事。

### 读取值

```python
scores["Alice"]
scores.get("Alice")
```

区别：

- `scores["xxx"]`：键不存在会抛出 `KeyError`。
- `scores.get("xxx")`：键不存在默认返回 `None`。
- `scores.get("xxx", -1)`：键不存在时可以返回指定默认值。

### 新增和修改

字典不用 `append()`。

```python
scores["Jerry"] = 66    # 新增
scores["Tom"] = 80      # 修改
```

核心记法：

```text
字典[键] = 值
```

### 判断键是否存在

```python
if "Tom" in scores:
    ...
```

对字典直接使用 `in`，默认检查的是 **key（键）**。

---

## 3. 遍历字典时到底拿到了什么

### 只遍历字典本身

```python
for x in scores:
    print(x)
```

得到的是键：

```text
Tom
Alice
Bob
```

所以：

```python
for score in scores:
```

这里变量虽然叫 `score`，但实际拿到的仍然是名字。**变量名不会改变数据本身是什么。**

### 同时拿到键和值

```python
for name, score in scores.items():
    print(name, score)
```

第一轮相当于：

```text
name = "Tom"
score = 78
```

`items()` 给出的是 `(key, value)`，这里又用到了之前学过的 **解包（unpacking）**。

### 只拿值

```python
for score in scores.values():
    print(score)
```

常见选择：

```text
只要 key       → for key in d
只要 value     → for value in d.values()
key 和 value   → for key, value in d.items()
```

关联：[[Python 词典]]

---

## 4. 字典计数模式

这是非常常见的一类代码：

```python
words = ["python", "java", "python"]
counts = {}

for word in words:
    if word not in counts:
        counts[word] = 1
    else:
        counts[word] += 1
```

思路不是“背代码”，而是：

```text
第一次见到这个单词 → 创建 key，初始值 1
以前见过           → 原来的次数 +1
```

这类结构以后会出现在计数、统计、分组、缓存等很多场景里。

---

## 5. 不要边遍历字典边改变它的大小

这种写法容易报错：

```python
for name, score in scores.items():
    if score < 60:
        del scores[name]
```

因为循环正在依赖字典当前的结构，你同时又在删除元素。

当前阶段更稳妥的思路是构造新结果：

```python
passed = {}

for name, score in scores.items():
    if score >= 60:
        passed[name] = score
```

然后：

```python
return passed
```

写函数结束前顺手问自己一句：

> 我真正构造出的结果变量是谁？`return` 的是不是它？

---

## 6. 字典推导式 dictionary comprehension

普通写法：

```python
passed = {}
for name, score in scores.items():
    if score >= 60:
        passed[name] = score
```

推导式写法：

```python
passed = {
    name: score
    for name, score in scores.items()
    if score >= 60
}
```

当前阶段优先把普通 `for` 写熟，再把它压缩成推导式。

关联：[[Python 词典理解]]

---

## 7. 集合 set 到底在干什么

集合不是“另一种列表”。它最主要的特点是：

- 元素不重复。
- 不依赖下标位置。
- 很适合判断“有没有”。
- 很适合处理“两组东西之间是什么关系”。

例如两个程序员会的技能：

```python
a = {"Python", "Git", "SQL", "Docker"}
b = {"Python", "Git", "Java"}
```

这时候集合比列表更自然，因为我们关心的是：

```text
共同会什么？
一共会什么？
A 会但 B 不会什么？
只有其中一方会什么？
```

关联：[[Python 集合]]

---

## 8. 四个集合运算不要只背名字

### 交集 intersection

“双方都有”：

```python
a & b
a.intersection(b)
```

结果：

```python
{"Python", "Git"}
```

### 并集 union

“双方加起来一共有”：

```python
a | b
a.union(b)
```

### 差集 difference

“A 有，B 没有”：

```python
a - b
```

差集有方向：

```python
a - b != b - a
```

### 对称差 symmetric difference

“只属于其中一方，共同拥有的不要”：

```python
a ^ b
```

可以这样记：

```text
&  共同的
|  合起来
-  我有你没有
^  两边独有
```

关联：[[Python 集交集]] · [[Python集合合并]] · [[Python集合差集]] · [[Python 对称差分]]

---

## 9. 子集、超集、不相交到底是什么意思

假设：

```python
user_permissions = {"read", "write", "delete"}
required = {"read", "write"}
```

用户是否拥有所有必需权限？

可以从两个方向说同一件事：

```python
user_permissions.issuperset(required)
required.issubset(user_permissions)
```

翻成人话：

```text
用户权限是必需权限的超集
必需权限是用户权限的子集
```

如果想判断两个集合完全没有共同元素：

```python
a.isdisjoint(b)
```

关联：[[Python issubset]] · [[Python issuperset]] · [[Python 不相交集]]

---

## 10. for...else 到底在干什么

它不是 `if...else` 的变种。

```python
for item in items:
    if condition:
        break
else:
    print("循环完整跑完，没有被 break 打断")
```

核心规则：

```text
循环正常结束       → 执行 else
break 提前结束     → 不执行 else
```

最适合的场景是“搜索”：

```python
for num in nums:
    if num % 2 == 0:
        print("找到了")
        break
else:
    print("一个偶数都没有")
```

如果函数里找到结果后直接 `return`，函数本身已经结束，也不会再进入后面的 `else`：

```python
def find_even(nums):
    for num in nums:
        if num % 2 == 0:
            return num
    else:
        return None
```

关联：[[Python for…else]]

---

## 11. while...else

逻辑和 `for...else` 一致：

```text
条件自然变成 False → 执行 else
遇到 break          → 跳过 else
```

关联：[[Python while else]]

---

## 12. 今天最值得反复看的几句话

```text
列表：一串数据
字典：key → value
集合：一组不重复元素，以及它们之间的关系
```

```text
list  添加：append()
set   添加：add()
dict  添加：d[key] = value
```

```text
for x in dict              → x 是 key
for x in dict.values()     → x 是 value
for k, v in dict.items()   → 同时拿 key 和 value
```

```text
return 会结束整个函数，不只是结束一轮循环
```

```text
写完函数最后检查：我 return 的是不是我真正算出来的结果？
```

> [!tip]
> 这一章如果觉得“每个方法单看都懂，一做题就不知道为什么要用”，先别继续堆方法。先把 **容器的用途、数据流向、遍历时拿到什么** 搞明白，后面的语法会顺很多。
