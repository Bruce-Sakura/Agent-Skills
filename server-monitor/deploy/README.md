# Ubuntu-Monitor 部署指南

Go + Gin 服务器监控服务，提供系统状态 API 和 Web 仪表盘。

## 快速部署

```bash
# 1. 复制文件
sudo mkdir -p /opt/Ubuntu-Monitor
sudo cp deploy/ubuntu-monitor /opt/Ubuntu-Monitor/myapp
sudo chmod +x /opt/Ubuntu-Monitor/myapp

# 2. 安装 systemd 服务
sudo cp deploy/ubuntu-monitor.service /etc/systemd/system/
sudo systemctl daemon-reload

# 3. 启动
sudo systemctl enable ubuntu-monitor
sudo systemctl start ubuntu-monitor
```

## 环境变量

| 变量 | 默认值 | 说明 |
|------|--------|------|
| `HOST` | `0.0.0.0` | 监听地址 |
| `PORT` | `9000` | 监听端口 |
| `GIN_MODE` | `release` | Gin 模式 (debug/release) |

修改方式：编辑 `/etc/systemd/system/ubuntu-monitor.service` 中的 `Environment` 行。

## 访问

- Web 仪表盘: `http://localhost:9000/`
- 健康检查: `http://localhost:9000/health`
- 系统数据 API: `http://localhost:9000/api/stats`

## 常用命令

```bash
# 查看状态
systemctl status ubuntu-monitor

# 查看日志
journalctl -u ubuntu-monitor -f

# 重启
sudo systemctl restart ubuntu-monitor

# 停止
sudo systemctl stop ubuntu-monitor
```

## 监控的数据

- CPU 使用率（逐核）
- 内存 / Swap
- 温度传感器（CPU、NVMe、PCH、WiFi）
- GPU（NVIDIA：温度、风扇、利用率、显存、功耗）
- Top 进程（按 CPU/内存排序）

## 依赖

- Linux (amd64)
- NVIDIA 驱动（可选，GPU 监控需要）
- 无需额外依赖，静态编译的 Go 二进制
