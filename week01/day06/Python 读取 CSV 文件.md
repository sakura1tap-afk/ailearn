## 什么是CSV文件[](https://www.pythontutorial.net/python-basics/python-read-csv-file/#what-is-a-csv-file "Anchor for What is a CSV file")

CSV 代表逗号分隔值。CSV 文件是一种用逗号分隔数值的分隔文本文件。

CSV文件由一行或多行组成。每一行都是数据记录。每个数据记录由一个或多个用逗号分隔的值组成。此外，CSV文件的所有行数值相同。

通常，你会用CSV文件来存储表状的纯文本数据。CSV 文件格式非常流行，许多软件软件如 Microsoft Excel 和 Google 电子表格都支持该格式。

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-Read-CSV-File.png)
## 用 Python 读取 csv 文件[](https://www.pythontutorial.net/python-basics/python-read-csv-file/#reading-a-csv-file-in-python "Anchor for Reading a csv file in Python")

要用 Python 读取 CSV 文件，步骤如下：

首先，导入csv模块：

```python
import csv
```

其次，在读取模式下使用内置的open（）函数打开CSV文件：

```python
f = open('path/to/csv_file')
```

如果CSV包含UTF8字符，你需要像这样指定编码方式：

```pythonw
```

第三，将文件对象（）传递给模块的函数。该函数返回一个csv读者对象：`f``reader()``csv``reader()`

```python
csv_reader = csv.reader(f)
```

是CSV文件中行的[可迭代](https://www.pythontutorial.net/python-basics/python-iterables/)对象。因此，你可以通过循环遍历CSV文件的行：`csv_reader``for`

```python
for line in csv_reader:
    print(line)
```

每一行都是数值[列表](https://www.pythontutorial.net/python-basics/python-list/)。访问每个值时，使用方括号表示。第一个值的指标为0。第二个值的索引为1，依此类推。`[]`

例如，以下函数访问某一行的第一个值：

```python
line[0]
```

最后，一旦无法访问文件，务必通过调用文件对象的方法关闭：`close()`

```python
f.close()    
```

用语句会更方便，这样你就不用显式调用方法。`with``close()`

以下说明了读取CSV文件的所有步骤：

```python
import csv

with open('path/to/csv_file', 'r') as f:
    csv_reader = csv.reader(f)
    for line in csv_reader:
        # process each line
        print(line)
```

d## 使用 DictReader 类读取 CSV 文件[](https://www.pythontutorial.net/python-basics/python-read-csv-file/#reading-a-csv-file-using-the-dictreader-class "Anchor for Reading a CSV file using the DictReader class")

使用该函数时，你可以使用括号符号访问CSV文件的数值，如、、等等。然而，使用该函数有两个主要局限性：`csv.reader()``line[0]``line[1]``csv.reader()`

- 首先，访问CSV文件中数值的方法并不那么直观。例如，“隐含的”国家名称“是个国家名称。如果你能访问国家名称，比如 。`line[0]``line['country_name']`
- 其次，当CSV文件列的顺序发生变化或新增列时，你需要修改代码以获得正确的数据。

这就是职业发挥作用的地方。DictReader 类也来自该模块。`DictReader``csv`

这个类允许你创建像普通CSV阅读器那样的对象。但它将每行的信息映射到字[典](https://www.pythontutorial.net/python-basics/python-dictionary/)（），其键由第一行的值指定。`DictReader``dict`

通过使用类，你可以访问文件中的值，如 、 、 和 行。`DictReader``country.csv``line['name']``line['area']``line['country_code2']``['country_code3']`

以下示例使用了读取文件的类：`DictReader``country.csv`

```python
import csv

with open('country.csv', encoding="utf8") as f:
    csv_reader = csv.DictReader(f)
    # skip the header
    next(csv_reader)
    # show the data
    for line in csv_reader:
        print(f"The area of {line['name']} is {line['area']} km2")
```

输出：

```python
The area of Afghanistan is 652090.00 km2
The area of Albania is 28748.00 km2
The area of Algeria is 2381741.00 km2        
...
```

如果你想拥有与第一行不同的字段名称，可以通过向构造函数传递字段名称列表来显式指定它们：`DictReader()`

```python
import csv

fieldnames = ['country_name', 'area', 'code2', 'code3']

with open('country.csv', encoding="utf8") as f:
    csv_reader = csv.DictReader(f, fieldnames)
    next(csv_reader)
    for line in csv_reader:
        print(f"The area of {line['country_name']} is {line['area']} km2")
```

在这个例子中，我们不是用第一行的值作为字段名，而是显式地将字段名称列表传递给构造子。`DictReader`

## 摘要[](https://www.pythontutorial.net/python-basics/python-read-csv-file/#summary "Anchor for Summary")

- 使用函数或类从CSV文件读取数据。`csv.reader()``csv.DictReader`