<h1 align="center">精准数浪 Skill</h1>

<p align="center">中文 | <a href="README.en.md">English</a></p>

一套可直接使用的 AI skill 工具包——把陈晓东《精准数浪》中的波浪理论内部结构分析方法，蒸馏成 12 张可单独触发、也可组合调用的能力卡：先定浪级与结构，再判"具备结束条件/确立结束"，在推动浪顶部或调整浪底部用极值外 1～2 点的技术止损入场，目标指向下一级结构的结束点，并按结构确定性配仓位。

它不是原书摘要，也不是读后感，而是把书中可复用的方法论拆成可触发、可执行、可测试的 skill 模块。

## 这套 skills 能解决什么问题

- 看得见"五浪上涨"，却说不清这是哪一级的五浪、1/3/5 能不能再拆、当前是推动浪还是锯齿反弹——级别一错，后面的方向、目标、止损、仓位全错
- 把"具备结束条件"当成"已经结束"，在结束点附近提前重仓，结果结构再分解、结束点下移
- 想抓顶或抄底，只能猜一个点；书里的做法是把顶部/底部逐级压缩到一个"具名级别的最后一浪具备结束条件"的区域
- 调整浪越看越乱：剪刀式、镰刀式、双节棍式、三角形、组合结构、浪中浪互相转化，不知道该按哪一套找结束点
- 日线看多、周线看空，不知道听谁的；结构变了，支撑阻力与止损该不该跟着迁移
- 方向看对了仓位下错了：该轻时重仓、该重时只敢试单，或者用固定百分比的资金止损代替结构止损

## 蒸馏了什么

12 张能力卡，按"先立坐标、再判结束、然后抓顶底、最后落到仓位与计划"的顺序组织：

- **坐标与结束判定**：`jingzhun-wave-levels`（逐级数浪与级别定位）、`jingzhun-end-conditions`（具备结束条件与确立结束判定）
- **顶底捕捉**：`jingzhun-top-capture`（推动浪顶部捕捉，含延长浪）、`jingzhun-bottom-capture`（调整浪底部捕捉，含 c 浪交易）
- **调整结构家族**：`jingzhun-correction-patterns`（调整结构模式库：四模式 + 剪刀/镰刀/双节棍 + 强弱）、`jingzhun-complex-correction`（复杂调整与浪中浪）、`jingzhun-triangle-trading`（三角形识别、方向/幅度与两段式交易）、`jingzhun-combination-structure`（组合结构的形成、演变与三种未来）
- **势、级别与周期**：`jingzhun-trend-position`（顺势四分法与仓位/确定性管理）、`jingzhun-multi-timeframe`（大小级别一致性与支撑阻力/止损迁移）、`jingzhun-horizon-extension`（中长线/波段/短线策略与延长浪盈利管理）
- **整合**：`jingzhun-trade-plan`（交易计划整合）

## 两种打包模式：single 与 pack

同一套 12 张能力卡，按两种粒度各编译了一次。两者内容完全相同，区别只在"agent 能看到几个入口"。

| | single（单一入口） | pack（compact pack，多入口） |
|---|---|---|
| 可发现入口 | **1 个**：`wave-accurate-counting-skill` | **8 个**：1 个来源路由入口 + 7 个已晋级独立 skill |
| 12 张能力卡放在哪 | 全部在入口的 `references/capabilities/` 里，由入口按路由表按需加载 1–2 张 | 7 张高频卡各自独立成 skill；其余 5 张仍在 router 的 `references/` 里 |
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

留在 router 内、不单独成 skill 的 5 张：`jingzhun-correction-patterns`、`jingzhun-complex-correction`、`jingzhun-triangle-trading`、`jingzhun-combination-structure`、`jingzhun-horizon-extension`。

### 该装哪一种

按你的工作方式选，**只装一种**：

| 你的工作方式 | 推荐 | 原因 |
|---|---|---|
| 用 DSH / Codex / Claude Code 等有 skills 目录，希望列表干净 | single | 只占 1 个入口，能力一张不少 |
| 日常问题高度集中在"数浪 / 结束没有 / 顶在哪 / 底在哪 / 仓位多重 / 周期冲突 / 出交易计划" | pack | 这 7 类正是被晋级的独立 skill，能直接命中 |
| 要分发给多个 agent 或团队，各自按需取用 | pack | 可以只装其中几个独立 skill，不必整包 |
| 只想装一次、不想维护多个目录 | single | 升级时只替换 1 个目录 |

> 两版由同一个 Bundle 编译，能力内容一致。**同时安装会重复触发**，请只装一种。

## 效果示例

### 示例 1：6124 附近能不能逃顶，止损放哪

**用户问题**

"上证指数在 6124 附近，五浪是不是走完了？哪里逃顶，止损放哪？"

**skill 如何判断**

