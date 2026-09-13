## 为什么你需要Python虚拟环境[](https://www.pythontutorial.net/python-basics/python-virtual-environments/#why-do-you-need-python-virtual-environments "Anchor for Why do you need Python virtual environments")

[安装 Python](https://www.pythontutorial.net/getting-started/install-python/) 时，Python 会将所有系统包存储在指定的文件夹中。通常，大多数系统包会位于路径的子文件夹中。要找到该路径，你可以导入模块并显示如下：`sys.prefix``sys`

```python
import sys

print(sys.prefix)
```

在Windows上会显示类似这样的内容：

```python
C:python
```

当你使用 [pip](https://www.pythontutorial.net/python-basics/python-pip/) 安装第三方包时，Python 会将这些包存储在函数指定的另一个文件夹中：`site.getsitepackges()`

```python
import site
print(site.getsitepackages())
```

在Windows上它会返回类似这样的内容：

```python
['C:\python', 'C:\python\Lib\site-packages']
```

如果你有些项目只用标准Python库，那就没问题。不过，当你有些项目使用第三方软件包时，这会成为问题。

假设你有两个项目使用不同版本的库。由于第三方包只能存放一个地方，你不能同时保存不同版本。

一个变通方法是，你可以用命令通过安装/卸载软件包来切换版本。不过，这会很耗时，而且扩展性不佳。`[pip](https://www.pythontutorial.net/python-basics/python-pip/)`

这正是虚拟环境发挥作用的地方。

## 什么是Python虚拟环境[](https://www.pythontutorial.net/python-basics/python-virtual-environments/#what-is-a-python-virtual-environment "Anchor for What is a Python virtual environment")

Python 利用**虚拟环境**为每个项目创建一个**隔离环境**。换句话说，每个项目都会有自己的目录来存储第三方软件包。

如果你有多个项目使用不同版本的包，你可以将它们存储在不同的虚拟环境中。

自3.3版本起，Python将虚拟环境模块（）作为标准库加入。因此，要使用该模块，你应该有 Python 3.3 或更高版本。`venv``venv`

要检查 Python 版本，可以使用以下命令：

```lua
python --version
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-virtual-environments/#summary "Anchor for Summary")

- 虚拟环境为Python项目创建一个隔离环境。
- 使用该模块创建一个新的虚拟环境。`venv`