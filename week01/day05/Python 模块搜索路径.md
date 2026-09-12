## Python 模块搜索路径简介[](https://www.pythontutorial.net/python-basics/python-module-search-path/#introduction-to-python-module-search-path "Anchor for Introduction to Python module search path")

当你在程序中导入[模块](https://www.pythontutorial.net/python-basics/python-module/)时：

```python
import module
```

Python 将从以下来源搜索该文件：`module.py`

- 程序运行的当前文件夹。
- 如果你之前设置了 [PYTHONPATH](https://docs.python.org/3/using/cmdline.html#envvar-PYTHONPATH) 环境变量，那是列表里指定的文件夹。
- 这是一份安装相关文件夹列表，这些文件夹是你安装Python时配置的。

Python 将生成的搜索路径存储在来自模块的变量中。`sys.path``sys`

以下程序展示了当前的模块搜索路径：

```python
import sys

for path in sys.path:
    print(path)
```

这是Windows上的示例输出：

```bash
C:pythonpython313.zip
C:pythonDLLs
C:pythonLib
C:python
C:pythonLibsite-packages
```

为了确保Python总能找到，你需要：`module.py`

- 把它放进程序将要执行的文件夹里。`module.py`
- 在环境变量中包含包含 的文件夹。或者你可以把它放在变量里的某个文件夹里。`module.py``PYTHONPATH``module.py``PYTHONPATH`
- 把 放在安装相关的文件夹里。`module.py`
## 摘要[#](https://www.pythontutorial.net/python-basics/python-module-search-path/#summary "Anchor for Summary")

- 导入模块时，Python 会从变量指定的文件夹中搜索模块文件。`sys.path`
- Python 允许你通过修改、添加和删除变量中的元素来修改模块搜索路径。`sys.path`