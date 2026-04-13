# 0.1: 安装

- **完成时间：** 15 分钟

- **前置条件：** Claude Pro 或 Max 订阅

## 概述

模块 0.1 

涵盖 Claude Code 的安装和认证。本参考指南提供快速访问信息，作为交互式教程的补充。

**核心要点：** Claude Code 需要 Node.js 18+ 和付费 Claude 订阅。满足前置条件后，安装只需不到 5 分钟。

## 前置条件

| 要求 | 详情 |
|---|---|
| **Claude 订阅** | Claude Pro（$20/月）或 Claude Max。不支持免费版。在 [claude.ai](https://claude.ai/) 注册 |
| **Node.js** | 需要版本 18 或更高。从 [nodejs.org](https://nodejs.org/) 下载 |
| **操作系统** | macOS 或 Windows 10+ |

## 如何打开终端

本指南中的所有命令都需要在**终端**（也称为命令行）中输入。以下是打开方法：

**Mac：**

1. 按 `Cmd + Space` 打开 Spotlight

2. 输入 "Terminal"

3. 按 Enter

**Windows：**

1. 按 Windows 键

2. 输入 "PowerShell"

3. 按 Enter

你会看到一个带有闪烁光标的窗口——这就是你输入命令的地方。

## 快速安装

### 检查 Node.js 版本

**打开终端，输入以下命令，然后按 Enter：**

```
node --version
```

如果显示 `v18.0.0` 或更高版本，继续安装。否则，先安装 Node.js。

### 安装 Node.js（如需要）

**推荐：** 从 [nodejs.org](https://nodejs.org/) 下载 LTS 版本

**使用包管理器：**

| 平台 | 命令 |
|---|---|
| **macOS** | `brew install node` |
| **Windows** | `choco install nodejs` |

**重要：** 安装 Node.js 后，完全关闭终端窗口并重新打开一个新的。这会刷新系统的 PATH，使其能识别 `node` 命令。

### 安装 Claude Code

**在终端中，复制并粘贴以下命令之一，然后按 Enter：**

**Mac：**

```
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell)：**

```
irm https://claude.ai/install.ps1 | iex
```

### 验证安装

**在终端中输入以下命令并按 Enter：**

```
claude --version
```

如果显示版本号，说明安装成功。如果显示 `command not found`，完全关闭终端窗口并重新打开一个新的，然后重试。

## 认证

**在终端中输入以下内容并按 Enter：**

```
claude
```

当出现提示时：

1. 选择 "Claude account with subscription"（不是 Anthropic Console）

2. 完成浏览器认证

3. 选择你喜欢的终端文本样式

认证完成后，你将看到 Claude Code 欢迎界面。

## 健康检查

**在 Claude Code 中，输入以下命令：**

```
/doctor
```

这将验证：

- 安装完整性

- 有效订阅

- 系统配置

- 常见问题

健康的输出会显示所有项目的绿色对勾。

## 故障排除

### Command not found: claude

**解决方法：**

1. 完全关闭终端窗口并重新打开一个新的

2. 如果仍然失败，检查 PATH 配置：

**Mac：** 添加到 `~/.bashrc` 或 `~/.zshrc`：

```
export PATH=$HOME/.local/bin:$PATH
```

**Windows：** 重启电脑（安装程序会自动更新 PATH）

### Subscription required

- 在 [claude.ai](https://claude.ai/) 验证有效的 Claude Pro/Max 订阅

- 退出并重新登录以刷新认证

### Node version too old

**在终端中输入：**

```
node --version
```

如果低于 v18.0.0，从 [nodejs.org](https://nodejs.org/) 下载最新 LTS 版本

### Permission denied

**Mac：**

```
sudo curl -fsSL https://claude.ai/install.sh | bash
```

**Windows：** 以管理员身份运行 PowerShell（右键点击 PowerShell → 以管理员身份运行）

## 命令参考

| 命令 | 功能 |
|---|---|
| `node --version` | 检查 Node.js 版本 |
| `claude` | 启动 Claude Code |
| `claude --version` | 检查 Claude Code 版本 |
| `/doctor` | 运行系统健康检查（在 Claude Code 内） |
| `/help` | 查看可用命令（在 Claude Code 内） |

## 资源

- [官方文档](https://docs.claude.com/en/docs/claude-code)

- [GitHub Issues](https://github.com/anthropics/claude-code/issues)

- Claude Code 社区论坛

## 下一步

**模块 0.2：** 启动 Claude Code 并克隆课程仓库。

你将学到：

- 与 Claude Code 进行第一次对话

- 使用 Claude 克隆仓库

- 理解基于意图的任务委派

交互式学习路径：继续学习课程仓库的 CLAUDE.md 文件

**关于本课程**

由 [Carl Vellotti](https://www.linkedin.com/in/carlvellotti/) 创建。如果你对本模块或整个课程有任何反馈，请给我留言！我正在为 PM 构建者打造一个通讯和社区，欢迎查看 [The Full Stack PM](https://fullstackpm.com/subscribe?utm_source=ccforpms&utm_medium=course&utm_campaign=installation)。

**源仓库：** [github.com/carlvellotti/claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course)

[0.0: 课程介绍](https://ccforpms.com/getting-started/introduction) 

[0.2: 下载与开始](https://github.com/STRUGGLE1999/claude-code-pm-course-cn/blob/main/module0/02-start-and-clone.md)
