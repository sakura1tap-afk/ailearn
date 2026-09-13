# Python 写文本文件

写文件最常见的方式是 `with open(...)`。

```python
with open("readme.txt", "w", encoding="utf-8") as f:
    f.write("Hello Python")
```

`with` 结束后会自动关闭文件，通常不需要手动 `close()`。

## 常用模式

```text
"w" → 写入。文件不存在会创建；存在会覆盖
"a" → 追加。内容写到文件末尾
"x" → 只创建新文件。文件已存在会报 FileExistsError
```

### 覆盖写入

```python
with open("log.txt", "w", encoding="utf-8") as f:
    f.write("第一行\n")
    f.write("第二行\n")
```

### 追加内容

```python
with open("log.txt", "a", encoding="utf-8") as f:
    f.write("新的一行\n")
```

## write 与 writelines

`write()` 写一个字符串：

```python
f.write("hello\n")
```

`writelines()` 接收多个字符串，但**不会自动添加换行**：

```python
lines = ["Tom\n", "Alice\n", "Bob\n"]

with open("names.txt", "w", encoding="utf-8") as f:
    f.writelines(lines)
```

也可以：

```python
lines = ["Tom", "Alice", "Bob"]

with open("names.txt", "w", encoding="utf-8") as f:
    f.write("\n".join(lines))
```

## 当前重点

看到：

```python
with open(path, mode, encoding="utf-8") as f:
```

要能判断：

```text
path → 写到哪里
mode → 覆盖、追加还是只创建
f    → 当前文件对象
```

文件读写是后面 JSON、配置文件、日志和数据处理的基础。