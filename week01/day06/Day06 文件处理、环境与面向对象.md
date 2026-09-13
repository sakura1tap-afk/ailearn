# Day06｜文件处理、环境与面向对象

Day06 的内容比较散，但其实可以压成四条主线：

```text
字符串表达
→ f-string / 转义字符 / raw string

文件与目录
→ 读写文本 / CSV / pathlib / os

项目环境
→ pip / PyPI / venv

面向对象
→ class / object / __init__ / self / inheritance
```

今天很多内容属于“认识工具”，不是都需要立刻背下来。

## 1. 字符串表达

### f-string

```python
name = "Tom"
age = 18

print(f"{name} is {age} years old")
```

重点：

```text
f"...{表达式}..."
```

关联：[[Python F字符串]]

### 转义字符与 raw string

```python
"\n"   # 换行
"\t"   # 制表符
r"C:\Users\Tom"
```

raw string 适合表示包含大量反斜杠的文本，例如 Windows 路径和正则表达式。

关联：[[Python 反斜线]]、[[Python 原始字符串]]

## 2. 文件读写

最重要的统一结构：

```python
with open("data.txt", "r", encoding="utf-8") as f:
    ...
```

### 读取

```text
read()        → 整个文件
readline()    → 一行
readlines()   → 所有行列表
for line in f → 逐行遍历
```

### 写入

```text
w → 覆盖写入 / 不存在则创建
a → 追加
x → 只创建新文件，已存在就报错
```

关联：[[Python 读取文本文件]]、[[Python 写文本文件]]、[[Python 创建文本文件]]

## 3. CSV

CSV 可以理解为简单的表格文本格式。

```text
csv.reader     → 每行是 list
csv.DictReader → 每行是 dict
csv.writer     → 写列表 / 元组
csv.DictWriter → 写字典
```

关联：[[Python 读取 CSV 文件]]、[[Python 写 CSV 文件]]

## 4. 路径与目录

现代 Python 项目推荐逐渐熟悉 `pathlib.Path`：

```python
from pathlib import Path

path = Path("data") / "users.txt"
```

常用操作：

```text
exists() → 是否存在
is_file() → 是否是文件
is_dir()  → 是否是目录
mkdir()   → 创建目录
rename()  → 重命名 / 移动
unlink()  → 删除文件
rglob()   → 递归查找文件
```

旧代码中仍会大量看到 `os` / `os.path`，需要认识但不必把两套 API 都背下来。

关联：[[Python 检查文件是否存在]]、[[如何在 Python 中操作目录]]、[[如何在 Python 中从目录中列出文件]]、[[如何在 Python 中删除文件]]、[[如何在 Python 中重命名文件]]

## 5. pip 与虚拟环境

### pip

```powershell
python -m pip install requests
```

负责安装和管理第三方包。

### venv

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

让每个项目拥有独立的依赖环境。

以后新建 Python 工程时，推荐形成：

```text
创建目录
→ 创建 .venv
→ 激活
→ pip 安装依赖
→ 开发
```

关联：[[Python pip]]、[[Python 虚拟环境]]

## 6. 异常处理补充

Day05 已经学了 `try / except / finally`。

今天补充：

```python
try:
    ...
except ValueError:
    ...
else:
    ...
finally:
    ...
```

```text
except  → 出异常时
else    → 没异常时
finally → 无论如何最后执行
```

关联：[[Python try…except…else]]

## 7. 面向对象编程

这一部分和 Java 的概念非常接近，但重点要放在 Python 的实际写法。

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        return f"Hi, I'm {self.name}"

person = Person("Tom")
```

核心链条：

```text
class
→ object / instance
→ __init__
→ self
→ attribute
→ method
→ inheritance
→ super()
→ override
```

关联：[[Python 类]]、[[Python 面向对象编程]]

## 8. Day06 当前优先级

```text
★★★★★ 文件读写 + with open
★★★★★ pip / venv
★★★★★ class / object / __init__ / self
★★★★☆ pathlib 路径处理
★★★★☆ f-string
★★★☆☆ CSV
★★★☆☆ 继承 / super()
★★☆☆☆ os.walk / 文件重命名删除
★★☆☆☆ try...except...else
```

今天最重要的不是“Python 教程终于快看完了”，而是把 Python 从语法知识推进到实际应用：

```text
会处理文件
会管理项目依赖
会创建隔离环境
能读懂类和对象
```

这些才是下一阶段进入真实 Python 项目和后端开发的接口。