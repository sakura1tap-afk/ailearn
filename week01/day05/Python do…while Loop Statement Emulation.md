# Python 中模拟 `do...while`

Python **没有**原生 `do...while` 语法。

`do...while` 的核心特点是：

> 循环体至少执行一次，然后再判断是否继续。

Python 中通常用：

```python
while True:
    # 先执行代码

    if 结束条件:
        break
```

来模拟。

## 示例

```python
while True:
    number = int(input("请输入一个正数："))

    if number > 0:
        break

print("输入正确")
```

无论用户第一次输入什么，循环体都会先执行一次。

## 为什么不用普通 `while`

普通 `while` 会在进入循环前先判断条件：

```python
while condition:
    ...
```

如果一开始 `condition` 就是 `False`，循环一次都不会执行。

而：

```python
while True:
    ...
    if condition:
        break
```

一定会先进入循环，再决定什么时候退出。

## 记忆

```text
Python 没有 do...while
需要“至少执行一次”
→ while True + break
```

这是一个实用的小技巧，理解即可，不需要当成新的循环语法死记。