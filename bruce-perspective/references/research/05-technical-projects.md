# Bruce 技术与项目分析

## 技术栈

### 前端
- Vue.js (Vue3, Vue Router, Pinia)
- Bootstrap 5
- HTML/CSS/JavaScript
- Blazor (MAUI)

### 后端
- Spring Boot (Java)
- Go (GORM)
- Python (FastAPI, akshare)
- Node.js

### 数据库
- MySQL (主要)
- Navicat Premium 管理

### 基础设施
- Ubuntu 服务器 (阿里云 + 自建)
- Raspberry Pi (本地开发)
- Docker, Nginx
- Git/GitHub (Bruce-Sakura)
- n8n (自动化工作流)

### AI/ML
- Python (akshare, scikit-learn)
- LSTM/GRU/Transformer 模型（学习中）
- OpenAI API, DeepSeek API

## 项目清单

### 1. MyMusic (音乐在线平台)
- 前端: Vue3 + Bootstrap
- 后端: Spring Boot + MyBatis Plus
- 功能: 用户登录、音乐播放、JWT 认证
- 部署: 192.168.0.3 (PI)

### 2. AIEverywhere (AI 健康平台)
- 定位: AI Health Advisor
- 功能: 医疗咨询、健康信息管理、职业数据库
- 数据库: 多表关联（用户、角色、医生、健康信息）
- 目标: 创业项目，寻求融资

### 3. AutoTranslate (自动翻译工具)
- 前端: Android (MAUI Blazor)
- 后端: Go
- 数据库: MySQL
- 部署: 192.168.2.128 (VM)

### 4. CSE_EXAM 系统
- 用途: 考试系统
- 后端: Spring Boot
- 数据库: MySQL

### 5. Minecraft 服务器
- 类型: Fabric + Velocity 代理
- 插件: LuckPerms, Essential Commands
- 运行环境: Ubuntu
- 状态: 活跃维护中

### 6. n8n 自动化工作流
- AI News: 定时抓取 RSS → 飞书推送
- 触发: 每 8 小时

## AI 编程工具演进

**2025-2026 工具变迁：**
1. Trae → 已抛弃
2. Cursor → 已抛弃
3. OpenClaw → 当前主力（建立框架 + Git 版本控制）
4. Codex → 项目优化 + bug 修复
5. Claude Code → 使用中

**核心心得：**
- AI 编程使开发时间从周级降到天级
- 1-2 天可以制作一个简单小软件
- 最佳实践: OpenClaw 搭框架 + Codex 优化
