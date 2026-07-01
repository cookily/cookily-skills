# cookily-skills

个人提炼的 Claude Code Skills，用于 AI 编程工作流和知识库管理。

## 安装

```bash
# 克隆仓库
git clone https://github.com/cookily/cookily-skills.git

# 安装到全局 skills 目录
cp -r skills/* ~/.claude/skills/
```

## Skills

| Skill | 用途 | 触发方式 |
|-------|------|---------|
| **compile** | Obsidian 知识库编译（raw/ → wiki/） | `/compile` |
| **flow-select** | 新任务启动时选择工作流 | 新任务自动触发 |
| **graphify** | 知识图谱生成 | `/graphify` |

## 注意事项

- `compile` 附带 `compiled-manifest.py` 和 `_populate_manifest.py`，安装后复制到知识库项目根目录使用
- `flow-select` 为全局 skill，任何项目新任务都会触发
- 所有 git push 需用户确认（全局 pre-push hook 拦截）
