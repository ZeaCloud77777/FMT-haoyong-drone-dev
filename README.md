# 好用无人机（FMT）硬件平台 · 开发与测试记录

> 面向「好用无人机」硬件平台的持续开发、版本管理与测试问题跟踪仓库。
> 平台：FMT 飞控固件 + FMT-SIM 仿真（SIH/HIL）+ ROS2 机载（NVIDIA Nano）。

本仓库用于**跨多次迭代沉淀事实**：固件与参数如何演进、在什么时间测过什么、出现过什么问题、当前结论是什么。目标是让任何一次测试都能回放到当时的版本与状态。

## 目录结构

```
.
├── README.md                # 本文件：项目说明与维护指南
├── CHANGELOG.md             # 版本 / 固件 / 参数发布记录（Keep a Changelog 风格）
├── docs/                    # 里程碑报告与权威文档
│   └── fmt-hao-drone-progress-report/   # 正式开发进度报告（HTML）
├── issues/                  # 问题记录：建议在 GitHub Issues 维护，此处放模板与归档
│   └── 问题跟踪模板.md
├── tests/                   # 每次测试一份记录（含时间 / 版本 / 环境 / 结果）
│   └── 测试记录模板.md
├── firmware/                # 固件与参数登记说明（版本、变更、下载/存放方式）
└── logs/                    # 原始测试日志 / 飞行数据说明与归档指引
```

## 工作流：如何持续记录

### 1. 每次测试（tests/）
新增 `tests/YYYY-MM-DD_本次主题.md`，内容严格按 `测试记录模板.md`：时间、所用固件/参数版本、环境（真机/SIH/HIL）、步骤、结果、问题链接。

### 2. 每个问题（GitHub Issues）
按 `issues/问题跟踪模板.md` 新建 Issue，状态流转：
`待处理 → 定位中 → 待验证 → 已解决`，并在描述里关联：测试记录、固件版本、commit。

### 3. 每次发版（CHANGELOG.md / firmware/）
固件或参数有更新就在 `CHANGELOG.md` 顶部追加一条：日期、版本、变更、影响（尤其参数改名）、验证状态。固件二进制与 param 建议入 `firmware/`（或给出可验证的存放方式）。

## 环境与关键信息

| 项目 | 说明 |
|---|---|
| 飞控固件 | FMT (Firmament Autopilot)；FMS / CONTROL / INS / MCN 总线 |
| 仿真 | FMT-SIM（SIH / HIL），可用 UE 数字孪生地图 |
| 地面站 | QGroundControl + RTK 基站 |
| 关键指令 | `mcn suspend pilot_cmd|gcs_cmd`、`test`（电机注入）、`mcn echo bat_status`、`mlog` |

## 安全与内容规范

- 仓库为**公开**性质，禁止上传：内部培训资料、地址、手机号等你方内部文档。
- 飞行测试注意载荷上限（避免电机饱和）与室内定位源，详见 `docs/` 报告的风险章节。

## 许可证

待定（联系人确认后补充）。