## 编写CSV文件的步骤[](https://www.pythontutorial.net/python-basics/python-write-csv-file/#steps-for-writing-a-csv-file "Anchor for Steps for writing a CSV file")

要将数据写入CSV文件，请遵循以下步骤：

- 首先，使用函数打开CSV文件进行写入（模式）。`w``open()`
- 其次，通过调用模块函数创建CSV编写对象。`writer()``csv`
- 第三，通过调用 CSV 编写对象的 or 方法，将数据写入 CSV 文件。`writerow()``writerows()`
- 最后，写入数据后关闭文件。
- 以下代码展示了上述步骤：

```python
import csv

# open the file in the write mode
f = open('path/to/csv_file', 'w')

# create the csv writer
writer = csv.writer(f)

# write a row to the csv file
writer.writerow(row)

# close the file
f.close()
```

如果你用语句，这样就不用调用方法来显式关闭文件，会更短：`with``close()`

```python
import csv

# open the file in the write mode
with open('path/to/csv_file', 'w') as f:
    # create the csv writer
    writer = csv.writer(f)

    # write a row to the csv file
    writer.writerow(row)
```

如果你处理的是非ASCII字符，你需要在函数中指定字符编码。`open()`

以下演示了如何将 UTF-8 字符写入 CSV 文件：

```python
import csv

# open the file in the write mode
with open('path/to/csv_file', 'w', encoding='UTF8') as f:
    # create the csv writer
    writer = csv.writer(f)

    # write a row to the csv file
    writer.writerow(row)
```

## 写入CSV文件示例[#](https://www.pythontutorial.net/python-basics/python-write-csv-file/#writing-to-csv-files-example "Anchor for Writing to CSV files example")

以下示例展示了如何将数据写入CSV文件：

```python
import csv  

header = ['name', 'area', 'country_code2', 'country_code3']
data = ['Afghanistan', 652090, 'AF', 'AFG']

with open('countries.csv', 'w', encoding='UTF8') as f:
    writer = csv.writer(f)

    # write the header
    writer.writerow(header)

    # write the data
    writer.writerow(data)
```

如果你打开 ，你会发现文件内容在两行之后多了一行空行：`countries.csv`

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-Write-CSV-blank-line.png)

要去除空行，你将关键字参数传递给函数，步骤如下：`newline=''``open()`

```python
import csv

header = ['name', 'area', 'country_code2', 'country_code3']
data = ['Afghanistan', 652090, 'AF', 'AFG']


with open('countries.csv', 'w', encoding='UTF8', newline='') as f:
    writer = csv.writer(f)

    # write the header
    writer.writerow(header)

    # write the data
    writer.writerow(data)
```

输出：

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-Write-CSV-remove-blank-lines.png)
## 写入多行到CSV文件[](https://www.pythontutorial.net/python-basics/python-write-csv-file/#writing-multiple-rows-to-csv-files "Anchor for Writing multiple rows to CSV files")

要同时写多行给CSV文件，可以使用CSV写入对象的方法。`writerows()`

以下方法使用该方法在文件中写入多行：`writerows()``countries.csv`

```python
import csv

header = ['name', 'area', 'country_code2', 'country_code3']
data = [
    ['Albania', 28748, 'AL', 'ALB'],
    ['Algeria', 2381741, 'DZ', 'DZA'],
    ['American Samoa', 199, 'AS', 'ASM'],
    ['Andorra', 468, 'AD', 'AND'],
    ['Angola', 1246700, 'AO', 'AGO']
]

with open('countries.csv', 'w', encoding='UTF8', newline='') as f:
    writer = csv.writer(f)

    # write the header
    writer.writerow(header)

    # write multiple rows
    writer.writerows(data)
```
## 使用 DictWriter 类写入 CSV 文件[](https://www.pythontutorial.net/python-basics/python-write-csv-file/#writing-to-csv-files-using-the-dictwriter-class "Anchor for Writing to CSV files using the DictWriter class")

如果CSV文件的每一行都是字典，你可以用模块的类把字典写入CSV文件。`DictWriter``csv`

示例展示了如何使用 DictWriter 类将数据写入 CSV 文件：

```python
import csv

# csv header
fieldnames = ['name', 'area', 'country_code2', 'country_code3']

# csv data
rows = [
    {'name': 'Albania',
    'area': 28748,
    'country_code2': 'AL',
    'country_code3': 'ALB'},
    {'name': 'Algeria',
    'area': 2381741,
    'country_code2': 'DZ',
    'country_code3': 'DZA'},
    {'name': 'American Samoa',
    'area': 199,
    'country_code2': 'AS',
    'country_code3': 'ASM'}
]

with open('countries.csv', 'w', encoding='UTF8', newline='') as f:
    writer = csv.DictWriter(f, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerows(rows)
```

它是如何运作的。

- 首先，定义包含CSV文件字段名称和数据行的变量。
- 接着，通过调用函数打开CSV文件进行写入。`open()`
- 然后，通过传递文件对象（）和参数来创建一个新的类实例。`DictWriter``f``fieldnames`
- 之后，通过调用方法写入CSV文件的头部。`writeheader()`
- 最后，用该方法将数据写入CSV文件。`writerows()`

## 摘要[](https://www.pythontutorial.net/python-basics/python-write-csv-file/#summary "Anchor for Summary")

- 使用CSV Writer或该类将数据写入CSV文件。`DictWriter`