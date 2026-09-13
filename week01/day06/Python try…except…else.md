# Python try...except...else

`else` 可以跟在 `try...except` 后面，表示：

> `try` 中没有发生异常时，执行这里。

```python
try:
    num = int(input("输入数字："))
except ValueError:
    print("输入格式错误")
else:
    print(f"你输入的是 {num}")
```

执行逻辑：

```text
try 成功
→ 跳过 except
→ 执行 else

try 出现异常
→ 执行对应 except
→ 不执行 else
```

## 为什么不把所有代码都塞进 try

推荐只把“可能抛异常”的代码放进 `try`：

```python
try:
    num = int(text)
except ValueError:
    print("转换失败")
else:
    result = num * 2
    print(result)
```

这样异常处理范围更清楚，不会把本来不该捕获的问题一起包进去。

## 和 finally 的关系

完整结构可以是：

```python
try:
    ...
except SomeError:
    ...
else:
    ...
finally:
    ...
```

其中：

```text
except  → 出异常时处理
else    → 没异常时执行
finally → 不管有没有异常，最后都执行
```

当前阶段重点掌握 `try + except`。`else` 和 `finally` 能看懂、知道什么时候用即可。