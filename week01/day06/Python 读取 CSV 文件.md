# Python 读取 CSV 文件

CSV（Comma-Separated Values，逗号分隔值）常用来保存表格数据。

Python 标准库提供 `csv` 模块。

## 使用 csv.reader

```python
import csv

with open("users.csv", "r", encoding="utf-8", newline="") as f:
    reader = csv.reader(f)

    for row in reader:
        print(row)
```

`row` 是一个列表：

```text
["Tom", "18"]
```

所以可以：

```python
row[0]
row[1]
```

## 使用 DictReader

如果第一行是表头，`DictReader` 通常更直观。

CSV：

```text
name,age
Tom,18
Alice,20
```

代码：

```python
import csv

with open("users.csv", "r", encoding="utf-8", newline="") as f:
    reader = csv.DictReader(f)

    for row in reader:
        print(row["name"], row["age"])
```

每一行会变成类似：

```python
{"name": "Tom", "age": "18"}
```

注意：CSV 读出来的内容默认都是**字符串**。

如果需要整数，要自己转换：

```python
age = int(row["age"])
```

## 怎么选

```text
只按列位置读取 → csv.reader
希望按字段名读取 → csv.DictReader
```

一般有表头的数据，`DictReader` 可读性更好。

## 一个容易踩的坑

`csv.DictReader` 默认会把第一行当字段名，因此通常**不需要再 `next(reader)` 跳过表头**。

否则可能会把第一条真实数据跳掉。

当前阶段重点是会把 CSV 和你已经学过的 `list / dict / for` 联系起来。