- `jingzhun-wave-levels`：先定级别——这段是日线大浪{3}；推动浪起点必须落在前一大级调整的终点，起点左侧要是完整三浪，否则后面全错
- `jingzhun-top-capture`：验推动（1、3、5 是否各为次一级完整五浪，2 不破 1 起点、4 不重叠 1 顶、3 不为最短），再把 {v} 拆到微浪(v)，必要时拆到亚微浪 v
- `jingzhun-top-capture`：逐条核对延长浪六类信号；只有信号、没有"同级推动浪上破 {v} 高点"的硬确认时，只能按普通顶部处理，不按延长目标死拿
- 目标不是固定百分比：短线＝下一级调整结束，波段＝本级 A、B、C 结束，中长线＝上一级 A、B、C 结束

**最终回答示例**

> 先别把"五浪走完"当结论。先定级别：这里按日线大浪{3}处理，起点是前一大级调整的终点，起点左侧必须能数出完整三浪；再把 {v} 往下拆到微浪(v)、亚微浪 v，顶部候选区落在"最小可用级别的最后一浪具备结束条件"的位置——这是一个区域，不是一个预测点位。延长浪六类信号要逐条给"有/无/待验证"，但信号不等于事实，硬确认是 {v} 具备结束条件后只走低一级调整、随后同级推动浪上破 {v} 高点；没有这一步，只能按保底目标，不能拿延长目标死拿。
>
> 关于下单，书中这个案例有一个必须说清的执行冲突：它同时给了"6124 上方 0～100 点区域"和"技术止损 6126"。如果你在 6126 以上入场，止损反而落在入场价下方，风险不可控。实盘要么把可执行区收窄到 6124～6126，要么改用结构止损并降低仓位，不能把"区域"和"止损"机械地同时套用。这是阶段 4 压力测试发现的问题，原书没有解决。
>
> 另外两条边界：1～2 点的止损口径假设流动性好、无跳空，A 股个股的 T+1 与涨跌停会让它失效；书中这段案例未给单笔盈亏，方法本身也没有样本外统计背书。

### 示例 2：这段调整走完了吗，现在能不能抄底

**用户问题**

"这波跌了这么久，c 浪是不是结束了？现在能不能先买一点？"

**skill 如何判断**

- `jingzhun-end-conditions`：先把四个关键点标出来——c 浪极值、c 浪高点、a 浪起点、b 浪高点，缺一个就先补标，不判结束
- `jingzhun-end-conditions`：判"具备"还是"确立"——a0 上破 c 浪高点＝初步确立，上破 a 浪起点＝更强确立；再看后市有没有走出"本应运行的推动浪"
- `jingzhun-bottom-capture`：把底压到最小 c 浪；最小 c 浪"具备结束条件"只轻仓试单，出现"确立结束"才加仓；止损放最小 c 浪确立结束低点下 1～2 点
- `jingzhun-trend-position`：仓位按确定性分档，B 浪位置不可重仓；c 浪交易本质是逆市单，不能因为"利润可观"就重仓
- 若 b 浪上破 a 浪起点，调整转上倾，底部流程作废，改顺上倾结构做多

**最终回答示例**

> 现在只能给你一个状态，不能直接回答"能不能买"。按 a、b、c 三段标出四个关键点后，先看是否满足"具备结束条件"——它只说明这一级的最低构成够了，可以结束，但不保证已经结束；它还可以再分解、再延长。真正的加仓信号是"确立结束"：a0 上破 c 浪高点算初步确立，上破 a 浪起点算更强确立，而且后市要走出一段本应运行的推动浪，而不是只走反弹或三浪。
>
> 对应两档动作：具备处价格好但易变、止损容易被打，只宜轻仓试单，止损放极值外 1～2 点；确立后或 b0 回调接近 c 浪低点时，价格差一些，但止损确定，可以加仓。书中明确说最佳风险回报常常在后者，而不是"具备"那一刻。
>
> 还有一个必须提前想好的情形：如果之后又下破 c 浪低点，原 b 改 a、原 c 改 b、a0 改 c，结束点下移，整张计划要重标。书里 2319.74 就是这样一个案例——它具备结束条件、外形还像强势三角形，后市却下破到 1849，年线(b) 被判定为已分解。所以哪怕"具备 + 形态漂亮"，也只能靠止损兜底，不能靠信心兜底。

## 这些 skill 是怎么生成出来的

这套 skill 使用 **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** 的 RIA-TV++ 流水线生成，整个流程分六个阶段：

1. **整书理解（Adler 分析）**——用 Mortimer Adler 的分析阅读法，对全书做结构、解释、批判、应用四步拆解
2. **并行提取**——同时派多个专项提取器（框架、原则、案例、反例、术语），从原文中提取候选方法论单元
3. **三重验证筛选**——每个候选必须通过三项检验：书内至少有 2 处独立佐证（跨域）、能回答书中未明说的新问题（预测力）、不是常识（独特性）
4. **RIA++ 构造**——按 R（原文引用）/ I（用自己的话重写）/ A1（书中案例）/ A2（未来触发场景）/ E（可执行步骤）/ B（边界与盲点）六个维度结构化
5. **Zettelkasten 链接**——找出能力卡之间的依赖、对比、组合关系，生成能力索引与路由表
6. **触发与输出测试**——为每张卡设计触发盲测题（含诱饵题：该触发时要触发，不该触发时要沉默）与输出评测场景，未通过的卡回炉重做，回炉后再做回归验证

