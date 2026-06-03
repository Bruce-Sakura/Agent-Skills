---
name: server-monitor
description: "Check server health status via Ubuntu-Monitor API: CPU, memory, disk, GPU, temperature, processes. Trigger on: server status, check server, server health, 运维检查, 服务器状态, 系统监控."
---

# Server Monitor

Check server health via local Ubuntu-Monitor API (`http://localhost:9000/api/stats`).

## Quick Check

```bash
curl -s http://localhost:9000/api/stats
```

## Workflow

1. Fetch stats from API.
2. Parse JSON response.
3. Evaluate against thresholds (see `references/thresholds.md`).
4. Output dashboard with ✅/⚠️/❌ indicators.
5. For any ⚠️/❌ items, provide actionable suggestions.

## Output Format

```
🖥️ Server Status — ubuntu
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

⏱️  Uptime: up 1 day, 6h | Load: 0.04

🧠 CPU       ✅ 0.7% (16 cores)
💾 Memory    ✅ 2.1/14.8 GB (14.3%)
🔄 Swap      ✅ 0.5/4.0 GB (12.4%)
🌡️  CPU Temp  ✅ 35°C (max core)
🎮 GPU       ✅ RTX 4060 Ti | 32°C | 0% util | 6W
📊 Processes ✅ 25 running

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
✅ All systems normal
```

## Alert Levels

- ✅ Normal — within safe range
- ⚠️ Warning — approaching limit, monitor closely
- ❌ Critical — requires immediate action

## Checks Performed

| Check | Data Source | What It Measures |
|-------|-----------|-----------------|
| CPU usage | `cpu[0].usage` | Overall CPU utilization |
| Memory | `mem.usage` | RAM utilization percentage |
| Swap | `mem.swap_usage` | Swap utilization |
| CPU temp | `temps` (coretemp) | Highest core temperature |
| GPU temp | `gpus[0].temp` | GPU temperature |
| GPU util | `gpus[0].util` | GPU utilization |
| GPU power | `gpus[0].power_draw` | Power consumption |
| Processes | `processes` | Top CPU/memory consumers |

## API Down

If `curl localhost:9000/api/stats` fails:

1. Check service: `systemctl status ubuntu-monitor`
2. Restart if needed: `sudo systemctl restart ubuntu-monitor`
3. Check port: `ss -ltnp | grep 9000`
