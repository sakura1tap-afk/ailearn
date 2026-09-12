# Python `try...except`

程序语法正确，也可能在运行时失败。这种运行期间出现的问题叫 **异常（exception）**。

常见异常：

```text
ValueError        值不符合要求
TypeError         类型不合适
NameError         使用了未定义的名字
KeyError          字典中不存在这个 key
IndexError        下标越界
ZeroDivisionError 除以 0
FileNotFoundError 文件不存在
```

## 基本结构

```python
try:
    # 可能发生异常的代码
except 某种异常:
    # 发生对应异常后怎么处理
```

例如：

```python
try:
    age = int(input("请输入年龄："))
except ValueError:
    print("请输入整数")
```

执行逻辑：

```text
try 正常完成
→ 跳过 except

try 发生 ValueError
→ 立即停止 try 中剩余代码
→ 执行对应 except
```

## 为什么不能什么都捕获

不推荐：

```python
try:
    ...
except:
    print("出错了")
```

因为它会把不同错误全部混在一起，很难定位真正原因。

优先捕获具体异常：

```python
try:
    value = int(text)
except ValueError:
    print("无法转换为整数")
```

## 处理多种异常

```python
try:
    number = int(input("请输入数字："))
    result = 100 / number
except ValueError:
    print("输入必须是整数")
except ZeroDivisionError:
    print("不能输入 0")
```

如果几种异常处理方式相同，也可以写：

```python
except (ValueError, TypeError):
    ...
```

## 获取异常信息

```python
try:
    result = 10 / 0
except ZeroDivisionError as error:
    print(error)
```

`error` 是异常对象，里面保存了错误信息。

## `except Exception`

有时需要在程序边界兜底：

```python
try:
    ...
except Exception as error:
    print(f"程序执行失败：{error}")
```

但不要用它代替所有具体异常处理。开发时过度兜底可能把真正的 bug 藏起来。

## 实际开发中为什么重要

以后做 Python 后端和 AI 应用时，经常有不可完全控制的失败：

```text
用户输入格式错误
读取文件失败
JSON 解析失败
调用模型 API 超时
数据库连接失败
第三方服务返回错误
```

`try...except` 的意义不是“让错误消失”，而是：

> 明确知道某一步可能失败，并规定失败后程序该怎么处理。

## 记忆

```text
try    → 尝试执行可能失败的代码
except → 出现指定异常后的处理方案
```

只包住真正可能失败的部分，不要把整个程序全部塞进一个巨大的 `try`。