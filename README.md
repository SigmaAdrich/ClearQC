<div align="center">

# ✦ ClearQC

**面向化学研究者的量子化学桌面应用**

[下载安装包](https://github.com/SigmaAdrich/ClearQC/releases/latest) · [提交问题](https://github.com/SigmaAdrich/ClearQC/issues)

</div>

---

## 简介

ClearQC 是一款运行在 Windows 上的量子化学计算工具。只需输入分子名称或拖入结构文件，即可完成从电子结构到激发态的一系列量子化学计算，结果以图形化方式直接呈现在应用内。

内置 PySCF 计算引擎（随安装包一同打包），**无需手动配置 Python 或任何依赖**。

---

## 功能

- **分子库检索** — 输入分子名称（中文 / 英文 / IUPAC）自动补全，一键发起计算
- **文件导入** — 支持拖拽导入 XYZ、PDB、MOL/SDF、Gaussian GJF 格式
- **多种计算任务** — 单点能（SP）、几何优化（Opt）、频率分析（Freq）、激发态（TD-DFT）
- **方法与基组** — HF / B3LYP，支持 STO-3G / def2-SVP / def2-TZVP
- **溶剂效应** — PCM 隐式溶剂模型（水、DMSO、甲醇等 8 种）
- **3D 可视化** — 球棍模型、HOMO/LUMO/电子密度轨道等值面
- **光谱图表** — UV-Vis 吸收光谱（TD-DFT）、红外振动光谱（IR）
- **AI 解读** — 接入 OpenAI 兼容接口，一键生成计算结果解读或失败诊断
- **结果导出** — 导出 JSON / CSV，含 Mulliken 电荷、热化学数据、优化构型
- **多语言界面** — 中文 / English / 日本語 / Deutsch
- **深色 / 浅色主题**

---

## 系统要求

| 项目 | 要求 |
|------|------|
| 操作系统 | Windows 10 / 11（64 位） |
| WSL 2 | 需已启用（[安装指南](https://learn.microsoft.com/zh-cn/windows/wsl/install)） |
| 内存 | 建议 8 GB 以上 |
| 磁盘空间 | 约 600 MB（含 WSL 运算环境） |

---

## 安装

前往 [Releases](https://github.com/SigmaAdrich/ClearQC/releases/latest) 下载安装包：

| 安装包 | 大小 | 说明 |
|--------|------|------|
| `ClearQC_x.x.x_x64-setup-offline.exe` | ~135 MB | **推荐**：含完整运算环境，下载即用 |
| `ClearQC_x.x.x_x64-setup-online.exe`  | ~14 MB  | 首次启动时自动下载运算环境（需联网） |

双击安装包按提示操作，安装完成后启动 ClearQC 即可。

> **注意**：首次启动会自动导入 WSL 运算环境（约 30 秒），完成后即可正常使用。

---

## 快速开始

1. 在聊天框输入分子名称，如 `caffeine`（咖啡因）或 `苯`
2. 在弹出的计算卡片上选择计算任务、方法与基组
3. 点击 **Compute** 发起计算
4. 计算完成后，结果卡片显示能量、电荷分布等数据；3D 可视化面板同步更新

也可以直接将 XYZ / PDB / MOL 文件拖入窗口，从自定义结构开始计算。

---

## 许可

© 2025 SigmaAdrich. All rights reserved.