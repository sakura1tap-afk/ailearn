# Python 虚拟环境 venv

虚拟环境用于给每个项目准备一套独立的 Python 依赖。

为什么需要它？

```text
项目 A 需要 package==1.x
项目 B 需要 package==2.x
```

如果所有项目都共用全局环境，很容易产生版本冲突。

虚拟环境相当于：

> 给每个项目单独准备一个依赖空间。

## Windows 常用流程

在项目目录创建虚拟环境：

```powershell
python -m venv .venv
```

PowerShell 激活：

```powershell
.\.venv\Scripts\Activate.ps1
```

激活后终端通常会出现：

```text
(.venv)
```

然后安装依赖：

```powershell
python -m pip install requests
```

退出环境：

```powershell
deactivate
```

## 虚拟环境里放什么

`.venv` 主要保存：

```text
Python 环境相关文件
第三方依赖
pip 安装的包
```

通常**不要提交到 GitHub**，在 `.gitignore` 中加入：

```gitignore
.venv/
```

项目真正需要记录的是依赖列表，例如：

```powershell
python -m pip freeze > requirements.txt
```

## 当前阶段形成这个习惯

以后新建 Python 项目优先：

```text
创建项目目录
→ python -m venv .venv
→ 激活 .venv
→ 安装依赖
→ 写代码
```

这会成为你后面 FastAPI、RAG、Agent 项目的标准开局动作。