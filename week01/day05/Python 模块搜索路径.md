# Python 模块搜索路径

当你写：

```python
import module
```

Python 必须先找到对应的模块文件。

它会按照自己的搜索路径查找，这些路径保存在：

```python
sys.path
```

可以查看：

```python
import sys

for path in sys.path:
    print(path)
```

## 可以先这样理解

Python 通常会从这些位置寻找模块：

```text
当前程序相关目录
Python 标准库目录
当前虚拟环境/解释器的 site-packages
PYTHONPATH 中额外指定的目录
```

所以出现：

```text
ModuleNotFoundError
```

通常意味着：

> Python 沿着 `sys.path` 找了一圈，没有找到你要导入的模块。

## 常见排查方式

先确认：

```text
1. 模块/包是否真的存在
2. 文件名有没有写错
3. 当前使用的是不是正确的 Python 解释器或虚拟环境
4. 第三方包是否已经安装
5. 项目目录结构和 import 路径是否合理
```

例如第三方包没装：

```bash
pip install requests
```

装错虚拟环境，也可能出现“明明装了但 import 不到”。

## 不要随便修改 `sys.path`

虽然可以：

```python
import sys
sys.path.append("某个目录")
```

但在正常项目里，这通常不应该成为主要解决方案。

更好的做法一般是：

```text
整理正确的项目包结构
使用正确的虚拟环境
正确安装项目或第三方依赖
```

## 记忆

```text
import 找不到模块
→ 先想到 sys.path / 环境 / 项目结构
```

当前阶段知道 Python 不是“全硬盘乱找文件”，而是沿固定搜索路径查找，就已经足够。