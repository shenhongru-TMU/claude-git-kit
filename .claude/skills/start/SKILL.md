---
name: start
description: 每日开工：拉取最新代码，回顾上次收工状态
user-invocable: true
allowed-tools: Bash(git *), Read
---

# 每日开工

## 第一步：拉取远程最新
执行 `git pull --rebase`，获取服务器或本地推上来的最新改动。
展示拉下来了哪些新 commit。

## 第二步：回顾上次收工
执行 `git log --oneline -5`，展示最近 5 条 commit，帮我回忆起上次干到哪了。

## 第三步：当前状态
执行 `git status --short`，展示当前工作区状态。
