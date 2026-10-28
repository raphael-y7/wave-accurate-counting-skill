<h1 align="center">精准数浪 Skill</h1>

<p align="center">中文 | <a href="README.en.md">English</a></p>

一套可直接使用的 AI skill 工具包——把陈晓东《精准数浪——波浪理论内部结构分析及买卖点位把握》中的内部结构数浪方法，蒸馏成 12 张可单独触发、也可组合调用的能力卡。

它不是原书摘要，也不是读后感，而是把书中可复用的方法论拆成可触发、可执行、可测试的 skill 模块。

## 这套 skills 能解决什么问题

- 数浪只能数出"1、2、3、4、5"的编号，却说不清当前这一浪属于哪一级——而级别是全部买卖点、止损与目标的前置坐标，级别错了后面全跟着错
- 抄底逃顶时只知道"跌了很多 / 涨了很多"，分不清"具备结束条件"（可以结束，只可试单）和"确立结束"（已经结束，才可加仓），于是该试单时重仓、该加仓时反而不敢动
- 调整浪走了三浪又说没完，b 浪一次次再分解，不知道按剪刀式、镰刀式还是双节棍式处理，也说不清关键点在哪
- 止损凭感觉放百分比，而不是放在所交易浪的极值外 1～2 个点，结果一根毛刺就被扫掉
- 日线看多、周线看空，不知道听谁的；结构一变，支撑阻力、止损和仓位没有同步迁移
- 看对了方向却亏钱：仓位大小与结构确定性不匹配，止损空间已经大于目标空间还在硬做

## 蒸馏了什么

12 张能力卡，按"先定级别、再判结束、然后下手、最后算账"的顺序组织：

- **坐标系**：`jingzhun-wave-levels-skill`（逐级数浪与级别定位：九级浪级、五浪走完升一级、1/3/5 在次一级各为完整五浪）
- **触发判据**：`jingzhun-end-conditions-skill`（具备结束条件与确立结束判定，含结束点下移）
- **买卖点捕捉**：`jingzhun-top-capture-skill`（推动浪顶部捕捉，含延长浪）、`jingzhun-bottom-capture-skill`（调整浪底部捕捉，含 c 浪交易）
- **模式库**：`jingzhun-correction-patterns`（调整结构模式库：四基础模式 + 剪刀/镰刀/双节棍 + 强弱）、`jingzhun-complex-correction`（复杂调整与浪中浪）、`jingzhun-triangle-trading`（三角形识别、方向/幅度与两段式交易）、`jingzhun-combination-structure`（组合结构的形成、演变与三种未来）
- **风控与策略**：`jingzhun-trend-position-skill`（顺势四分法与仓位/确定性管理）、`jingzhun-multi-timeframe-skill`（大小级别一致性与支撑阻力/止损迁移）、`jingzhun-horizon-extension`（中长线/波段/短线策略与延长浪盈利管理）
- **整合**：`jingzhun-trade-plan-skill`（交易计划整合：浪级→结构→势→入场→止损→目标→仓位→失效八步）

## 两种打包模式：single 与 pack

同一套 12 张能力卡，按两种粒度各编译了一次。两者内容完全相同，区别只在"agent 能看到几个入口"。

| | single（单一入口） | pack（compact pack，多入口） |
|---|---|---|
| 可发现入口 | **1 个**：`wave-accurate-counting-skill` | **8 个**：1 个来源路由入口 + 7 个已晋级独立 skill |
| 12 张能力卡放在哪 | 全部在入口的 `references/capabilities/` 里，由入口按路由表按需加载 1–2 张 | 7 张高频卡各自独立成 skill；其余 5 张仍在 router 的 `references/capabilities/` 里 |
| 触发方式 | 只有入口的 description 参与匹配，进入后靠路由表分流 | 7 个高频能力可被 description 直接命中，少一跳 |
| 升级维护 | 替换 1 个目录 | 替换 8 个目录 |

