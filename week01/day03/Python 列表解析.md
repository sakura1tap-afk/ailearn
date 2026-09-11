# Python 列表推导式（List Comprehension）

列表推导式用于根据一个可迭代对象快速生成新列表。

## 基本结构

```python
[结果表达式 for 元素 in 可迭代对象]
```

例如：

```python
nums = [1, 2, 3, 4]
squares = [num ** 2 for num in nums]

print(squares)
# [1, 4, 9, 16]
```

它等价于：

```python
squares = []
for num in nums:
    squares.append(num ** 2)
```

## 带条件筛选

```python
[结果表达式 for 元素 in 可迭代对象 if 条件]
```

例如筛选偶数并平方：

```python
nums = [1, 2, 3, 4, 5, 6]
even_squares = [num ** 2 for num in nums if num % 2 == 0]

print(even_squares)
# [4, 16, 36]
```

## 容易写错的地方

错误：

```python
new_nums[num ** 2 for num in nums]
```

这里 Python 会把 `new_nums[...]` 当成下标访问，而且内部语法也不成立。

正确：

```python
new_nums = [num ** 2 for num in nums]
```

如果函数只需要返回生成的列表，可以直接：

```python
def even_square(nums):
    return [num ** 2 for num in nums if num % 2 == 0]
```

## 什么时候不用列表推导式

如果逻辑需要很多层判断、多个副作用或复杂异常处理，普通 `for` 循环通常更清楚。

初学阶段建议：
1. 先能用 `for + if + append` 写出来。
2. 再判断能不能安全地改成列表推导式。

## 自查

不运行代码，试着解释：

```python
[x * 2 for x in range(10) if x % 3 == 0]
```

它遍历谁？筛选条件是什么？最终放进列表的值是什么？

关联：[[Day03 列表与迭代]]、[[Python中筛选列表元素]]、[[Python map（） 函数转换列表元素]]
