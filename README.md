# cookily/skills

个人 AI 技能库。一行命令装到任意 Agent，跨 Claude Code / Codex / Hermes / Cursor 通用。

## 安装

```bash
npx skills add https://github.com/cookily/skills
```

## 包含技能

| 技能 | 触发 | 做什么 |
|------|------|--------|
| **compile** | `/compile` | 把 `raw/` 里的杂乱资料编译成结构化知识库（摘要+概念+索引） |
| **graphify** | `/graphify` | 把任意文件夹变成知识图谱，自动发现文件间的关系 |

## 使用

### /compile

把文章丢进 `raw/`，输入 `/compile`，自动：

- 扫描未编译文件
- 生成一句话摘要 + 核心要点
- 方法论类文章自动提取概念卡片
- 更新索引，建立交叉链接

```bash
/compile
```

### /graphify

把文件夹变成交互式知识图谱：

```bash
/graphify                    # 当前目录全量扫描
/graphify raw/               # 只处理 raw 文件
/graphify . --graphml        # 导出 GraphML 格式
/graphify . --update         # 增量更新（只处理新文件）
/graphify . --mode deep      # 深度提取，更丰富的关联
```

输出：交互式 HTML 图谱 + JSON 数据 + 社区聚类 + 审计报告。

## 两个技能怎么配合

```
你随手丢一篇文章进 raw/
       ↓
   /compile    ← 提炼（文章 → 摘要 + 概念）
       ↓
   /graphify   ← 连接（散点 → 知识网络）
```

## 添加新技能

在 `skills/` 下新建文件夹，放一个 `SKILL.md` 即可：

```
skills/
├── compile/
│   └── SKILL.md
├── graphify/
│   └── SKILL.md
└── your-new-skill/
    └── SKILL.md
```

然后重新安装即可获取新技能：
```bash
npx skills add https://github.com/cookily/skills
```

## License

MIT