pack 里被晋级为独立 skill 的 7 张卡：

- `jingzhun-wave-levels-skill` — 逐级数浪与级别定位
- `jingzhun-end-conditions-skill` — 具备结束条件与确立结束判定
- `jingzhun-top-capture-skill` — 推动浪顶部捕捉（含延长浪）
- `jingzhun-bottom-capture-skill` — 调整浪底部捕捉（含 c 浪交易）
- `jingzhun-trend-position-skill` — 顺势四分法与仓位/确定性管理
- `jingzhun-multi-timeframe-skill` — 大小级别一致性与支撑阻力/止损迁移
- `jingzhun-trade-plan-skill` — 交易计划整合

留在 router 里的 5 张卡：`jingzhun-correction-patterns`、`jingzhun-complex-correction`、`jingzhun-triangle-trading`、`jingzhun-combination-structure`、`jingzhun-horizon-extension`。

### 该装哪一种

按你的工作方式选，**只装一种**：

| 你的工作方式 | 推荐 | 原因 |
|---|---|---|
| 用 DSH / Codex / Claude Code 等有 skills 目录，希望列表干净 | single | 只占 1 个入口，能力一张不少 |
| 日常问题高度集中在"数浪 / 这段走完没有 / 哪里逃顶 / 哪里抄底 / 仓位多重" | pack | 这 7 类正是被晋级的独立 skill，能直接命中 |
| 要分发给多个 agent 或团队，各自按需取用 | pack | 可以只装其中几个独立 skill，不必整包 |
| 只想装一次、不想维护多个目录 | single | 升级时只替换 1 个目录 |

> 两版由同一个 Bundle 编译，能力内容一致。**同时安装会重复触发**，请只装一种。

## 效果示例

### 示例 1：6124 这个顶，止损和目标怎么放

**用户问题**

"上证 6124 那个顶，现在回头看是明确的顶，当时怎么判断它已经走完？止损和目标放哪？"

**skill 如何判断**

- 先进 `jingzhun-wave-levels-skill`：确认这个顶属于哪一级推动浪，并从该级起点往下逐级拆，看 1、3、5 在次一级是否各为完整五浪
- 进 `jingzhun-top-capture-skill`：把推动浪顶部逐级锁到最小浪级的最后一浪，在最小级别的结束条件处出局或做空；止损放高点外 1～2 个点；目标为下一级调整的结束
- 补 `jingzhun-end-conditions-skill`：区分"具备结束条件"（只可减仓/试空）与"确立结束"（才可加仓）
- 若同级推动浪继续上破前高，则按延长浪处理，顶部上移

**最终回答示例**

> 先说结论：6124 是"具备结束条件"被事后确认成"确立结束"，当时只能按前者动手。做法是把这段上涨逐级拆到最小级别，看最后一浪在最小级别上是否走完五浪——走完了就在最小级别的结束条件处减仓或试空，止损放在该高点外 1～2 个点，目标指向下一级调整的结束位置，而不是去猜一个固定跌幅。
>
> 这里有一处书中自带的冲突要说明：原案例同时给出"6124 上方 0～100 点区域"和"止损 6126"。如果你真的在 6126 以上入场，止损就落在入场价下方了，这在逻辑上不成立。所以实际操作只有两种收法：要么把入场区收窄到 6124～6126，要么放弃点位止损、改用结构止损（即该级别结构被破坏的位置）。这个冲突在能力卡的 B 段（边界与盲点）里写明了，不是漏掉的细节。
>
> 还有一点必须标清楚：这是事后复盘，当时的"确立结束"要等后续结构走完才能确认。实时当下你只能得到"具备结束条件"，对应动作是轻仓试单而不是重仓逃顶。

### 示例 2：跌到前低附近，能不能先轻仓

**用户问题**

"这波调整的 c 浪好像还没走完，但价格已经跌到前低附近了，能不能先轻仓抄一点？"

**skill 如何判断**

