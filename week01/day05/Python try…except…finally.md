# Python `try...except...finally`

`finally` 表示：**无论前面是否发生异常，这段代码最后都会执行。**

基本结构：

```python
try:
    # 可能出错的代码
except 某种异常:
    # 异常处理
finally:
    # 无论如何都会执行
```

例如：

```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("不能除以 0")
finally:
    print("执行结束")
```

输出：

```text
不能除以 0
执行结束
```

即使没有异常：

```python
try:
    result = 10 / 2
    print(result)
except ZeroDivisionError:
    print("不能除以 0")
finally:
    print("执行结束")
```

`finally` 仍然会执行。

## 什么时候用

典型用途是**清理资源**：

```text
关闭文件
关闭数据库连接
释放锁
清理临时资源
```

例如：

```python
file = None

try:
    file = open("data.txt", "r", encoding="utf-8")
    content = file.read()
except FileNotFoundError:
    print("文件不存在")
finally:
    if file is not None:
        file.close()
```

不过处理文件时，更推荐以后学习的 `with`：

```python
with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()
```

它会自动关闭文件，通常比手写 `finally` 更简洁。

## `try...finally`

如果你不准备处理异常，只想保证清理动作一定执行，也可以：

```python
try:
    ...
finally:
    ...
```

异常仍会继续向外抛出，但 `finally` 会先执行。

## 记忆

```text
try     → 尝试
except  → 出错后怎么处理
finally → 最后无论如何都做
```

当前阶段重点理解执行顺序即可，不需要为了使用 `finally` 而强行使用。