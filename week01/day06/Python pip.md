## Python 软件包索引（PyPI）简介[](https://www.pythontutorial.net/python-basics/python-pip/#introduction-to-python-package-index-pypi "Anchor for Introduction to Python package index (PyPI)")

Python 有一个丰富的标准库，你可以直接在项目中使用。如果你需要标准库里没有的包，可以在 [Python 包索引](https://pypi.org/)中找到它。

Python 软件包索引（PyPI）是最大的 Python 仓库。它包含了许多由 Python 社区开发和维护的 Python 软件包。

要查找包裹，可以使用搜索框。例如，要搜索处理HTTP请求的包，你只需使用关键字。`requests`

搜索结果会显示许多包裹。要查看每个套餐的详细信息，您可以点击相应链接。

让我们来看看[请求包](https://pypi.org/project/requests/)。

### 包版本[](https://www.pythontutorial.net/python-basics/python-pip/#package-version "Anchor for Package version")

Python 软件包使用语义版本管理，由三部分版本号组成：主要版本、次要版本和补丁：

```css
major.minor.patch
```

补丁编号会增加，用于一些小改动和不改变包运行方式的漏洞修复。

小版本也会因新增功能且兼容向下的版本而增加。

主要版本是针对不向下兼容的变更而增加的。

例如，该软件包的版本是2.24.0（撰写本文时）。它的主版本是2，小版本是24，补丁是零。`requests`

如果你的项目中使用了版本 2.24.0，你可以升级到任何包含主要版本 2 的版本，例如 2.25.1。`requests`

如果你安装了更高版本的软件包，比如3.0.0，你的应用可能无法正常工作。

## 什么是点数[](https://www.pythontutorial.net/python-basics/python-pip/#what-is-pip "Anchor for What is pip")

要下载该软件包，你需要使用模块中描述的命令：

```sql
pip install requests
```

那么，什么是PIP？

pip 是 Python 的软件包安装程序。Pip 允许你安装来自 PyPI 和其他仓库的包。

Python 默认就有。要确认你的电脑是否可用，可以在Windows上打开命令提示符（或Powershell），并输入以下命令：`pip``pip`

```lua
pip --version
```

它会显示类似这样的内容：

```css
pip 25.0.1 from C:pythonLibsite-packagespip (python 3.13)
```

…其中25.0.1是版本，是pip的位置。`C:pythonLibsite-packagespip`

如果你用macOS或Linux，可以启动终端并用 代替：`pip3``pip`

```lua
pip3 --version
```

### 安装一个包[](https://www.pythontutorial.net/python-basics/python-pip/#install-a-package "Anchor for Install a package")

要从PyPI安装包，在Windows上使用以下命令：

```abap
pip install <package_name>
```

然后更改为macOS和Linux版本：`pip``pip3`

```abap
pip3 install <package_name>
```

例如，以下命令用于安装包：`requests`

```sql
pip install requests
```

从现在起，你可以在任何项目中使用这个软件包。例如，你可以创建一个名为 并使用 package 的新项目。`requests``pip-demo``requests`

以下代码使用该包向 发送 HTTP 请求，并显示 HTTP 状态码：`requests``https://pypi.org/`

```python
import requests

response = requests.get('https://pypi.org/')
print(response.status_code)
```

输出：

```yaml
200
```

要安装特定版本的包，请使用以下命令：

```abap
pip install <package_name>==<version>
```

以下命令安装软件包版本 2.20.1：`requests`

```sql
pip install requests==2.20.1
```

### 列表已安装的软件包[](https://www.pythontutorial.net/python-basics/python-pip/#list-installed-packages "Anchor for List installed packages")

要列出所有已安装的软件包，请使用以下命令：`pip`

```cpp
pip list
```

它会像这样返回你电脑上安装的软件包列表：

```css
Package                                  Version
---------------------------------------- -----------
aiohappyeyeballs                         2.6.1
aiohttp                                  3.11.14
aiosignal                                1.3.2
altgraph                                 0.17.4
annotated-types                          0.7.0
...
```

要检查哪些软件包过时，可以使用以下命令：

```cpp
pip list --outdated
```

输出：

```css
Package    Version Latest Type
---------- ------- ------ -----
setuptools 47.1.0  50.3.2 wheel
```

它显示了包名、已安装版本和最新版本。

### 卸载一个包[](https://www.pythontutorial.net/python-basics/python-pip/#uninstall-a-package "Anchor for Uninstall a package")

要卸载一个包，你使用以下命令：`pip uninstall`

```abap
pip uninstall <package_name>
```

它会提示你这样确认：

```abap
Proceed (y/n)?
```

如果你输入 ，pip 会卸载该软件包。否则，它不会这样做。`y`

### 列表包的依赖[](https://www.pythontutorial.net/python-basics/python-pip/#list-dependencies-of-a-package "Anchor for List dependencies of a package")

当你安装一个包并且该包使用其他包时，pip会安装该包及其依赖，以及依赖的依赖，依此类推。

要显示包的依赖关系，您可以使用以下命令：

```abap
pip show <package_name>
```

以下命令显示请求包的依赖关系：

```dart
pip show requests
```

输出：

```yaml
Name: requests
Version: 2.32.3
Summary: Python HTTP for Humans.
Home-page: https://requests.readthedocs.io
Author: Kenneth Reitz
Author-email: me@kennethreitz.org
License: Apache-2.0
Location: C:pythonLibsite-packages
Requires: certifi, charset-normalizer, idna, urllib3
Required-by: huggingface-hub, kubernetes, langchain, langchain-community, langsmith, posthog, requests-oauthlib, requests-toolbelt, transformers
```

该行列出了请求包所使用的包。`Requires`

```powershell
Requires: certifi, charset-normalizer, idna, urllib3
```

## 摘要[](https://www.pythontutorial.net/python-basics/python-pip/#summary "Anchor for Summary")

- Python 套件索引提供由 Python 社区开发和维护的第三方 Python 软件包。
- 使用Python安装程序（pip）来管理第三方Python包。