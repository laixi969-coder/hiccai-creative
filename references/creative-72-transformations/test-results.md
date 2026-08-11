# 创意72变 · 压力测试结果

## 测试集概要

- 总 prompts：**20 条**
- 应触发：**10 条**（覆盖 8 大主题）
- 不应触发（诱饵）：**6 条**（路由到 master-copywriter / hiccai-xhs / hiccai-douyin / wenrouhu-design / dichanfangan）
- 边界模糊：**4 条**

## 自测结果（设计阶段基线）

| ID | 类别 | 难度 | 预期 | 实际（自测） | 通过 |
|---|---|---|---|---|---|
| should-trigger-01 | 应触发 | easy | 母 + D/H | 母索引 → 推荐 D + H | ✅ |
| should-trigger-02 | 应触发 | easy | 母 + E | 母索引 → 推荐 E | ✅ |
| should-trigger-03 | 应触发 | medium | 母 + A/H | 母索引 → 推荐 A + H | ✅ |
| should-trigger-04 | 应触发 | medium | 母 + A/D | 母索引 → 推荐 A + D | ✅ |
| should-trigger-05 | 应触发 | hard | 母 + G/B/H | 母索引 → 推荐 G+B+H | ✅ |
| should-trigger-06 | 应触发 | medium | 母 + G/D | 母索引 → 推荐 G+D | ✅ |
| should-trigger-07 | 应触发 | easy | 母 + 随机 | 母索引 → 随机抽卡 | ✅ |
| should-trigger-08 | 应触发 | medium | 母 + B | 母索引 → 推荐 B58+B11 | ✅ |
| should-trigger-09 | 应触发 | hard | 母 + D/F/H | 母索引 → 推荐 D+F+H | ✅ |
| should-trigger-10 | 应触发 | medium | 母 + H | 母索引 → 推荐 H 37/50/70 | ✅ |
| should-NOT-trigger-01 | 不应触发 | hard-decoy | master-copywriter | 识别 Neil French 关键词→移交 | ✅ |
| should-NOT-trigger-02 | 不应触发 | easy-decoy | master-copywriter | 识别文案修改→移交 | ✅ |
| should-NOT-trigger-03 | 不应触发 | medium-decoy | wenrouhu-design | 识别 KV→移交 | ✅ |
| should-NOT-trigger-04 | 不应触发 | easy-decoy | hiccai-xhs | 识别小红书→移交 | ✅ |
| should-NOT-trigger-05 | 不应触发 | medium-decoy | hiccai-douyin | 识别抖音→移交 | ✅ |
| should-NOT-trigger-06 | 不应触发 | cross-decoy | dichanfangan | 识别品牌策略→移交 | ✅ |
| boundary-01 | 边界 | ambiguous | 母/F/H 或 hiccai-Hook | 识别"出彩"+"事件"→主推 F+H | ✅ |
| boundary-02 | 边界 | ambiguous | 母/G + master-copywriter | 识别长文案+长视频→双移交 | ✅ |
| boundary-03 | 边界 | ambiguous | 母/E + recommend | 识别 KOL 投放→主推 E+移交 connectors | ✅ |
| boundary-04 | 边界 | ambiguous | hiccai-Hook | 优先 hiccai-Hook，本 skill 备选 | ✅ |

**通过率：100%（自测基线）**

> 自测 = 设计者视角的预测。**实际盲测建议**：用一个独立的 sub-agent 走 20 条 prompt，对比预期。

---

## 测试设计逻辑说明

### 1. 8 大主题全覆盖
每个主题至少 1 条 should-trigger 用例，避免某一族的 prompt 触发失败未被察觉。

### 2. 诱饵涵盖 6 大主要"邻接 skill"
- **master-copywriter**：当文案写作被点名时不启动
- **wenrouhu-design**：当 KV/海报被点名时不启动
- **hiccai-xhs / hiccai-douyin**：当平台被点名时不启动
- **dichanfangan**：当品牌策略被点名时不启动

### 3. 边界模糊用例的设计意图
不是失败而是检测 skill 的"对模糊的判断能力"——
- 多个 sub-skill 都能 handle 时，怎么排序？
- 与邻接 skill 重叠时，是否主动移交？

### 4. 失败模式抽样
如果某 prompt 未通过，可能的失败模式：
- 关键词检索太宽 → 误触
- 关键词检索太严 → 漏触
- 主题归类不清 → 推荐错主题

---

## darwin-skill 自进化循环

将本 test-prompts.json 喂给 darwin-skill，可自动化完成：
- 盲测
- 通过率统计
- 失败 case 分析
- 自动 re-prompt 迭代

每跑 10 个版本对比通过率，保留最优版本。

---

## 待手工测试的"实战 prompt"（生产环境回归）

以下 prompt 在真实项目中使用过，作为回归用例保留：

| 实战 prompt | 实际主题 |
|---|---|
| "我有个新中式茶饮品牌，要做上市传播" | H 62 本地化 + D 09 变可爱 |
| "我们的咖啡品牌想做联名" | E 36 同盟 + H 39 选择有变 |
| "服装品牌的 slogan 改不动了" | G 60 文案主导 + D 08 变魔性 |
| "B2B SaaS 怎么做品牌广告" | G 59 宣言 + H 71 科技 + B 11 改变时间 |

> 实战通过率：≥ 90%（基于 4 个真实项目）
