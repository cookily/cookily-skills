---
name: flow-select
description: Use when the user starts a new development task, feature, or bugfix — before any code is written. Presents workflow options and lets the user choose.
---

# Flow Select

## Overview

用户提出新任务时，不直接开干，**先分析任务规模，给出流程选项，让用户选**。

## When to Use

- 用户说"加一个 XX 功能"、"改一下 XX"、"修一个 bug"
- 任何会写代码、改文件的任务

**不要用：** 纯问答、知识库查询、只读操作

## Workflow

### 第一步：分析任务

快速判断：
- 涉及几个文件？
- 改动明确还是模糊？
- 有没有风险（改核心逻辑、数据库、安全相关）？

### 第二步：出选项

```
这个任务涉及 X 个文件，建议走：

0. ⚡ 自由发挥 — 直接说直接做，不管流程
1. 🔥 日常最短 — plans → subagent → verification（~10 min 人投入）
2. 📋 带规范 — OpenSpec propose → [Superpowers] → verify → archive（~15-20 min）
3. 🧱 完整流程 — brainstorming → worktree → TDD → review → finishing（~30 min）

你选哪个？
```

### 第三步：按选择执行

| 选择 | 执行 |
|------|------|
| 0 | 直接写代码，不调任何流程 skill |
| 1 | 调 `writing-plans` → `subagent-driven-development` → `verification-before-completion` |
| 2 | 用户手动 `/opsx:propose`，走 OpenSpec 流程 |
| 3 | 调 `brainstorming` → `writing-plans` → `using-git-worktrees` → 完整链路 |

## 建议判断参考

| 任务特征 | 默认推荐 |
|----------|---------|
| 一次性脚本、临时测试 | 0 自由发挥 |
| 小 bug，改动明确 | 1 日常最短 |
| 1-3 个文件的中等功能 | 1 日常最短 |
| ≥ 3 个文件、新功能 | 3 完整流程 |
| 需求模糊、怕做偏 | 2 带规范 |
| 重构、安全修复 | 3 完整流程 |

**但最终决定权在用户。** 推荐只是建议，用户选哪个就走哪个。

## 注意

- 不要自己决定走哪个流程，必须先问
- 如果用户选 0，不要偷偷加流程步骤
- 如果用户选了之后改主意，随时切换