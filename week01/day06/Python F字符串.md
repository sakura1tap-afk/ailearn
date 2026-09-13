# Python f-string

f-string（格式化字符串）用于把变量或表达式直接嵌入字符串，是 Python 中最常用的字符串格式化方式之一。

## 基本写法

在字符串前加 `f`，把变量或表达式放进 `{}`：

```python
name = "Tom"
age = 18

text = f"My name is {name}, age is {age}."
print(text)
```

也可以直接写表达式：

```python
x = 10
y = 20

print(f"sum = {x + y}")
```

核心记法：

```text
f"...{表达式}..."
```

## 常用数字格式

保留小数：

```python
price = 9.98567
print(f"{price:.2f}")   # 9.99
```

百分比：

```python
rate = 0.1259
print(f"{rate:.2%}")   # 12.59%
```

千位分隔：

```python
num = 1000000
print(f"{num:,}")      # 1,000,000
```

补零：

```python
num = 42
print(f"{num:06d}")    # 000042
```

## 显示花括号

如果字符串本身需要 `{` 或 `}`，写双花括号：

```python
print(f"{{hello}}")
# {hello}
```

## 什么时候用

以后打印日志、拼接提示词、生成路径、构造输出文本时都会大量使用：

```python
user = "Alice"
score = 95
print(f"{user} 的成绩是 {score}")
```

当前阶段不用背复杂格式规则，先熟练：

```text
{name}
{x + y}
{number:.2f}
{rate:.2%}
```
