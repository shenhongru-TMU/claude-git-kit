---
name: start
description: Daily start — pull latest code and review last session's status
user-invocable: true
allowed-tools: Bash(git *), Read
---

# Daily Start

## Step 1: Pull latest changes
Run `git pull --rebase` to fetch the latest commits from remote.
Show what was pulled down.

## Step 2: Review last session
Run `git log --oneline -5` to show the last 5 commits, so I can recall where I left off.

## Step 3: Current status
Run `git status --short` to show the current working tree state.
