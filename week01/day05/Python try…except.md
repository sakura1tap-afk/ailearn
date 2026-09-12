# Python `try...except`

异常处理解决的是一个非常实际的问题：**程序运行时出错了，能不能别直接崩掉，而是自己处理。**

## 1. 语法错误和异常不是一回事

语法错误：代码本身写得不合法。

```python
if x > 10
    print(x)
```

这里缺少 `:`，程序甚至不能正常开始执行。

异常（exception）：代码语法没问题，但运行过程中出了问题。

```python
int("abc")
```

这会产生：

```text
ValueError
```

再比如：

```python
10 / 0
```

会产生：

```text
ZeroDivisionError
```

## 2. `try...except` 在干什么

基本结构：

```python
try:
    # 可能出错的代码
except SomeError:
    # 出现指定异常时怎么处理
```

例如：

```python
try:
    age = int(input("请输入年龄："))
except ValueError:
    print("请输入数字")
```

如果输入：

```text
18
```

正常执行。

如果输入：

```text
abc
```

`int("abc")` 会产生 `ValueError`，程序进入 `except ValueError:`，而不是直接崩掉。

## 3. 执行顺序

```text
进入 try
↓
正常执行
├─ 没异常 → except 跳过
└─ 出异常 → try 剩余代码停止 → 去找匹配的 except
```

例如：

```python
try:
    print("A")
    num = int("abc")
    print("B")
except ValueError:
    print("C")
```

输出：

```text
A
C
```

`B` 不会执行，因为异常出现后，`try` 中后面的代码被跳过。

## 4. 尽量捕获具体异常

不推荐一上来就写：

```python
try:
    ...
except:
    print("出错了")
```

因为这样会把很多不同问题混在一起。

更清楚的是：

```python
try:
    previous = float(input("上一期销售额："))
    current = float(input("当前销售额："))
    change = (current - previous) / previous
except ValueError:
    print("请输入数字")
except ZeroDivisionError:
    print("上一期销售额不能为 0")
```

两个异常代表两个完全不同的问题。

## 5. `as e` 是什么

可以把异常对象保存到变量里：

```python
try:
    num = int("abc")
except ValueError as e:
    print(e)
```

`e` 里面包含这次异常的具体信息。

## 6. `Exception` 什么时候用

有时程序边界处确实需要兜底：

```python
try:
    ...
except Exception as e:
    print("发生异常：", e)
```

但学习和业务代码中，**能明确知道异常类型时优先捕获具体异常**。

否则很容易把真正的 bug 也一起吞掉。

## 7. 异常处理不是“让错误消失”

它的真正作用是：

```text
预料某些运行时失败
↓
识别是什么问题
↓
决定程序接下来怎么办
```

例如未来做 API 时：

```text
用户参数错误       → 返回合理错误信息
请求外部模型超时   → 重试或返回超时信息
文件不存在         → 提示文件问题
数据库连接失败     → 记录日志并停止当前请求
```

所以 `try...except` 在后端和 AI 应用开发里会非常常见。

## 当前阶段记住

```text
try    → 放可能失败的操作
except → 指定失败发生后怎么处理
```

并且优先记住几个常见异常：

```text
ValueError
TypeError
KeyError
IndexError
ZeroDivisionError
FileNotFoundError
```