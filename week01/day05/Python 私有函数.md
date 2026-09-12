**总结**：在本教程中，你将学习如何使用变量在模块中定义 Python 私有函数。`__all__`

假设你有一个称为 的[模](https://www.pythontutorial.net/python-basics/python-module/)，包含两个[函数](https://www.pythontutorial.net/python-basics/python-functions/) 和 。`mail.py``send()``attach_file()`

```python
def send(email, message):
    print(f'Sending "{message}" to {email}')

def attach_file(filename):
    print(f'Attach {filename} to the message')
   
```

你只想把函数暴露给其他模块，而不是函数本身。换句话说，你希望函数是私有的，不能从邮件模块外部访问。`send()``attach_file()``attach_file()`

注意，为了简化，我们只打印部分文本。

如果其他模块使用这样的语句：`import *`

```python
from mail import *
```

你可以在函数名前加上下划线（）来实现私密。例如：`_`

```python
def send(email, message):
    print(f'Sending "{message}" to {email}')

def _attach_file(filename):
    print(f'Attach {filename} to the message')
```
从文件中，你可以使用该模块，只看到函数：`mail.py``import * from mail``send()`

```python
from mail import *


send('test@example.com','Hello')
```

换句话说，你无法从模块中访问该函数。如果你尝试调用该函数，会收到错误。`_attach_file()``main``_attach_file()`

另一种让函数私有化的方法是使用变量。这样，你不需要在函数名前加上下划线（_）来实现私有。`attach_file()``__all__`

以下方法是利用模块中的变量使函数为公函数，使函数为私有：`__all__``mail``send()``attach_file()`

```python
# mail.py

__all__ = ['send']

def send(email, message):
    print(f'Sending "{message}" to {email}')

def attach_file(filename):
    print(f'Attach {filename} to the message')
   
```

从模块中，你也无法像之前那样访问该函数：`main.py``attach_file()`

## 摘要[](https://www.pythontutorial.net/python-basics/python-private-functions/#summary "Anchor for Summary")

要在 Python 中将函数设为私有：

- 首先，创建一个包含该文件的包`__init__.py`
- 其次，不要在变量中指定函数。`__all__`
- 第三，将模块中的所有符号导入包文件，并仅通过变量暴露公函数。`__init__.py``__all__`