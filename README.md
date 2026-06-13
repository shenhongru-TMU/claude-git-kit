# claude-git-kit

Claude Code multi-machine Git workflow kit. One command to start the day, one to wrap it up.

## What it does

- `/start` — Daily start: git pull + review recent commits + check working tree
- `/wrap-up` — Daily wrap-up: selectively stage files + auto commit message + push
- `settings.json` — Whitelist git commands (no more permission prompts)

## Core principle

> You pick the files. Claude executes. Pull before starting, push when done. Only commit what's worth keeping — temp files stay local.

## How to use

### First time: copy into your project

```bash
cp -r .claude /path/to/your-project/
```

### Every day

```
Morning   →  cd into project → claude → /start
Work      →  chat, code, run experiments
Wrap-up   →  /wrap-up → pick files → commit → push
```

### Multi-machine collaboration

```
Local Mac                    Server
/start pull  ←── GitHub ──→  /start pull
Work                         Work
/wrap-up push ──→ GitHub ←── /wrap-up push
```

## File structure

```
your-project/
  .claude/
    settings.json              ← git whitelist
    skills/
      start/SKILL.md           ← /start
      wrap-up/SKILL.md         ← /wrap-up
```

## Requirements

- Claude Code v2.1.3+
- An existing git repo with a GitHub remote configured
