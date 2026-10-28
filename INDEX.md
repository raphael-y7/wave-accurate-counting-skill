# Skill 地图 — 精准数浪

一句话说明：这是 12 张能力卡的入口地图——先在能力总表里按意图定位卡，再看依赖关系决定补读哪一张，最后按加载顺序执行；完整规格见 [`bundle/verified.yaml`](./bundle/verified.yaml)。

## 能力总表

| capability_id | slug | 中文标题 | 重要度 | 去向 |
|---|---|---|---|---|
| `cap.wave-accurate-counting-skill.wave-level-parser` | `jingzhun-wave-levels-skill` | 逐级数浪与级别定位 | critical | promoted → 独立 skill |
| `cap.wave-accurate-counting-skill.end-condition-diagnosis` | `jingzhun-end-conditions-skill` | 具备结束条件与确立结束判定 | critical | promoted → 独立 skill |
| `cap.wave-accurate-counting-skill.impulse-top-capture` | `jingzhun-top-capture-skill` | 推动浪顶部捕捉（含延长浪） | high | promoted → 独立 skill |
| `cap.wave-accurate-counting-skill.correction-bottom-capture` | `jingzhun-bottom-capture-skill` | 调整浪底部捕捉（含 c 浪交易） | high | promoted → 独立 skill |
| `cap.wave-accurate-counting-skill.correction-pattern-library` | `jingzhun-correction-patterns` | 调整结构模式库（四模式 + 剪刀/镰刀/双节棍 + 强弱） | high | router → 路由入口 |
| `cap.wave-accurate-counting-skill.complex-correction-wave` | `jingzhun-complex-correction` | 复杂调整与浪中浪 | medium | router → 路由入口 |
| `cap.wave-accurate-counting-skill.triangle-trading` | `jingzhun-triangle-trading` | 三角形识别、方向/幅度与两段式交易 | high | router → 路由入口 |
| `cap.wave-accurate-counting-skill.combination-structure` | `jingzhun-combination-structure` | 组合结构的形成、演变与三种未来 | medium | router → 路由入口 |
| `cap.wave-accurate-counting-skill.trend-position-sizing` | `jingzhun-trend-position-skill` | 顺势四分法与仓位/确定性管理 | critical | promoted → 独立 skill |
| `cap.wave-accurate-counting-skill.multi-timeframe-levels` | `jingzhun-multi-timeframe-skill` | 大小级别一致性与支撑阻力/止损迁移 | high | promoted → 独立 skill |
| `cap.wave-accurate-counting-skill.horizon-extension-strategy` | `jingzhun-horizon-extension` | 中长线/波段/短线策略与延长浪盈利管理 | medium | router → 路由入口 |
| `cap.wave-accurate-counting-skill.trade-plan-builder` | `jingzhun-trade-plan-skill` | 交易计划整合 | critical | promoted → 独立 skill |

- **promoted → 独立 skill**（7 张）：在 pack 模式下各自是一个带 `SKILL.md` 的独立目录，可被 description 直接命中；在 single 模式下仍是入口内部的一张卡。
- **router → 路由入口**（5 张）：pack 模式下只存在于 `wave-accurate-counting-skill-router/references/capabilities/`，由路由表按意图加载。

## 依赖关系（also_read）

下表列出 `bundle/verified.yaml` 中每张卡声明的 `also_read`，即在主卡执行完之后建议补读的卡（方向按 yaml 记录，未做对称展开）：

