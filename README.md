# claude-git-kit

Claude Code 多机器协作 Git 工作流套件。一个命令开工，一个命令收工。

## 做了什么

- `/start` — 开工：git pull + 回顾最近 commit + 查看工作区状态
- `/wrap-up` — 收工：选择性提交文件 + 自动生成 commit message + push
- `settings.json` — git 命令免确认白名单

## 核心原则

> 你来选文件，Claude 来执行。开工先 pull，收工才 push。只推值得保留的，临时文件留在本地。

## 怎么用

### 第一次：复制到项目里

```bash
cp -r .claude /path/to/your-project/
```

### 每天

```
早上    →  cd 进项目 → claude → /start
工作中  →  自然对话，改代码、跑实验
收工前  →  /wrap-up → 选文件 → commit → push
```

### 多机器协作

```
本地 Mac                      服务器
/start pull  ←── GitHub ──→  /start pull
干活                          干活
/wrap-up push ──→ GitHub ←── /wrap-up push
```

## 文件结构

```
your-project/
  .claude/
    settings.json              ← git 白名单
    skills/
      start/SKILL.md           ← /start
      wrap-up/SKILL.md         ← /wrap-up
```

## 要求

- Claude Code v2.1.3+
- 项目本身已经 `git init` 且关联了 GitHub remote
