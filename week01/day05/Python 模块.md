
## Python 模块简介[](https://www.pythontutorial.net/python-basics/python-module/#introduction-to-python-modules "Anchor for Introduction to Python modules")

模块是一种具有特定功能的软件。Python 模块是一个包含 Python 代码的文件。

例如，在构建购物车应用时，你可以有一个模块用于计算价格，另一个模块用于管理购物车中的商品。每个模块都是独立的 Python 源代码文件。

模块的名称由文件名指定，但不含扩展名。例如，如果你有一个名为 的文件，模块名是 。`.py``pricing.py``pricing`

## 编写 Python 模块[](https://www.pythontutorial.net/python-basics/python-module/#writing-python-modules "Anchor for Writing Python modules")

首先，创建一个名为的新文件，并添加以下代码：`pricing.py`

```python
# pricing.py

def get_net_price(price, tax_rate, discount=0):
    discounted_price = price * (1 - discount) 
    net_price = discounted_price * (1 + tax_rate) 
    return net_price


def get_tax(price, tax_rate=0):
    return price * tax_rate
```

定价模块包含两个功能，分别计算销售价格、税率和折扣的净价和税收。
## 导入模块对象[](https://www.pythontutorial.net/python-basics/python-module/#importing-module-objects "Anchor for Importing module objects")

要使用模块中定义的对象，可以使用语句。`import`

该声明有几种形式，我们将在接下来的章节中讨论。`import`

### 进口<module_name>[](https://www.pythontutorial.net/python-basics/python-module/#import-module_name "Anchor for import <module_name>")

要使用模块中定义的对象，你需要用以下语句导入该模块：`import`

```python
import module_name
```

例如，要使用文件中的模块，你需要使用以下语句：`pricing``main.py`

```python
import pricing
```
导入模块时，Python 会执行对应文件中的所有代码。在这个例子中，Python 从文件中执行代码。此外，Python 会在当前模块中添加模块名称。`pricing.py`

这个模块名称允许你访问当前模块中导入模块中的函数、变量等。例如，你可以调用导入模块中定义的[函数](https://www.pythontutorial.net/python-basics/python-functions/)，使用以下语法：

```python
module_name.function_name()
```

以下展示了如何在文件中使用模块中定义的函数：`get_net_price()``pricing``main.py`

```python
# main.py
import pricing


net_price = pricing.get_net_price(
    price=100,
    tax_rate=0.01
)

print(net_price)
```

输出：

```python
101.0
```
以下示例将函数从模块重新命名为函数：`get_net_price()``pricing``calculate_net_price()`

```python
from pricing import get_net_price as calculate_net_price

net_price = calculate_net_price(
    price=100,
    tax_rate=0.1,
    discount=0.05
)
```
如果你想在模块中引用对象而不在模块名称前缀，可以用以下语法显式导入它们：

```python
from module_name import fn1, fn2
```

现在，你可以使用导入的函数，而无需指定模块名，就像这样：

```python
fn1()
fn2()
```

### 从<module_name>导入* ：导入模块中的所有对象[](https://www.pythontutorial.net/python-basics/python-module/#from-module_name-import-import-all-objects-from-a-module "Anchor for from <module_name> import * : import all objects from a module")

要导入模块中的每个对象，可以使用以下语法：

```python
from module_name import *
```

该语句将所有公共标识符，包括[变量](https://www.pythontutorial.net/python-basics/python-variables/)、[常量](https://www.pythontutorial.net/python-basics/python-constants/)、[函数](https://www.pythontutorial.net/python-basics/python-functions/)、[类](https://www.pythontutorial.net/python-oop/python-class/)等，导入到程序中。`import`

但这并不是好习惯，因为如果导入的模块有相同的对象，第二个模块的对象会覆盖第一个模块。这个项目可能不会像你预期的那样有效。

## 摘要[](https://www.pythontutorial.net/python-basics/python-module/#summary "Anchor for Summary")

- 模块是一个带有扩展名的 Python 源代码文件。模块名称是 Python 文件名，但没有扩展名。`.py`
- 要使用模块中的对象，你可以通过 语句导入它们。`import`