| 主卡 | 建议补读（also_read） |
|---|---|
| `jingzhun-wave-levels-skill` | `jingzhun-end-conditions-skill`、`jingzhun-correction-patterns`、`jingzhun-multi-timeframe-skill` |
| `jingzhun-end-conditions-skill` | `jingzhun-wave-levels-skill`、`jingzhun-top-capture-skill`、`jingzhun-bottom-capture-skill` |
| `jingzhun-top-capture-skill` | `jingzhun-wave-levels-skill`、`jingzhun-end-conditions-skill`、`jingzhun-trend-position-skill`、`jingzhun-horizon-extension` |
| `jingzhun-bottom-capture-skill` | `jingzhun-wave-levels-skill`、`jingzhun-end-conditions-skill`、`jingzhun-trend-position-skill`、`jingzhun-horizon-extension` |
| `jingzhun-correction-patterns` | `jingzhun-wave-levels-skill`、`jingzhun-complex-correction`、`jingzhun-triangle-trading`、`jingzhun-combination-structure` |
| `jingzhun-complex-correction` | `jingzhun-correction-patterns`、`jingzhun-end-conditions-skill`、`jingzhun-combination-structure` |
| `jingzhun-triangle-trading` | `jingzhun-wave-levels-skill`、`jingzhun-end-conditions-skill`、`jingzhun-correction-patterns`、`jingzhun-combination-structure` |
| `jingzhun-combination-structure` | `jingzhun-wave-levels-skill`、`jingzhun-correction-patterns`、`jingzhun-end-conditions-skill` |
| `jingzhun-trend-position-skill` | `jingzhun-top-capture-skill`、`jingzhun-bottom-capture-skill`、`jingzhun-multi-timeframe-skill`、`jingzhun-trade-plan-skill` |
| `jingzhun-multi-timeframe-skill` | `jingzhun-wave-levels-skill`、`jingzhun-trend-position-skill`、`jingzhun-horizon-extension`、`jingzhun-trade-plan-skill` |
| `jingzhun-horizon-extension` | `jingzhun-top-capture-skill`、`jingzhun-bottom-capture-skill`、`jingzhun-trend-position-skill`、`jingzhun-trade-plan-skill` |
| `jingzhun-trade-plan-skill` | `jingzhun-wave-levels-skill`、`jingzhun-end-conditions-skill`、`jingzhun-trend-position-skill`、`jingzhun-multi-timeframe-skill`、`jingzhun-horizon-extension` |

几条成环的强依赖，实际使用时按这个顺序读：

- **坐标系 → 触发判据 → 买卖点**：`jingzhun-wave-levels-skill` → `jingzhun-end-conditions-skill` → `jingzhun-top-capture-skill` / `jingzhun-bottom-capture-skill`（级别是前置坐标，结束条件是入场判据，顶底捕捉是落点）
- **模式库 → 进阶结构**：`jingzhun-correction-patterns` → `jingzhun-complex-correction` / `jingzhun-triangle-trading` / `jingzhun-combination-structure`（先归四基础模式，再判嵌套与组合）
- **结构 → 仓位 → 周期 → 计划**：`jingzhun-trend-position-skill` ⇄ `jingzhun-multi-timeframe-skill` ⇄ `jingzhun-horizon-extension` → `jingzhun-trade-plan-skill`（仓位与周期互为前提，最后整合成一份可复核的计划）

## 加载顺序

1. **先读入口 `SKILL.md`**：single 模式读 `single/wave-accurate-counting-skill/SKILL.md`，pack 模式读 `pack/wave-accurate-counting-skill-router/SKILL.md`。入口里有「触发与不触发」「核心原则」「能力路由表」「加载规则」几段，概览类问题读到核心原则即可回答，不必加载能力卡。
2. **按路由表加载 1 张卡**：拿用户意图去匹配路由表的「用户意图」列，命中后只加载对应的那一张卡（`references/capabilities/<slug>.md`）。
3. **最多补读 1 张**：任务确实跨域时（例如既判断当前浪级、又要给出该顶部的止损与目标），按上表的 `also_read` 再加载 1 张，总数不超过 2 张。
4. **非能力类查询走索引**：书名/作者/章节/整书概览 → `references/overview.md`；术语 → `references/glossary.md`；决策规则速查 → `references/cheatsheet.md`；路由表未覆盖的意图 → `references/capability-index.md`。
5. **判停**：路由表与索引都无法命中的意图，明确告知超出本书范围；同一段走势存在多种等价分解且无法用关键点突破收敛时，停止下结论并标「未确认」，不强行给出买卖点。
