<div align="center">

# ✦ ClearQC

**面向化学研究者的量子化学桌面应用**

[下载安装包](https://github.com/SigmaAdrich/ClearQC/releases/latest) · [提交问题](https://github.com/SigmaAdrich/ClearQC/issues)

**中文 · [English](README.en.md) · [Deutsch](README.de.md) · [日本語](README.ja.md)**

</div>

---

## 简介

ClearQC 是一款运行在 Windows 上的量子化学计算工具。只需输入分子名称或拖入结构文件，即可完成从电子结构到激发态的一系列量子化学计算，结果以图形化方式直接呈现在应用内。

内置 PySCF 计算引擎（随安装包一同打包），**无需手动配置 Python 或任何依赖**。

---

## 量子化学能算什么？举几个例子

你可能觉得"量子化学"很抽象。下面用几个具体的例子说明它能帮你做什么：

**🔬 分子结构优化（Geometry Optimization）**
给定一个分子的初始构型，让计算机找到它能量最低、最稳定的三维形状。就像你把一个弹簧拧成某个形状，它会自己弹回平衡位置——计算机帮你找的就是那个平衡位置。

**⚡ 前线轨道（HOMO / LUMO）**
HOMO 是"最高占据分子轨道"，LUMO 是"最低未占分子轨道"。这两个轨道决定了分子在化学反应中"从哪里失去电子"、"从哪里接受电子"——也就是反应活性。ClearQC 会把它们画成漂亮的三维等值面。

**🌈 紫外-可见光谱（TD-DFT / UV-Vis）**
为什么苯环在紫外区有吸收？为什么染料有颜色？用激发态计算（TD-DFT）可以预测分子会吸收哪些波长的光，直接对应实验室的 UV-Vis 光谱仪结果。

**📳 红外光谱（IR）**
分子的化学键就像弹簧，会在特定频率振动。频率分析可以预测红外吸收峰，对应实验室 IR 光谱仪测出的结果。

**🧪 Mulliken 电荷**
告诉你分子中每个原子上"多带了多少电荷"，帮助你理解极性、氢键位点、亲核 / 亲电位置。

---

## 截图预览

![ClearQC 界面截图](docs/screenshot.png)

---

## 功能一览

| 功能 | 说明 |
|------|------|
| 分子库检索 | 输入中文名、英文名或 IUPAC 名称，自动找到分子并准备计算 |
| 文件导入 | 拖拽导入 XYZ、PDB、MOL/SDF、Gaussian GJF 格式 |
| 计算方法 | HF · 21 种 DFT 泛函（B3LYP、PBE0、M06-2X、ωB97X-V、CAM-B3LYP …）· 后 HF（MP2、CCSD、CCSD(T)） |
| 基组 | 28 个基组，覆盖 Pople、Dunning、Karlsruhe、pcseg、ECP 家族 |
| 单点能计算 | 计算给定构型下的电子能量 |
| 几何优化 | 自动搜索最稳定的分子构型 |
| 频率分析 | 计算振动频率，生成红外光谱 |
| 激发态（TD-DFT） | 计算光吸收，生成 UV-Vis 光谱 |
| 溶剂效应 | 8 种隐式溶剂（ddCOSMO）：水、DMSO、甲醇、乙醇、乙腈、THF、DCM、甲苯 |
| 3D 可视化 | 球棍模型 + HOMO/LUMO/电子密度等值面 |
| AI 助手 | 支持本地 LLM（内置 llama.cpp）或远程 OpenAI 兼容 API，自动解读结果、诊断失败原因 |
| 结果导出 | 导出 JSON / CSV / IR / UV-Vis 数据 |
| 多语言 | 中文 / English / Deutsch / 日本語 |
| 主题与字号 | 深色 / 浅色主题，4 档字号缩放 |

---

## 系统要求

ClearQC 目前只支持 **Windows 10 / 11（64 位）**。

还需要开启 **WSL 2**（Windows Subsystem for Linux 2）。WSL 2 是 Windows 自带的功能，它让 Windows 能运行 Linux 程序——ClearQC 的计算引擎（PySCF）就运行在这个 Linux 环境里。**你不需要了解 Linux**，整个过程 ClearQC 会自动处理。

### 如何开启 WSL 2？

1. 以**管理员身份**打开 PowerShell（在开始菜单搜索"PowerShell"，右键 → 以管理员身份运行）
2. 输入以下命令并回车：
   ```
   wsl --install
   ```
3. 等待安装完成，**重启电脑**

重启后 WSL 2 就开启了。如果遇到问题，可以参考[微软官方文档](https://learn.microsoft.com/zh-cn/windows/wsl/install)。

### 硬件建议

| 配置项 | 最低 | 建议 |
|--------|------|------|
| 内存 | 4 GB | 8 GB 以上 |
| 磁盘空间 | 600 MB | 1 GB 以上（计算临时文件） |
| CPU | 任意 x64 | 多核更快 |

---

## 下载与安装

前往 [Releases 页面](https://github.com/SigmaAdrich/ClearQC/releases/latest) 下载最新版本。

`.exe` 安装包约 135 MB，**计算引擎已经打包在内**，整个安装与使用过程都不需要联网。

### 安装步骤

1. 下载 `.exe` 安装包
2. 双击运行，可能会出现 Windows 安全提示（"已保护你的电脑"），点击 **更多信息 → 仍要运行** 即可
3. 按照安装向导点击下一步，完成安装
4. 从开始菜单或桌面快捷方式启动 **ClearQC**
5. **首次启动时**，软件会自动导入 WSL 运算环境，这个过程需要约 30–60 秒，请耐心等待
6. 看到主界面后，就可以开始计算了！

---

## 五分钟上手

**第一步：输入分子名称**

在左侧聊天框底部输入框里，输入 `/compute caffeine`（或 `/compute 咖啡因`），按回车。

软件会在内置分子库里找到咖啡因的结构，并在聊天框里显示一张**计算卡片**。

**第二步：选择计算参数**

计算卡片上默认已经选好了推荐的方法和基组（B3LYP / def2-SVP，平衡速度与精度）。如果你想调整，点击 **Adjust** 按钮展开更多选项：

- **方法（Method）**：HF、21 种 DFT 泛函（B3LYP、PBE0、M06-2X、ωB97X-V、CAM-B3LYP 等），或后 HF 方法 MP2 / CCSD / CCSD(T)
- **基组（Basis）**：28 个基组按家族分组（Pople、Dunning、Karlsruhe、pcseg、ECP），默认 def2-SVP
- **任务（Task）**：单点能（SP）/ 几何优化（Opt）/ 频率（Freq）/ 激发态（Excited）
- **溶剂**：如果你想模拟溶液中的情况，在下拉框里选一种溶剂（共 8 种）

第一次用的话，保持默认就好。

**第三步：点击 Compute**

点击绿色的 **Compute** 按钮，计算开始。右侧状态栏会显示计算进度。

小分子（如咖啡因）用默认设置（B3LYP / def2-SVP）大约需要 1–3 分钟。

**第四步：查看结果**

计算完成后，结果卡片会自动出现，显示：

- 总能量（单位：Hartree）
- 是否收敛
- Mulliken 原子电荷
- 计算耗时

右侧面板同步显示三维结构。点击右上角的下拉框，可以切换查看 **HOMO、LUMO、电子密度**等轨道等值面。

**第五步（可选）：让 AI 解读结果**

ClearQC 不内置 AI 模型，需要你自己接一个 OpenAI 兼容的 API。配置好之后，结果卡片底部的 **AI Explain**（解读结果）和 **AI Diagnose**（诊断错误）按钮就能用了。

**配置步骤：**

1. 顶部菜单 **Settings → AI Configuration…**，弹出配置窗口
2. 填入三个字段：

   | 字段 | 说明 | 示例 |
   |---|---|---|
   | **API Base URL** | API 接口地址（不含末尾的 `/chat/completions`） | OpenAI：`https://api.openai.com/v1`<br>DeepSeek：`https://api.deepseek.com/v1`<br>Moonshot：`https://api.moonshot.cn/v1` |
   | **API Key** | 你的密钥，通常以 `sk-` 开头，从对应平台的"API Keys"页面复制 | `sk-xxxxxxxxxxxxx` |
   | **Model** | 模型名，建议挑便宜且速度快的 | `gpt-4o-mini` / `deepseek-chat` / `moonshot-v1-8k` |

3. 点击 **Save**

回到结果卡片，点 **AI Explain** —— AI 会用自然语言告诉你：算出了什么、能量代表什么、电荷分布是否合理、哪里需要注意。如果计算失败了，结果卡片上会出现 **AI Diagnose**，AI 会分析报错原因（最常见是电荷/自旋写错或方法不适用）。

> **没有付费 API？** 几乎所有大模型平台都赠送免费额度（OpenAI 试用、DeepSeek 注册赠金、Moonshot 月度免费额度）。注册后到平台的 API Keys 页面创建一个 key 就能用。

---

## 常见问题

**Q：安装完打开没反应，或者提示找不到 WSL？**

A：请先按照上面的步骤开启 WSL 2，然后重启电脑再试。

**Q：首次启动卡在"正在导入运算环境"很久？**

A：这是正常现象，WSL 导入需要 30–60 秒，甚至更长（取决于你的硬盘速度）。请耐心等待，不要关闭窗口。

**Q：计算失败，提示错误？**

A：常见原因是电荷或自旋设置不对（比如用了阳离子但忘了把电荷改成 +1）。可以点击结果卡片上的 **AI Diagnose** 按钮，让 AI 帮你分析原因。

**Q：支持哪些文件格式？**

A：支持直接拖入 XYZ、PDB、MOL/SDF、Gaussian GJF/COM 格式的结构文件。

**Q：计算速度很慢？**

A：量子化学计算本身就比较耗时。分子越大、基组越大、方法越精确，耗时越长。建议先保持默认（B3LYP / def2-SVP）做单点能（SP）计算，熟悉流程后再换更精确的方法（MP2、CCSD(T)）或更大基组（cc-pVTZ、def2-TZVP）。

**Q：可以在 Mac 或 Linux 上用吗？**

A：目前只支持 Windows 10 / 11。Mac / Linux 版本暂无计划。

---

## 反馈与支持

遇到 Bug、有功能建议，或者想交流量子化学计算的使用经验，可以通过以下任一方式联系：

- **GitHub Issues**：[提交 Bug 或功能建议](https://github.com/SigmaAdrich/ClearQC/issues)
- **邮箱**：540059610@qq.com
- **Discord 服务器**：<https://discord.gg/gNkRV2xkC3>

---

## 许可

© 2025 SigmaAdrich. All rights reserved.