- 进 `jingzhun-bottom-capture-skill`：先由调整级别推出内部三浪，再把底部逐级缩到 c 浪的微浪(c) / 亚微浪 c，在最小 c 浪"具备结束条件"时先试单、"确立结束"时再加仓
- 进 `jingzhun-end-conditions-skill`：用 a0 上破 c 浪高点、上破 a 浪起点、后市本应结构验证，三选二才算确立结束；未确认则结束点下移
- 若 b 浪再分解，底部要下移到 c3，前低不是终点
- 最后 `jingzhun-trend-position-skill`：止损放 c 浪低点下 1～2 点，止损空间大于目标空间就不做

**最终回答示例**

> 可以试，但要先接受"这不是抄底，是试单"。理由：c 浪还没确立结束，现在只可能满足"具备结束条件"，按书里的分工，这个位置只配轻仓，加仓要等确立。
>
> 具体三步：第一，确认调整级别，推出内部应该是几浪；第二，把底部逐级缩到 c 浪的最小级别，看最小 c 浪有没有走完；第三，止损放 c 浪低点下 1～2 个点，目标指向下一推动浪的结束。
>
> 最关键的失效条件先讲：如果 b 浪继续再分解，底部会下移到 c3，你现在抄的"前低"就不是底。所以要么等 a0 上破 c 浪高点或 a 浪起点（三选二）再加仓，要么就守住 c 浪低点下 1～2 点这个止损。止损空间如果已经大于能看到的上涨空间，这笔就别做——这也是书里"止损空间大于目标空间则不做"的原话。

## 这些 skill 是怎么生成出来的

这套 skill 使用 **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** 的 RIA-TV++ 流水线生成，整个流程分六个阶段：

1. **整书理解（Adler 分析）**——用 Mortimer Adler 的分析阅读法，对全书做结构、解释、批判、应用四步拆解
2. **并行提取**——同时派多个专项提取器（框架、原则、案例、反例、术语），从原文中提取候选方法论单元
3. **三重验证筛选**——每个候选必须通过三项检验：书内至少有 2 处独立佐证（跨域）、能回答书中未明说的新问题（预测力）、不是常识（独特性）
4. **RIA++ 构造**——按 R（原文引用）/ I（用自己的话重写）/ A1（书中案例）/ A2（未来触发场景）/ E（可执行步骤）/ B（边界与盲点）六个维度结构化
5. **Zettelkasten 链接**——找出能力卡之间的依赖、对比、组合关系，生成能力索引与路由表
6. **触发与输出测试**——为每张卡设计触发盲测题（含诱饵题：该触发时要触发，不该触发时要沉默）与输出评测场景，未通过的卡回炉重做，回炉后再做回归验证

本书的蒸馏难点在"级别"这一层：书里所有买卖点、止损、目标都挂在浪级上，所以第一张卡（逐级数浪）必须是全体系的前置坐标，其余 11 张卡都以它为输入；这也决定了 `also_read` 里几乎每张卡都要回读它。

## 测试与验证

本仓库连生成过程的测试材料一起发布：`evals/test-prompts.json` 是 51 条触发与边界用例，`evals/test-results.md` 是逐项评分结果——包含失败与回炉修复的完整过程，不是只留通过记录。

- **触发盲测**：51 条（should_trigger 25 / should_not_trigger 18 / edge_case 8），首轮 48 / 51，3 条因 description 边界重叠误选（如"6124 附近怎么设止损"被交易计划吸走），修订 description 后重测 3 / 3，最终 51 / 51
- **诱饵容错**：18 条 should_not_trigger 全部未误触发被测入口
- **执行测试**：12 个能力 × 正常 / 边界 = 24 项，正常 12 / 12 完成且字段齐全，边界 12 / 12 全部给出"不能 / 降级 / 未确认 / 回避"的明确处理，没有强行给出确定性结论
- **测试发现的遗留问题**：4 条进入 needs-review——顶部区域与止损位置冲突、止损距离与仓位缺少量化映射、股票与杠杆品种的仓位基数口径、数据不足时的降级规则
- **未做的验证**：跨模型复测、样本外统计检验、真实资金回测；这些不作为"已证明有效"的依据

