# Python pip 与 PyPI

`pip` 是 Python 的第三方包管理工具，`PyPI` 是最主要的 Python 第三方包仓库。

可以简单理解成：

```text
PyPI → 放包的仓库
pip  → 安装 / 卸载 / 查看这些包的工具
```

## 常用命令

Windows 下更推荐：

```powershell
python -m pip --version
python -m pip install requests
python -m pip uninstall requests
python -m pip list
python -m pip show requests
```

安装指定版本：

```powershell
python -m pip install requests==2.32.3
```

升级包：

```powershell
python -m pip install --upgrade requests
```

## 项目依赖

查看当前环境的依赖：

```powershell
python -m pip freeze
```

保存到文件：

```powershell
python -m pip freeze > requirements.txt
```

其他人可以通过：

```powershell
python -m pip install -r requirements.txt
```

恢复依赖。

## 为什么推荐 `python -m pip`

直接写：

```powershell
pip install xxx
```

有时会调用到另一套 Python 对应的 `pip`。

而：

```powershell
python -m pip install xxx
```

明确表示：**使用当前这个 Python 解释器对应的 pip**。

在虚拟环境中尤其重要。

## 当前阶段最需要记住

```text
安装包       python -m pip install 包名
卸载包       python -m pip uninstall 包名
查看已安装   python -m pip list
查看详情     python -m pip show 包名
导出依赖     python -m pip freeze > requirements.txt
安装依赖     python -m pip install -r requirements.txt
```

以后做 FastAPI、LLM、RAG 项目时，第三方库基本都通过 pip 安装。