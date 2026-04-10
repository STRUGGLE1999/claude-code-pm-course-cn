# 4.4：GitHub

- **完成时间：** 15分钟

**互动课程：** 在 Claude Code 中运行 `/start-4-4`

**本节内容：** 将你的项目推送到私有 GitHub 仓库。

## 什么是版本控制？

版本控制是一个随时间跟踪文件每次变更的系统。

把它想象成 Word 中的"修订"功能，但适用于整个项目。你可以：

- 查看每次变更的历史

- 回到任何之前的版本

- 撤销错误

它永远解决了"最终版_v3_真正的最终版.docx"的问题。

## Git vs GitHub

这两个相关但不同：

**Git** = 在你电脑上运行的版本控制系统。它在本地跟踪变更。

**GitHub** = 在云端存储你的 Git 仓库的网站。

类比：Git 就像 Microsoft Word（工具）。GitHub 就像 Google Drive（你存储和分享文件的地方）。

## 关键术语

| 术语 | 含义 |
|---|---|
| **Repository（仓库/Repo）** | 被 Git 跟踪的项目文件夹 |
| **Commit（提交）** | 某个时间点保存的快照 |
| **Push（推送）** | 从你的电脑上传提交 → GitHub |
| **Pull（拉取）** | 从 GitHub 下载变更 → 你的电脑 |

## 为什么部署需要这个

现在你的代码只存在于你的电脑上。如果你的笔记本电脑坏了，代码就没了。

更重要的是：部署服务需要从某个地方拉取你的代码。GitHub 就是那个地方。

当你在下一节部署时，Vercel 会连接到你的 GitHub 仓库并自动拉取代码。

## 什么是 GitHub CLI？

GitHub CLI（`gh`）是一个用于操作 GitHub 的命令行工具。

Claude 使用它，这样你就不必自己输入 Git 命令。它通过浏览器使用设备码流程进行认证——你会看到一个代码，在 GitHub 网站上输入它，就连接成功了。

## 故障排除

### "gh: command not found"

GitHub CLI 没有安装。

- **Mac：** 运行 `brew install gh`

- **其他：** 从 [cli.github.com](https://cli.github.com/) 下载

### 认证失败

重新运行 `gh auth login` 并确保完成浏览器步骤。你需要输入代码并点击"Authorize"。

### "Repository already exists"

你的 GitHub 上已经存在同名仓库。可以：

- 选择不同的名称

- 先在 github.com 上删除现有仓库

### "Permission denied"

你的认证令牌已过期。重新运行 `gh auth login`。

### 在 github.com 上找不到仓库

确保你在浏览器中登录了正确的 GitHub 账户。

## 下一步

[**4.5：上线 →**](https://ccforpms.com/vibe-coding/go-live) - 将应用部署到互联网并获得可分享的真实 URL
