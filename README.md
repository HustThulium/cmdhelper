# cmdhelper

一个命令行提示器，用于记录和查询自己常用的命令。支持按关键词搜索，并以「注释 + 命令」的块形式展示结果。

## 功能

- **列出全部**：`cmdhelper` 无参数时列出所有已记录命令。
- **关键词搜索**：`cmdhelper 关键词` 在注释和命令中不区分大小写搜索，只输出匹配到的完整块。
- **添加命令**：`cmdhelper -add` 交互式添加一条新命令（先输入注释说明，再输入具体命令）。

数据保存在同目录下的 `helpers.txt` 中，每条命令的格式为：

```
# 注释说明
具体命令
空行
```

## 通过 PATH 安装

把本项目所在目录加入环境变量 `PATH` 后，即可在任意目录直接执行 `cmdhelper`。

### 1. 临时生效（仅当前终端）

```bash
export PATH="/path/to/cmdhelper:$PATH"
```

将 `/path/to/cmdhelper` 替换为本项目实际路径，例如：

```bash
export PATH="$HOME/workspace/cmdhelper:$PATH"
```

### 2. 永久生效（推荐）

在 shell 配置文件中加入上述 `export`，然后重新加载配置或新开终端。

**Bash**（`~/.bashrc` 或 `~/.profile`）：

```bash
echo 'export PATH="/path/to/cmdhelper:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

**Zsh**（`~/.zshrc`）：

```bash
echo 'export PATH="/path/to/cmdhelper:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

请将 `/path/to/cmdhelper` 替换为你本机上的项目目录绝对路径。安装后可直接运行：

```bash
cmdhelper          # 列出全部
cmdhelper hugo     # 搜索含 hugo 的命令
cmdhelper -add     # 添加新命令
```
