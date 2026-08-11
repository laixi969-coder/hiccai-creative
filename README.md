# hiccai-creative — 创意与新媒体全案操盘手

> 一个把「72 张创意卡 × 三本创意经典 × 六种交付模式」炼成一体的 AI Skill。
> 输入品牌/产品/现象 → 输出可直接使用的创意成品（方向、文案、标题、脚本、提案、装置方案）。

[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Standard-blue)](https://github.com/alchaincyf/agent-skills-standard)
[![Multi-Runtime](https://img.shields.io/badge/Multi-Runtime-ready-green)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 这是什么

`hiccai-creative` 是创意与新媒体全案操盘手，融合五大能力于一体：

- **首席提案官** — 输出可直接复制粘贴的完整品牌提案（≥50 页分页文案）
- **小红书操盘手** — 爆款标题批量生产 + 内容增长全案
- **顶级创意总监** — 输出有裂变基因的品牌故事创意，执行 Big Idea 评估
- **洞察转创意引擎** — 把现象洞察转化为可拍的创意表达
- **广告全案协作者** — 策略定位→创意方向→文案→AI图像Prompt 一体化

**它的独特之处**：不只是一个 prompt 模板，而是把 **4 套方法资产**（72 张创意卡牌 + 3 本创意经典）内置进工作流，让每个模式都有方法论背书，产出有质量下限。

---

## 快速开始

### 方式一：作为 Skill 安装（推荐）

1. clone 仓库到你的 skills 目录：

```bash
git clone https://github.com/laixi969-coder/hiccai-creative.git \
  ~/.workbuddy/skills/hiccai-creative
# 或其他 runtime 的 skills 目录（.claude/skills、.cursor/skills 等）
```

2. 对话中直接说需求，自动触发：

```
「帮我写 30 条小红书爆款标题，主题是成都的宠物友好咖啡馆」
「我们是一个高端矿泉水品牌，想做年轻化传播，帮我出创意」
「帮我做一个新中式茶饮品牌的完整提案」
「理想 L9 的夏季战役，给几个创意方向」
```

### 方式二：作为方法库阅读

即使不安装，`references/` 下的内容也是完整的创意方法论参考书（72 张卡牌 + 三本经典拆解），可直接阅读。

---

## 六大模式（自动识别，无需手动选）

| 模式 | 适用 | 第一步交付物 |
|---|---|---|
| **提案模式** | 品牌全案、甲方汇报 PPT | ≥50 页分页提案文案（单页≤50 字） |
| **小红书全案模式** | 完整小红书增长方案 | 趋势→IP→玩法→三阶段节奏 + 笔记 Demo |
| **标题工厂模式** | 批量爆款标题 | 30 条标题（6 类×5 条，附评分） |
| **创意故事模式** | 品牌故事方向 / 传播创意 | 3 个不同族 × 不同载体的创意方向 |
| **洞察转创意模式** | 现象/洞察→创意内容 | 一句话创意 + 画面 + 标题 + 15s 脚本 + 钩子 |
| **广告全案模式** | 策略→创意→文案→视觉全案 | 四步走全案（策略/方向/文案/Prompt） |

**模糊请求兜底**：只说品牌名没说要什么（如「理想 L9」）→ 默认创意故事模式第一步，先给 3 个方向让用户选。

---

## 方法资产（全部内置，clone 即得）

本 skill 把 4 套创意方法资产编织进六模式工作流，形成完整闭环：

```
72变 出方向 → Young 生成 Big Idea → Gladwell 设计传播 → Heath 检验黏性
```

| 资产 | 来源 | 核心能力 | 位置 |
|---|---|---|---|
| **《创意72变》卡牌** | 实体卡牌数字化 | 72 个「变 X」方向，8 大主题，选族选卡产方向 | `references/creative-72-transformations/` |
| **《创意的生成》5 步流程** | James Webb Young (1940) | 吸收→咀嚼→孵化→产出→检验 + 「旧元素新组合」组合机 | `references/creative-methods/young-five-steps/` |
| **《引爆点》三法则** | Malcolm Gladwell (2000) | 个别人物 + 附着力 + 环境威力 | `references/creative-methods/gladwell-tipping/` |
| **《让创意更有黏性》SUCCESs** | Chip & Dan Heath (2007) | Simple/Unexpected/Concrete/Credible/Emotional/Stories | `references/creative-methods/heath-stickiness/` |

### 创意72变 · 8 大主题速览

| 族 | 主题 | 覆盖卡号 | 典型卡 |
|---|---|---|---|
| A | 形性重构 | 01-04, 27-28 | 变小、变大、变形、物成人 |
| B | 时空错位 | 10-11, 21, 58 | 变个地方、改变时间、变倒退 |
| C | 视角重置 | 22, 25, 54, 56, 66 | 第一人称、变分屏、有形于无形 |
| D | 性格置换 | 05-09, 57 | 变勇、变可爱、变魔性、唯情不变 |
| E | IP 与关系 | 13-17, 36, 42, 64 | 变同盟、变代言、变 IP |
| F | 参与互动 | 17-20, 29, 31, 44-45 | 变游戏、变实验、装置艺术 |
| G | 叙事语义 | 23-24, 32-35, 49-52, 59, 67-68 | 变反转、变夸张、变宣言 |
| H | 前瞻杠杆 | 30, 37-41, 43, 46-48, 50, 53, 60-63, 65, 69-72 | 变本地化、变节日、随科技变 |

---

## 核心设计原则

### 1. 交付总纲（最高优先级）

> **用户要的是「能直接用的成品」，不是「关于成品的分析」。**

- 交付物 = 成品（文案/标题/方向/脚本/提案/钩子）
- 第一步只交「该模式的第一层产物」，用户确认后再展开
- 分析工具（门槛/方法论/检验）只做内部步骤，不进交付正文

### 2. 双重多样性（防路径依赖）

每个创意任务强制产出 ≥3 个方向，且满足：
- **族不同**：来自不同主题（A/B/C/D/E/F/G/H）
- **载体不同**：至少 2 个不是视频（视频/装置/H5/联名/事件/海报/音乐/UGC/产品/游戏）

防止「换个品牌名，创意永远一个样」的路径依赖。

### 3. 三条硬门槛（质量下限）

任何成品输出前必须通过：
- **门槛一 洞察标准**：命名老现象，可拍，反推测试
- **门槛二 文案质感**：语义通顺、硬事实拦截、禁用词替换
- **门槛三 小红书质感**：七愿意闸门、去 AI 味、降权信号拦截

---

## 目录结构

```
hiccai-creative/
├── SKILL.md                        # 主文件：六模式 + 交付总纲 + 方法资产总表
├── README.md                       # 本文件
├── test-prompts.json               # 主 skill 测试集（darwin-skill 兼容）
└── references/
    ├── creative-72-transformations/   # ★《创意72变》72张卡·8族
    │   ├── SKILL.md                  # 母索引：选族 + 路由 + 双重多样性
    │   ├── cards.md                  # 72 张卡完整清单
    │   ├── GLOSSARY.md               # 共享术语词典
    │   ├── INDEX.md                  # 引用图
    │   ├── DIGEST.md                 # 精华长文
    │   ├── test-prompts.json / test-results.md
    │   └── themes/                   # 8 大主题 sub-skill
    │       ├── a-shape/  b-spacetime/  c-perspective/  d-character/
    │       └── e-ip-relate/  f-engage/  g-narrate/  h-leverage/
    └── creative-methods/              # 三本创意经典方法论
        ├── young-five-steps/          # 《创意的生成》5步流程+组合机
        ├── gladwell-tipping/          # 《引爆点》三法则
        └── heath-stickiness/          # 《让创意更有黏性》SUCCESs
```

---

## 触发词

`hiccai-creative`、品牌提案、创意方案、小红书方案、爆款标题、创意故事、洞察、传播脚本、新媒体全案、内容策略、裂变创意、广告全案、策略定位、Big Idea、AI图像prompt、brand pitch、creative strategy

---

## 版本历史

| 版本 | 日期 | 内容 |
|---|---|---|
| **v2.5.0** | 2026-08-10 | 全量重构：方法资产总表 + 六模式全部绑定方法资产，形成「出方向→生成→传播→黏性」闭环 |
| v2.4.1 | 2026-08-10 | 《创意72变》全套并入仓库，自包含全部方法资产 |
| v2.4.0 | 2026-08-10 | 第一性原理修复：交付总纲、模糊请求兜底、5 模式交付物定义 |
| v2.3.0 | 2026-08-10 | 接入 references/creative-methods/ 三本创意经典 |
| v2.2.0 | 2026-07-06 | 基线版本 |

---

## 相关项目

- **darwin-skill** — 本 skill 的自动进化器（9 维 rubric 评估 + 盲测优化）
- **master-copywriter** — 文案大师工坊（Neil French / 许舜英 / 李欣频）
- **hiccai-wenan / hiccai-xhs** — 文案质感与小红书质感标准的来源

---

## License

MIT

_蒸馏与维护：Caiwenbin · 2026_
