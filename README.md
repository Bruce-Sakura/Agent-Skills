# Agent-Skills

个人 OpenClaw Skills 仓库，存放自定义 Agent 技能。

## 目录

| Skill | 说明 | 状态 |
|-------|------|------|
| [server-monitor](./server-monitor/) | 服务器监控：CPU/内存/GPU/温度/进程 | ✅ |

## 安装

```bash
# 克隆到 OpenClaw skills 目录
git clone https://github.com/Bruce-Sakura/Agent-Skills.git ~/.openclaw/skills-repo

# 软链接需要的 skill
ln -s ~/.openclaw/skills-repo/server-monitor ~/.openclaw/skills/server-monitor
```

## 添加新 Skill

```bash
mkdir 新skill名
# 在里面放 SKILL.md + scripts/ + references/ + deploy/ 等
# 更新上面的目录表格
git add . && git commit -m "feat: 新skill" && git push
```

## 规范

- 每个 skill 一个文件夹
- 必须包含 `SKILL.md`（含 YAML frontmatter）
- 可选：`scripts/`、`references/`、`deploy/`、`assets/`
- 参考 [skill-creator 规范](https://github.com/openclaw/openclaw/tree/main/skills/skill-creator)