## 仓库结构

```text
wave-accurate-counting-skill/
├── README.md                      ← 你正在看的
├── README.en.md                   ← English version
├── LICENSE                        ← MIT
├── INDEX.md                       ← skill 地图：能力总表 + 依赖关系 + 加载顺序
├── BOOK_OVERVIEW.md               ← 整书理解（Adler 四步拆解，阶段 0 产出）
├── verified.md                    ← 12 个规范单元的三重验证结论
├── bundle/                        ← 审计用原始 Bundle，可复核 verified.yaml 与能力卡原文
│   ├── verified.yaml              ← 12 张能力卡的规范定义与 promoted / router 去向
│   ├── cards/
│   │   ├── jingzhun-bottom-capture-skill.md
│   │   ├── jingzhun-combination-structure-skill.md
│   │   ├── jingzhun-complex-correction-skill.md
│   │   ├── jingzhun-correction-patterns-skill.md
│   │   ├── jingzhun-end-conditions-skill.md
│   │   ├── jingzhun-horizon-extension-skill.md
│   │   ├── jingzhun-multi-timeframe-skill.md
│   │   ├── jingzhun-top-capture-skill.md
│   │   ├── jingzhun-trade-plan-skill.md
│   │   ├── jingzhun-trend-position-skill.md
│   │   ├── jingzhun-triangle-trading-skill.md
│   │   └── jingzhun-wave-levels-skill.md
│   └── book/
│       ├── glossary.md            ← 术语表
│       └── overview.md            ← 整书概览
├── single/                        ← 单一入口模式
│   └── wave-accurate-counting-skill/
│       ├── BUILD_MANIFEST.json    ← 编译清单与文件哈希
│       ├── SKILL.md               ← 入口：触发条件 + 路由表 + 加载规则
│       └── references/
│           ├── capability-index.md  ← 完整意图与关键词索引
│           ├── cheatsheet.md      ← 决策规则速查
│           ├── glossary.md        ← 术语表
│           ├── overview.md        ← 整书概览
│           └── capabilities/
│               ├── jingzhun-bottom-capture-skill.md
│               ├── jingzhun-combination-structure.md
│               ├── jingzhun-complex-correction.md
│               ├── jingzhun-correction-patterns.md
│               ├── jingzhun-end-conditions-skill.md
│               ├── jingzhun-horizon-extension.md
│               ├── jingzhun-multi-timeframe-skill.md
│               ├── jingzhun-top-capture-skill.md
│               ├── jingzhun-trade-plan-skill.md
│               ├── jingzhun-trend-position-skill.md
│               ├── jingzhun-triangle-trading.md
│               └── jingzhun-wave-levels-skill.md
├── pack/                          ← 多入口模式（compact pack）
│   ├── BUILD_MANIFEST.json
│   ├── capability-destinations.json
│   ├── jingzhun-bottom-capture-skill/
│   │   └── SKILL.md
│   ├── jingzhun-end-conditions-skill/
│   │   └── SKILL.md
│   ├── jingzhun-multi-timeframe-skill/
│   │   └── SKILL.md
│   ├── jingzhun-top-capture-skill/
│   │   └── SKILL.md
│   ├── jingzhun-trade-plan-skill/
│   │   └── SKILL.md
│   ├── jingzhun-trend-position-skill/
│   │   └── SKILL.md
│   ├── jingzhun-wave-levels-skill/
│   │   └── SKILL.md
│   └── wave-accurate-counting-skill-router/
│       ├── SKILL.md               ← 来源路由入口
│       └── references/
│           ├── capability-index.md
│           ├── cheatsheet.md
│           ├── glossary.md
│           ├── overview.md
│           └── capabilities/
│               ├── jingzhun-bottom-capture-skill.md
│               ├── jingzhun-combination-structure.md
│               ├── jingzhun-complex-correction.md
│               ├── jingzhun-correction-patterns.md
│               ├── jingzhun-end-conditions-skill.md
│               ├── jingzhun-horizon-extension.md
│               ├── jingzhun-multi-timeframe-skill.md
│               ├── jingzhun-top-capture-skill.md
│               ├── jingzhun-trade-plan-skill.md
│               ├── jingzhun-trend-position-skill.md
│               ├── jingzhun-triangle-trading.md
│               └── jingzhun-wave-levels-skill.md
└── evals/                         ← 触发与输出测试材料
    ├── test-prompts.json          ← 51 条触发 / 近邻 / 边界用例
    └── test-results.md            ← 逐项评分与回炉修复记录
```

