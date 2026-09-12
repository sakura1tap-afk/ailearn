## Python 包介绍[](https://www.pythontutorial.net/python-basics/python-packages/#introduction-to-python-packages "Anchor for Introduction to Python packages")

假设你需要开发一个大型应用程序，负责从订单到收款的销售流程。

该应用将包含许多[模块](https://www.pythontutorial.net/python-basics/python-module/)。当模块数量增加时，很难把所有模块集中在一个地方。

你也可以把模块分组成有意义的组合。

这正是包发挥作用的地方。

包允许你按层级结构组织模块。

Python 组织包和模块的方式，比如操作系统，结构化了文件夹和文件。

要创建包，你需要创建一个新文件夹，并将相关模块放入该文件夹。

要指示 Python 将包含文件的文件夹视为包，你需要在该文件夹中创建一个文件。`__init__.py`

## 导入软件包[](https://www.pythontutorial.net/python-basics/python-packages/#importing-packages "Anchor for Importing packages")

导入包时，你使用如下语句：`import`

```python
import package.module
```

要访问属于包的模块中的对象，使用点符号：

```python
package.module.function
```

以下展示了如何使用包中的函数， ， 和模块：`order``delivery``billing``sales`

```python
# main.py
import sales.order
import sales.delivery
import sales.billing


sales.order.create_sales_order()
sales.delivery.create_delivery()
sales.billing.create_billing()
```

为了让代码更简洁，你可以用以下语句从模块导入函数：

```python
from <module> import <function>
```

## 来自 <package> import *[](https://www.pythontutorial.net/python-basics/python-packages/#from-package-import "Anchor for from <package> import *")

当你用该语句导入包中的所有对象时：

```python
from <package> import *
```

Python 会查找该文件。`__init__.py`

如果文件存在，它会加载文件中调用的特殊列表中指定的所有模块。`__init__.py``__all__`
从 main.py，你可以访问和模块中定义的函数。但你看不到这个模块，因为它不在列表中。`order``delivery``billing``__all__`

## 子包[](https://www.pythontutorial.net/python-basics/python-packages/#subpackages "Anchor for Subpackages")

包可以包含子包。子包允许你进一步组织模块。

下图显示包含三个子包的包：、、和。每个子包都有对应的模块。`sales``order``delivery``billing`

例如，你可以将所有与订单处理相关的其他模块放入子包中：`order`

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-Subpackages.png)

你学到的所有关于包的内容也适用于子包。

例如，要从子包导入函数，你使用以下语句：`order``import`

```python
# main.py
from sales.order import create_sales_order

create_sales_order()
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-packages/#summary "Anchor for Summary")

- Python 包包含一个或多个模块。Python 使用文件夹和文件结构来管理包和模块。
- 如果你想初始化包级数据，可以使用该文件。`__init__.py`
- 使用变量指定导入包时会自动加载的模块。`__all__`
- 一个包可以包含子包。