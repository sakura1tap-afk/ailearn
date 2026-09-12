# Python 中模拟 `do...while`

Python **没有真正的 `do...while` 语法**。

这个知识点真正想表达的只有一件事：

> 有些循环需要“先执行一次，再判断要不要继续”。

## 1. 普通 `while` 是先判断

```python
while condition:
    ...
```

执行顺序：

```text
先判断 condition
↓
True  → 执行循环体
False → 一次都不执行
```

所以普通 `while` 可能一次都不运行。

## 2. `do...while` 的思路是先执行

很多其他语言里会有类似：

```text
do:
    执行代码
while 条件
```

意思是：

```text
先执行一次
↓
再判断
↓
决定要不要继续
```

## 3. Python 通常用 `while True + break` 模拟

```python
while True:
    user_input = input("输入 q 退出：")

    if user_input == "q":
        break
```

为什么它一定至少执行一次？

因为：

```python
while True:
```

第一次一定会进入循环。

退出条件放在循环内部：

```python
if condition:
    break
```

## 4. 典型使用场景

例如菜单程序：

```python
while True:
    print("1. 查询")
    print("2. 添加")
    print("q. 退出")

    choice = input("请选择：")

    if choice == "q":
        break
```

菜单必须先展示一次，然后用户决定是否继续，这种场景就很适合。

再比如猜数字：

```python
while True:
    guess = int(input("请输入数字："))

    if guess == 7:
        print("猜对了")
        break

    print("再试一次")
```

## 5. 不要把它当成新的循环语法背

Python 里并没有：

```python
do ... while
```

当前阶段只要知道：

```text
需要至少执行一次循环体
→ while True
→ 在循环内部判断
→ 满足退出条件时 break
```

这本质上还是你已经学过的 `while` 和 `break`。