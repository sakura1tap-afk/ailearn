# Python 写入 CSV 文件

CSV 适合保存表格型数据。Python 标准库提供 `csv` 模块。

## 写一行

```python
import csv

header = ["name", "age"]
row = ["Tom", 18]

with open("users.csv", "w", encoding="utf-8", newline="") as f:
    writer = csv.writer(f)
    writer.writerow(header)
    writer.writerow(row)
```

关键点：

```text
"w"           → 写入模式，会覆盖旧内容
encoding       → 推荐 utf-8
newline=""     → 写 CSV 时推荐加上，Windows 下可避免多余空行
writerow()     → 写一行
writerows()    → 写多行
```

## 写多行

```python
rows = [
    ["Tom", 18],
    ["Alice", 20],
]

with open("users.csv", "w", encoding="utf-8", newline="") as f:
    writer = csv.writer(f)
    writer.writerow(["name", "age"])
    writer.writerows(rows)
```

## 字典数据用 DictWriter

如果程序里的数据本来就是字典，`DictWriter` 更直观：

```python
import csv

rows = [
    {"name": "Tom", "age": 18},
    {"name": "Alice", "age": 20},
]

with open("users.csv", "w", encoding="utf-8", newline="") as f:
    writer = csv.DictWriter(f, fieldnames=["name", "age"])
    writer.writeheader()
    writer.writerows(rows)
```

## 怎么选

```text
数据是列表 / 元组 → csv.writer
数据是字典         → csv.DictWriter
```

实际项目里 CSV 常用于导入导出、简单报表和数据交换。当前阶段会读、会写即可，不需要背 `csv` 模块所有参数。