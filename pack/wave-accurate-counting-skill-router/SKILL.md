---
name: wave-accurate-counting-skill-router
description: |
  《精准数浪》来源路由入口：收录逐级数浪、结束条件、顶底捕捉、调整模式库、复杂浪中浪、三角形、组合结构、顺势仓位、多周期一致性、延长浪、交易计划等12张能力卡。
  触发：用户提到陈晓东、精准数浪、内部结构数浪、剪刀式/镰刀式/双节棍式、浪中浪、三角形买卖点、组合结构、延长浪、支撑阻力迁移等“模式识别/进阶结构”问题，先由本入口分派到对应能力卡。
  不适用：明确要求单一动作（如只数浪、只判结束、只做计划）时，优先直接调用对应的晋级 Skill，避免路由层重复触发。
metadata:
  cangjie.generated-by: cangjie-tools v2.5.0
  cangjie.variant: router
  cangjie.bundle-id: bundle.wave-accurate-counting-skill
  cangjie.capability-count: 12
  cangjie.entrypoint-count: 8
---
# 精准数浪——波浪理论内部结构分析及买卖点位把握 — 来源路由入口（compact pack）

## 触发与不触发

**适用**：与本书能力域相关的咨询与任务（见下方路由表的意图列）。
**不适用**：
- 不含基本面、消息面、资金流、行业与估值分析。
- 不预测无结构的随机波动，不提供收益保证。
- 不替代用户的下单决策与风险承受判断。
- 不适用于缺乏K线数据或流动性极差的品种。

## 核心原则（常驻速览，概览类问题读到这里即可回答）

1. 先级别后结构，先大级别后小级别；级别错则买卖点、止损、目标全错。
2. 具备结束条件≠确立结束：前者只可试单，后者才加仓。
3. 买卖点在结构结束临界点；技术止损放所交易浪极值外1～2点。
4. 目标位是下一级结构的结束条件，不用固定盈亏比猜目标。
5. 结构确定性决定仓位；确定性不足只轻仓、试单或回避。
6. 调整结构会演变，必须用关键点突破逐一排除替代分解。
7. 小级别服从大级别；结构变则支撑阻力、止损与仓位同步迁移。

## 能力路由（先读本表，按意图加载 1 张能力卡）

| 用户意图 | 先读 | 补读/备注 |
|---|---|---|
| 判断当前浪级；数浪；区分推动浪与锯齿；判断基础浪与细分浪 | references/capabilities/jingzhun-wave-levels-skill.md | 已晋级为独立 Skill `jingzhun-wave-levels-skill`（已安装时优先直接使用；本卡仅作原文与背景补充） |
| 判断调整是否结束；判断某段走完没有；区分具备结束条件与确立结束；判断结束点是否下移 | references/capabilities/jingzhun-end-conditions-skill.md | 已晋级为独立 Skill `jingzhun-end-conditions-skill`（已安装时优先直接使用；本卡仅作原文与背景补充） |
| 找推动浪顶部；判断哪里逃顶；判断五浪是否走完；判断是不是延长浪；给出顶部区域的止损与目标；处理延长浪 | references/capabilities/jingzhun-top-capture-skill.md | 已晋级为独立 Skill `jingzhun-top-capture-skill`（已安装时优先直接使用；本卡仅作原文与背景补充） |
| 找调整浪底部；判断能否抄底；判断 c 浪是否结束；跌到前低附近能否先轻仓；处理 b 浪再分解 | references/capabilities/jingzhun-bottom-capture-skill.md | 已晋级为独立 Skill `jingzhun-bottom-capture-skill`（已安装时优先直接使用；本卡仅作原文与背景补充） |
| 识别调整结构；区分剪刀式镰刀式双节棍式；判断调整强弱；找调整结构关键点 | references/capabilities/jingzhun-correction-patterns.md | references/capabilities/jingzhun-wave-levels-skill.md、references/capabilities/jingzhun-complex-correction.md、references/capabilities/jingzhun-triangle-trading.md、references/capabilities/jingzhun-combination-structure.md |
| 识别浪中浪；判断双复杂结构；找双关键点共振；处理三组三浪 | references/capabilities/jingzhun-complex-correction.md | references/capabilities/jingzhun-correction-patterns.md、references/capabilities/jingzhun-end-conditions-skill.md、references/capabilities/jingzhun-combination-structure.md |
| 判断三角形突破方向；三角形怎么交易；三角形目标位；识别引导/终结倾斜三角形 | references/capabilities/jingzhun-triangle-trading.md | references/capabilities/jingzhun-wave-levels-skill.md、references/capabilities/jingzhun-end-conditions-skill.md、references/capabilities/jingzhun-correction-patterns.md、references/capabilities/jingzhun-combination-structure.md |
| 识别组合结构；判断横盘蓄势；处理组合结构移位；判断组合结束后的三种未来 | references/capabilities/jingzhun-combination-structure.md | references/capabilities/jingzhun-wave-levels-skill.md、references/capabilities/jingzhun-correction-patterns.md、references/capabilities/jingzhun-end-conditions-skill.md |
| 判断该重仓还是轻仓；判断能否加仓；判断顺哪种势；评估确定性 | references/capabilities/jingzhun-trend-position-skill.md | 已晋级为独立 Skill `jingzhun-trend-position-skill`（已安装时优先直接使用；本卡仅作原文与背景补充） |
| 处理日线周线冲突；找支撑阻力；判断止损是否随结构移动；判断小级别突破能否追 | references/capabilities/jingzhun-multi-timeframe-skill.md | 已晋级为独立 Skill `jingzhun-multi-timeframe-skill`（已安装时优先直接使用；本卡仅作原文与背景补充） |
| 选择中长线还是短线；处理延长浪；设置保底与延长目标；结构失败反手 | references/capabilities/jingzhun-horizon-extension.md | references/capabilities/jingzhun-top-capture-skill.md、references/capabilities/jingzhun-bottom-capture-skill.md、references/capabilities/jingzhun-trend-position-skill.md、references/capabilities/jingzhun-trade-plan-skill.md |
| 生成交易计划；制定买卖策略；计算止损目标仓位；复盘交易计划 | references/capabilities/jingzhun-trade-plan-skill.md | 已晋级为独立 Skill `jingzhun-trade-plan-skill`（已安装时优先直接使用；本卡仅作原文与背景补充） |

**非能力类查询**：
- 书名/作者/章节/整书概览 → references/overview.md
- 术语解释 → references/glossary.md
- 决策规则速查（不需要原文依据时） → references/cheatsheet.md
- 完整意图与关键词索引（本表未覆盖的意图先查这里） → references/capability-index.md

## 加载规则

- 每次任务先读本文件，再按路由表加载 **1** 张能力卡；任务明确跨域时最多加载 2 张。
- 概览/书名类问题不加载能力卡，用「核心原则」与 overview.md 回答。
- 路由表与 capability-index.md 都无法命中的意图，明确告知超出本书范围，不要硬套。

## 边界与判停

- 关键点被突破且结构必须重标，原交易计划失效。
- 数据不足，无法完成次一级结构细分，级别判定只能标“未确认”。
- 找不到技术止损，或技术止损空间大于可预见目标空间。
- 同一段走势存在多种等价分解，且无法用关键点突破收敛。
