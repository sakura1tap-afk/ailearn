## Python 词典理解导论[](https://www.pythontutorial.net/python-basics/python-dictionary-comprehension/#introduction-to-python-dictionary-comprehension "Anchor for Introduction to Python dictionary comprehension")

词典理解允许你在[词典](https://www.pythontutorial.net/python-basics/python-dictionary/)上运行[`for`循环](https://www.pythontutorial.net/python-basics/python-for-range/)，对每个项目做一些操作，比如变换或过滤，然后返回一个新的词典。

与循环不同，词典理解在正确使用时能提供更具表现力和简洁的句法。`for`

以下是词典理解的一般语法：

```css
{key:value for (key,value) in dict.items() if condition}
```

该词典理解表达式返回一个新词典，其项由表达式`key: value`

## Python 词典理解示例[](https://www.pythontutorial.net/python-basics/python-dictionary-comprehension/#python-dictionary-comprehension-examples "Anchor for Python dictionary comprehension examples")

我们将探讨如何使用词典理解来转换和筛选词典中的项。

### 利用 Python 词典理解来转换词典[](https://www.pythontutorial.net/python-basics/python-dictionary-comprehension/#using-python-dictionary-comprehension-to-transform-a-dictionary "Anchor for Using Python dictionary comprehension to transform a dictionary")

假设你有以下词典，其条目分别是股票代码和价格：

```python
stocks = {
    'AAPL': 121,
    'AMZN': 3380,
    'MSFT': 219,
    'BIIB': 280,
    'QDEL': 266,
    'LVGO': 144
}
```

为了将每只股票的价格提高2%，你可以设计一个类似这样的for循环：

```python
stocks = {
    'AAPL': 121,
    'AMZN': 3380,
    'MSFT': 219,
    'BIIB': 280,
    'QDEL': 266,
    'LVGO': 144
}

new_stocks = {}
for symbol, price in stocks.items():
    new_stocks[symbol] = price*1.02

print(new_stocks)
```
它是如何运作的。

- 首先，循环查看词典中的各个项`stocks`
- 其次，将价格提高2%，并将该物品添加到新的词典中（）。`new_stocks`
以下示例展示了如何使用词典理解来实现相同的结果：

```python
stocks = {
    'AAPL': 121,
    'AMZN': 3380,
    'MSFT': 219,
    'BIIB': 280,
    'QDEL': 266,
    'LVGO': 144
}

new_stocks = {symbol: price * 1.02 for (symbol, price) in stocks.items()}

print(new_stocks)
```
### 使用 Python 字典理解来过滤词典[](https://www.pythontutorial.net/python-basics/python-dictionary-comprehension/#using-python-dictionary-comprehension-to-filter-a-dictionary "Anchor for Using Python dictionary comprehension to filter a dictionary")

要选择价格大于200的股票，可以使用以下循环：`for`

```python
stocks = {
    'AAPL': 121,
    'AMZN': 3380,
    'MSFT': 219,
    'BIIB': 280,
    'QDEL': 266,
    'LVGO': 144
}

selected_stocks = {}
for symbol, price in stocks.items():
    if price > 200:
        selected_stocks[symbol] = price

print(selected_stocks)
```
它是如何运作的。

- 首先，反复修改词典中的某个项。`stocks`
- 如果价格大于，则将该项加入字典。`selected_stocks``200`
- 以下示例使用带有if子句的字典理解以得到相同结果：

```python
stocks = {
    'AAPL': 121,
    'AMZN': 3380,
    'MSFT': 219,
    'BIIB': 280,
    'QDEL': 266,
    'LVGO': 144
}

selected_stocks = {s: p for (s, p) in stocks.items() if p > 200}

print(selected_stocks)
```
## 摘要[](https://www.pythontutorial.net/python-basics/python-dictionary-comprehension/#summary "Anchor for Summary")

- 词典理解是对词典中的词项进行迭代，并通过转换或筛选每个词条来创建新的词典。