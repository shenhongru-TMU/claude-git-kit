---
name: wrap-up
description: Daily wrap-up — selective commit + auto commit message + push to GitHub
user-invocable: true
allowed-tools: Bash(git *), Read
---

# Daily Wrap-up

Follow these steps one by one:

## Step 1: Pull latest changes
Run `git pull --rebase` first, to avoid overwriting remote changes.
If a conflict occurs, stop and list the conflicting files for manual resolution.

## Step 2: List all changes
Run `git status`, then categorize every changed file into three groups:

| Group | What |
|------|------|
| 📌 Core | Code, scripts, final result figures |
| 📎 Minor | Docs, config files |
| 🗑️ Temp/Draft | Temp logs, intermediate results, experiment drafts |

## Step 3: Summarize the diff
Run `git diff --stat`, then write a one-line summary of what each group changed.

## Step 4: Let me choose
Ask me: **"Which files should go into this commit?"**

Wait for my answer. Only `git add` the files I select.

## Step 5: Generate commit message
Based on the selected changes, generate a Conventional Commits message:
```
<type>(<scope>): <short summary>
- Change 1
- Change 2
```
type must be one of: feat / fix / docs / refactor / results / chore

Show the message for my confirmation.

## Step 6: Commit and push
After I confirm:
```bash
git add <selected files>
git commit -m "<confirmed message>"
git push
```
Finish by showing `git log --oneline -1`.
