# Aurabot 记忆备份

大肥鱼（QQ 机器人）的记忆快照，每三天自动同步一次。

## 这里面有什么

| 路径 | 内容 |
| --- | --- |
| `data/memories.json` | 记忆库：她自己记的事、自动提炼的事实、每个人的人物档案、相处经验 |
| `data/diary.json` | 日记 |
| `data/mood.json` | 心情（四个维度的数值和最近的起伏） |
| `data/sessions.json` | QQ 会话和 DSH 会话的对应关系 |
| `data/speakup.json` | 主动搭话的节流记录 |
| `data/recent-media.json` | 最近发过的图 |
| `data/config.redacted.json` | 配置的脱敏快照（密码、token、cookie 全部抹掉了） |
| `personas/*.md` | 人格文件 |

## 这里面没有什么

- SnowLuma 的 WebUI 密码、WebSocket token
- 哔哩哔哩 / 抖音 / 小黑盒的登录 cookie
- 生图服务的 API key
- 大文件（头像、表情包图库、翻唱音频）

## 怎么恢复

把 `data/` 和 `personas/` 整个拷回：

```
C:\Users\<用户名>\.dsh\plugins-data\aurabot\
```

覆盖之前先停掉 Aurabot（面板里的总开关关掉），覆盖完再打开。

配置别直接拿 `config.redacted.json` 覆盖回去，那份是脱敏的，密码是空的。
要恢复配置就用本地现成的，或者手动把密码补回去。

## 手动同步

```powershell
powershell -ExecutionPolicy Bypass -File E:\qqbot\scripts\sync-memory.ps1
```

日志在同目录 `_sync.log`。
