# Python 读取文本文件

最常用的基础写法：

```python
with open("readme.txt", "r", encoding="utf-8") as f:
    content = f.read()
```

`with` 结束后会自动关闭文件。

## 三种读取方式

```python
f.read()       # 读取整个文件，返回 str
f.readline()   # 读取一行，返回 str
f.readlines()  # 读取所有行，返回 list[str]
```

## 逐行读取

文件对象本身可以直接迭代：

```python
with open("readme.txt", encoding="utf-8") as f:
    for line in f:
        print(line.strip())
```

这通常比手写 `while + readline()` 更自然。

## `strip()`

文本行常带有换行符：

```text
"hello\n"
```

所以经常看到：

```python
line.strip()
```

用来去掉首尾空白字符。

## 当前重点

```text
read()        → 整个文件 → str
readline()    → 一行     → str
readlines()   → 所有行   → list[str]
for line in f → 逐行遍历
```

文件读写的价值在于让程序开始处理外部数据。后面的 JSON、配置文件、日志都会建立在这里。