## 如何使用

先把仓库克隆下来：

```bash
git clone https://github.com/raphael-y7/wave-accurate-counting-skill.git
```

### 装 single（推荐先试这个）

```bash
# macOS / Linux
cp -r wave-accurate-counting-skill/single/wave-accurate-counting-skill ~/.agents/skills/
```

```powershell
# Windows
Copy-Item -Recurse .\wave-accurate-counting-skill\single\wave-accurate-counting-skill "$env:USERPROFILE\.agents\skills\"
```

### 装 pack

只复制含 `SKILL.md` 的目录，不要把 `pack/` 下的两个 json 一起拷进 skills 目录：

```bash
# macOS / Linux
cd wave-accurate-counting-skill/pack
cp -r wave-accurate-counting-skill-router \
      jingzhun-wave-levels-skill \
      jingzhun-end-conditions-skill \
      jingzhun-top-capture-skill \
      jingzhun-bottom-capture-skill \
      jingzhun-trend-position-skill \
      jingzhun-multi-timeframe-skill \
      jingzhun-trade-plan-skill ~/.agents/skills/
```

```powershell
# Windows
$pack = ".\wave-accurate-counting-skill\pack"
$dest = "$env:USERPROFILE\.agents\skills"
@('wave-accurate-counting-skill-router','jingzhun-wave-levels-skill','jingzhun-end-conditions-skill','jingzhun-top-capture-skill','jingzhun-bottom-capture-skill','jingzhun-trend-position-skill','jingzhun-multi-timeframe-skill','jingzhun-trade-plan-skill') |
  ForEach-Object { Copy-Item -Recurse -LiteralPath (Join-Path $pack $_) -Destination $dest }
```

> `~/.agents/skills` 是 DSH 的 skill 目录；用别的 agent 时换成它自己的 skills 目录即可（例如 Claude Code 是 `~/.claude/skills`）。

### 怎么确认装好了

装完问一句"这波调整的 c 浪走完没有，能不能先轻仓，止损放哪"，看 agent 是否直接进入 `jingzhun-end-conditions-skill` 与 `jingzhun-bottom-capture-skill` 的判定流程（区分具备结束条件与确立结束、止损放 c 浪低点下 1～2 点），而不是给你一段泛泛的"注意风险"。装的是 single 时，它会先读入口再按路由表进能力卡；装的是 pack 时，对应能力会被直接命中。

## 来源

- 《精准数浪——波浪理论内部结构分析及买卖点位把握》陈晓东 著

## 声明

本仓库只发布蒸馏后的 skill、索引与规则速查材料，不包含原书 PDF、逐页图像（PNG）或全书转写稿。能力卡中出现的原文引用仅用于标注方法论出处和保持可审计性。

书中所有点位与数字判据（浪级符号、止损外扩 1～2 点、仓位档位、6124 / 4778 / 2319 / 2566～2952 等案例数值）都是案例与经验归纳，原书未提供统计回测背书，使用时需按标的自行测试并声明所用口径。本仓库内容不构成投资建议。

## License

[MIT](./LICENSE)
