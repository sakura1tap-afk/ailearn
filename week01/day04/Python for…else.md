# Python for...else

`for...else` 是 Python 里比较特别的语法。

核心规则只有一句：

> **只要 `for` 循环没有被 `break` 提前打断，循环结束后就会执行 `else`。**

## 基本结构

```python
for item in iterable:
    if condition:
        break
else:
    # 循环没有 break 时执行
    ...
```

## 例子：查找名字

```python
people = [
    {"name": "John", "age": 25},
    {"name": "Jane", "age": 22},
    {"name": "Peter", "age": 30},
]

name = "Maria"

for person in people:
    if person["name"] == name:
        print(person)
        break
else:
    print(f"{name} not found!")
```

这里如果找到人，会执行 `break`，所以 `else` 不执行。

如果整个列表都找完了仍然没找到，循环正常结束，于是进入 `else`。

## 和 flag 写法对比

不用 `for...else` 时，经常要写：

```python
found = False

for person in people:
    if person["name"] == name:
        found = True
        break

if not found:
    print("not found")
```

`for...else` 可以省掉这个专门记录“找到没有”的标志变量。

## 空列表会怎样？

```python
items = []

for item in items:
    print(item)
else:
    print("done")
```

因为循环没有遇到 `break`，所以仍然会执行 `else`。

## continue 会阻止 else 吗？

不会。

`continue` 只是跳过当前这一轮，不会结束整个循环。

真正会让 `for...else` 的 `else` 不执行的是 `break`。

## 最适合的使用场景

“循环查找某个东西”：

```text
找到 → break
全部找完都没找到 → else
```

## 易错点

- `else` 属于 `for`，不是属于里面的 `if`。
- 不是“循环至少执行一次才有 else”，空列表也会进入 else。
- `continue` 不会跳过最终的 else。

## 自查

下面代码会不会打印 `not found`？为什么？

```python
nums = [1, 3, 5]

for num in nums:
    if num == 2:
        break
else:
    print("not found")
```

关联：[[Python break]]、[[Python while else]]、[[00 Day04整理版]]
