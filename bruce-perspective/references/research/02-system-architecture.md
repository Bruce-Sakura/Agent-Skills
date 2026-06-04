# Bruce 系统架构分析

## Agent 架构

| Agent | Workspace | 用途 | 飞书账号 |
|-------|-----------|------|---------|
| main | ~/.openclaw/workspace | 主 agent，日常交互 | default |
| coder | ~/.openclaw/workspace-coder | 代码任务 | coder |
| legal | ~/.openclaw/workspace-legal | 法律咨询 | legal |

## 隔离原则
- 每个 agent 有独立 workspace
- workspace skill 各自独立，不串
- 全局 skill（~/.openclaw/skills/）所有 agent 共享
- 插件 skill（~/.openclaw/plugin-skills/）所有 agent 共享

## 自动化设置
- 每日新闻简报 cron（UTC 7:00，覆盖中/英/经济）
- self-improving-agent（全局 skill，自动记录错误和学习）
- server-monitor（服务器监控 skill）

## 基础设施
- 服务器：Ubuntu，运行 ubuntu-monitor 项目
- Git：GitHub (Bruce-Sakura/Agent-Skills)
- 通信：飞书（主要渠道）
- 模型：mimo-v2.5-pro
