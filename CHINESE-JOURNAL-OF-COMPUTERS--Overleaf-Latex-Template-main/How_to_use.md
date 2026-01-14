# GitHub 仓库使用与维护指南

本文档旨在帮助你管理、维护和使用存储在 GitHub 上的 LaTeX 论文项目。

## 1. 初次设置 (在新设备上)

如果你在一台新电脑上开始工作，需要先克隆仓库：

`ash
# 请将 <Repo_URL> 替换为你的 GitHub 仓库地址
git clone <Repo_URL>
`

## 2. 日常写作流程 (同步文档)

当你完成了一段写作、修改了 LaTeX 代码或上传了新图片后，请按以下步骤同步：

### 2.1 检查状态
查看哪些文件发生了变动：
`ash
git status
`

### 2.2 添加更改
将变动添加到暂存区：
`ash
# 添加所有更改 (推荐)
git add .
`

### 2.3 提交更改 (Commit)
将暂存区的变动保存为一个个版本快照：
`ash
git commit -m "填写修改说明，例如：完成引言部分写作"
`

### 2.4 推送至 GitHub (Push)
将本地的提交上传到 GitHub 服务器：
`ash
git push
`

---

## 3. 多人协作与更新 (拉取)

如果仓库被其他人修改，或者你在另一台设备上推送了更新，在开始工作前请务必先拉取最新版本：

`ash
git pull
`

**提示：** 养成 **先 pull，再写作，最后 push** 的好习惯，可以最大程度避免冲突。

---

## 4. 常见问题处理

### 4.1 换行符警告 (LF will be replaced by CRLF)
如果在 Windows 上看到关于 LF 和 CRLF 的警告，这是正常的。Git 会自动处理 Windows (CRLF) 和 Linux (LF) 的换行符转换。
- 这通常**不会影响** LaTeX 编译。
- 你可以忽略此警告。

### 4.2 忽略编译中间文件 (.gitignore)
LaTeX 编译会产生大量辅助文件 (如 .aux, .log, .fdb_latexmk)。建议不要将这些文件上传到 GitHub。
确保你的仓库根目录有一个 .gitignore 文件，并包含以下内容：
`	ext
*.aux
*.log
*.out
*.pdf
*.gz
*.fls
*.fdb_latexmk
*.bbl
*.blg
`

## 5. 常用命令速查表

| 命令 | 作用 |
| :--- | :--- |
| \git status\ | 查看当前文件状态 |
| \git add .\ | 添加所有修改到暂存区 |
| \git commit -m "msg"\ | 提交修改并附带说明 |
| \git push\ | 上传到远程仓库 |
| \git pull\ | 从远程仓库拉取更新 |
| \git log\ | 查看提交历史 |
