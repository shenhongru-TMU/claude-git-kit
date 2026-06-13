---
name: wrap-up
description: 每日收工：选择性提交 + 生成 commit message + 推送到 GitHub
user-invocable: true
allowed-tools: Bash(git *), Read
---

# 每日收工

请逐步完成以下收工流程：

## 第一步：拉取远程最新
先执行 `git pull --rebase`，确保本地不会覆盖远端改动。
如果出现冲突，停止流程，列出冲突文件，让我手动处理。

## 第二步：列出所有改动
执行 `git status`，把所有改动的文件按重要性分成三类展示：

| 分类 | 说明 |
|------|------|
| 📌 核心改动 | 代码、脚本、最终结果图 |
| 📎 次要改动 | 文档、配置 |
| 🗑️ 临时/草稿 | 临时日志、中间结果、实验草稿 |

## 第三步：看 diff 总结
执行 `git diff --stat`，用一句话概括每类改动的核心内容。

## 第四步：让我选择
问我：「**哪些要加入这次提交？**」等我的答案。只 add 我选中的文件。

## 第五步：生成 commit message
根据我选中的文件改动内容，生成符合 Conventional Commits 规范的提交信息：
```
<type>(<scope>): <简短描述>
- 具体改动 1
- 具体改动 2
```
type 从以下选：feat / fix / docs / refactor / results / chore
把 commit message 展示给我确认。

## 第六步：提交并推送
确认后执行：
```bash
git add <我选中的文件>
git commit -m "<确认的message>"
git push
```
完成后展示本次提交的 `git log --oneline -1`。