这本书的结构也决定了蒸馏方式：全书不是按形态字典排列，而是"语言层（九级浪级）→ 模式层（调整结构家族）→ 时机层（具备结束条件与确立结束）→ 风控层（止损、目标、仓位）→ 策略层（顺势与周期）"层层递进，所以能力卡按这条主线切分，而不是按章节平均分配。

## 测试与验证

本仓库连生成过程的测试材料一起发布：`evals/` 下是触发与执行测试的题面、执行输出和逐项评分记录——包含失败与修订的完整过程，不是只留通过记录。

- **触发盲测**：51 条（should_trigger 25、should_not_trigger 18、edge_case 8）。首轮 48/51，3 条误选（tp-2、tp-6、bc-6）经 description 边界修订后重测命中，最终 51/51
- **执行测试**：12 个能力 × 正常/边界两个场景，共 24 项，全部通过字段核对；边界任务全部给出"不能 / 降级 / 未确认 / 回避"的明确处理，没有强行给确定性结论
- **记录在案的问题**：6124 案例"顶部区域"与"止损 6126"的执行冲突、止损距离与仓位的量化映射缺失、股票与杠杆品种仓位口径不同、数据不足时必须标"未确认"——这些进入 needs-review，并写进了对应能力卡的边界段
- **未做**：跨模型复测、实盘或样本外统计检验、真实资金回测。以上不作为"已证明有效"的依据

## 仓库结构

```text
wave-accurate-counting-skill/
├── README.md                      ← 你正在看的
├── README.en.md                   ← English version
├── LICENSE                        ← MIT
├── BOOK_OVERVIEW.md               ← 整书理解（Adler 四步拆解，阶段 0 产出）
├── verified.md                    ← 12 个规范单元的三重验证结论
├── single/                        ← 单一入口模式
│   └── wave-accurate-counting-skill/
│       ├── SKILL.md               ← 入口：触发条件 + 路由表 + 加载规则
│       ├── BUILD_MANIFEST.json    ← 编译清单与文件哈希
│       └── references/
│           ├── overview.md        ← 整书概览
│           ├── capability-index.md  ← 完整意图与关键词索引
│           ├── cheatsheet.md      ← 决策规则速查
│           ├── glossary.md        ← 术语表
│           └── capabilities/      ← 12 张能力卡
├── pack/                          ← 多入口模式（compact pack）
│   ├── BUILD_MANIFEST.json
│   ├── capability-destinations.json
│   ├── wave-accurate-counting-skill-router/
│   │   ├── SKILL.md               ← 来源路由入口
│   │   └── references/
│   │       ├── capabilities/      ← 12 张卡，供 router 内部调用
│   │       ├── capability-index.md
│   │       ├── cheatsheet.md
│   │       ├── glossary.md
│   │       └── overview.md
│   ├── jingzhun-wave-levels-skill/
│   │   └── SKILL.md
│   ├── jingzhun-end-conditions-skill/
│   │   └── SKILL.md
│   ├── jingzhun-top-capture-skill/
│   │   └── SKILL.md
│   ├── jingzhun-bottom-capture-skill/
│   │   └── SKILL.md
│   ├── jingzhun-trend-position-skill/
│   │   └── SKILL.md
│   ├── jingzhun-multi-timeframe-skill/
│   │   └── SKILL.md
│   └── jingzhun-trade-plan-skill/
│       └── SKILL.md
└── evals/                          ← 触发与执行测试记录
    ├── test-results.md             ← 逐项评分与修订记录
    ├── test-prompts.json           ← 51 条触发/近邻/边界用例
    ├── test-prompts-per-skill/     ← 8 个入口各自的用例
    ├── blind-A.md                  ← 盲测记录 A
    ├── blind-B.md                  ← 盲测记录 B
    ├── entrypoints.md              ← 入口清单
    └── outputs/                    ← 24 份执行输出（12 能力 × 正常/边界）
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

装完问一句"这段调整走完了吗、c 浪能不能算结束"，看 agent 是否先要 a、b、c 三个关键点、是否把"具备结束条件"和"确立结束"分开说，而不是直接给你一个"可以抄底"。装的是 single 时，它会先读入口再按路由表进能力卡；装的是 pack 时，对应能力会被直接命中。

## 来源

- 《精准数浪》陈晓东 著
- 全书蒸馏，共产出 12 张能力卡

## 声明

本仓库只发布蒸馏后的 skill、索引与规则速查材料，不包含原书 PDF、EPUB、OCR 文件、截图或全书转写稿。能力卡中出现的原文引用仅用于标注方法论出处和保持可审计性。

书中所有数字判据（九级浪级划分、1～2 点技术止损、调整深度 0.382/0.5/0.618、仓位比例档位等）都是案例与经验归纳，原书未提供统计回测背书，案例多为事后标注；"确定性"没有评分表。使用时需按标的与周期自行测试并声明所用口径。本仓库内容不构成投资建议。

## License

[MIT](./LICENSE)

