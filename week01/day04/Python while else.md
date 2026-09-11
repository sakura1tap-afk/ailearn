# Python while...else

`while...else` 和 `for...else` 的规则基本一致：

> **如果 `while` 是因为条件变成 False 而正常结束，就执行 `else`；如果中途遇到 `break`，就跳过 `else`。**

## 基本结构

```python
while condition:
    if something:
        break
else:
    # while 正常结束时执行
    ...
```

## 例子：查找数字

```python
nums = [3, 5, 7, 9]
target = 8
index = 0

while index < len(nums):
    if nums[index] == target:
        print("found")
        break
    index += 1
else:
    print("not found")
```

因为列表里没有 `8`，循环最终是因为：

```python
index < len(nums)
```

变成 `False` 而结束的，所以会执行 `else`。

如果找到了 `target` 并 `break`，则不会执行 `else`。

## 和普通 while 的区别

普通写法可能需要一个标志变量：

```python
found = False
index = 0

while index < len(nums):
    if nums[index] == target:
        found = True
        break
    index += 1

if not found:
    print("not found")
```

`while...else` 可以在某些“循环查找”场景中减少这个 flag。

## return 呢？

如果 `while` 位于函数里，并且循环中直接执行 `return`，函数已经结束，自然也不会继续执行后面的 `else`。

## 易错点

- `else` 不是每轮循环都执行一次。
- `else` 只在整个 `while` 正常结束后执行一次。
- `break` 会跳过 `else`。
- 使用 `while` 时别忘了更新循环条件相关变量，否则可能死循环。

## 自查

下面会输出什么？

```python
n = 3

while n > 0:
    print(n)
    n -= 1
else:
    print("done")
```

如果在 `n == 2` 时加入 `break`，结果又会怎样？

关联：[[Python while]]、[[Python break]]、[[Python for…else]]、[[00 Day04整理版]]
