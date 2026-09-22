# Changelog

本项目遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/) 语义。格式：

```
## [版本号] - YYYY-MM-DD

### Added / Changed / Fixed / Deprecated / Removed
- 说明（关联 issue / 测试记录）
```

最新条目总是位于顶部。**每次固件、参数或重大变更发布时间机在顶部追加新条目。**

---

## [进行中 · 待验证] - 2026-09-15

### Added
- 电机饱和处理固件 `fmt_sieon-s1.bin`（含 FMS/CONTROL 参数改名）。
- 配套参数 `param.xml`（v2，用于更新实机 /sys 目录）。

### Changed
- 固件修改了 `FMS` / `CONTROL` 部分参数名，飞控外部设置参数需同步改名。

### 状态
- 待实机验证姿态失衡修复效果（对应问题 #6）。

---

## [已发布] - 2026-08-11

### Added
- 电机异常故障注入代码（`test` 指令 + 序号 1/2/4/8 ↔ 1~4 号电机），已合入 FMT-Firmware。

---

## [里程碑] - 2026-05-25

### Added
- ROS2 多机通讯闭环 Demo；板载 offboard 测试通过。
- 飞控日志记录与数据在环分析（DataSIM）流程说明。

---

> 更早的拆分记录以群里讨论、测试记录与 issues 为准，后续逐步补入。