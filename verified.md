# 阶段 1.5 — 三重验证结果（《精准数浪》）

- 候选池：frameworks 30、principles 40、cases 41、counter-examples 30、glossary 39（合计 180 条）
- 去重/聚类后：12 个能力单元（C1–C12）
- 判定口径：V1 来源充分性 / V2 可执行性（walkthrough）/ V3 任务增益；三项全过 = verified
- 说明：本阶段 walkthrough 为纸面演练，不代表实盘验证；阶段 4 另做真实任务输出核对。

```yaml
- id: c01
  capability_id: cap.wave-accurate-counting-skill.wave-level-parser
  title: 逐级数浪与级别定位（含推动浪/锯齿判别）
  type: procedure
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第一节（表1-1 浪级符号）、第一章第六节（推动浪）、第五章第二节八（锯齿与推动浪区分）}
  V1_source_sufficiency:
    passed: true
    reason: 九级浪级符号表、基础浪升级规则、推动浪1/3/5再细分五浪、锯齿允许缺陷等均有原文完整表述；p01/p04/p32/p33 逐字可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 某标的周线一段上涨，日线可见3个驱动段；先用九级表定位基础浪为小浪级，日线为细浪级；检查1、3、5浪在日线是否各为完整五浪。
    expected: 输出基础浪=小浪、细分浪=细浪；若1、3、5中任一段不能细分五浪，则降为锯齿反弹；五浪走完后基础浪上调一级。
    observed: 按 f01/f02 流程可得到上述层级与升降级动作；对“某段不能细分五浪”的情况，p32/p33 给出降级判据。
    missing_conditions: 实时数据不足时无法完成次一级细分，需标“未确认”，不得强行定为推动浪。
  V3_task_utility:
    passed: true
    expected_benefit: 防止级别错配与把锯齿当推动浪，是后续所有买卖点、止损、目标的前置坐标。
  decision: verified
  canonical_sources: [f01, f02, p01, p04, p32, p33, p07, p08]
  task_ids: [task-01, task-02, task-14]

- id: c02
  capability_id: cap.wave-accurate-counting-skill.end-condition-diagnosis
  title: 具备结束条件与确立结束判定（含结束点下移）
  type: framework
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第五节、第二章第四节、第二章第十节、第五章第二节七}
  V1_source_sufficiency:
    passed: true
    reason: 原文反复区分“具备结束条件≠确立结束”，并给出 a0 上破 c 浪高点、上破 a 浪起点、后市结构验证、结束点下移等完整判据；f03/f17/f29/p14/p37 均有逐字出处。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 一个日线调整浪已走出 a、b、c 三浪，c 浪内部三浪完成，价格尚未上破 c 浪高点。
    expected: 判定“具备结束条件”，只可轻仓试单，止损 c 浪低点下1～2点；等待上破 c 浪高点/ a 浪起点后再确认“确立结束”并加仓；若后市再破 c 浪低点，则结束点下移，原 b 改 a、c 改 b。
    observed: 按 f03 的三级判定与 f17 的结束点下移流程，能产出上述三档动作；p14 明确“具备≠确立”，p37 给出两个时点的分工。
    missing_conditions: “后市本应运行的结构”需至少一根次级别结构完成才能验证；实时当下只能给条件概率式判断。
  V3_task_utility:
    passed: true
    expected_benefit: 把“抄底/逃顶”拆成试单与加仓两档，避免把可结束当成已结束而重仓被套。
  decision: verified
  canonical_sources: [f03, f17, f29, p03, p06, p14, p37]
  task_ids: [task-04, task-09, task-11]

- id: c03
  capability_id: cap.wave-accurate-counting-skill.impulse-top-capture
  title: 推动浪顶部捕捉（含延长浪处理）
  type: procedure
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第五节一、第一章第九至十一节、第五章第二节五}
  V1_source_sufficiency:
    passed: true
    reason: 顶部逐级锁定到 {v} 的微浪(v)/亚微浪、延长浪六类信号与确立条件、延长浪后调整级别，均有完整说明；f04/f08/f09/p22-p27/p40 逐字可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 一个日线小浪1上涨已走完 {i}-{v}，{v} 内部微浪(v)接近完成；日线未出现同级推动浪上破 {v} 高点。
    expected: 将顶部锁定在微浪(v)结束区；止损放该高点上方1～2点；目标为随后细浪{a}{b}{c}调整结束。若后市同级推动浪上破 {v} 高点，则确立延长浪，顶部上移至延长浪结束。
    observed: 按 f04 的锁定步骤与 f08 的延长浪六信号，可产出“普通顶部/延长顶部”两套计划；p23 给出延长浪确立的硬条件。
    missing_conditions: 需要至少日线与60分钟两级数据；若只有日线，锁定精度下降，应放宽止损或放弃。
  V3_task_utility:
    passed: true
    expected_benefit: 把“猜顶”变成“在最小级别结束条件处设极近止损”，并提前处理延长浪导致的顶部外移。
  decision: verified
  canonical_sources: [f04, f08, f09, p22, p23, p24, p25, p26, p27, p40]
  task_ids: [task-05, task-13, task-15]

- id: c04
  capability_id: cap.wave-accurate-counting-skill.correction-bottom-capture
  title: 调整浪底部捕捉（含 c 浪交易）
  type: procedure
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第五节二、第四章第六节二（交易c浪）、第五章第二节七}
  V1_source_sufficiency:
    passed: true
    reason: 由调整级别关系推出内部三浪、把底部逐级缩到 c 浪的微浪(c)/亚微浪c、在最小 c 浪结束处抓底，以及“验证a浪、放弃b浪、交易c浪”的风险回报理由，均有原文；f05/f24/p13/p40 可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 一个周线小浪2调整，内部为细浪{a}{b}{c}；{b} 反弹接近 {a} 起点，{c} 尚未结束。
    expected: 在 {c} 的微浪(c)/亚微浪c具备结束条件或确立结束时做多；止损 {c} 确立结束低点下1～2点；目标下一个推动浪（如小浪3）结束条件。若 {b} 再分解，底部下移到 {c3}。
    observed: 按 f05 的逐级缩小与 f24 的 c 浪交易流程，可产出底部区域、止损、目标与“b浪再分解则下移”的分支。
    missing_conditions: 若 {b} 已上破 {a} 起点，调整转上倾，本流程失效，应改顺上倾结构做多。
  V3_task_utility:
    passed: true
    expected_benefit: 把抄底限定在“最小 c 浪结束+极近止损”，减少在中途 b 浪分解中接飞刀。
  decision: verified
  canonical_sources: [f05, f24, p13, p40]
  task_ids: [task-06, task-09, task-15]

- id: c05
  capability_id: cap.wave-accurate-counting-skill.correction-pattern-library
  title: 调整结构模式库（四模式+剪刀/镰刀/双节棍+强弱）
  type: checklist
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第二至四节、第二章第一节、第二章第九至十节}
  V1_source_sufficiency:
    passed: true
    reason: 基础四模式（本体三浪、5-3-5、3-3-5、3-3-3）、剪刀/镰刀/双节棍的定义与关键点、0.382/0.5/0.618强弱口径均有原文；f06/f16/p05/p06/p09/p10 逐字可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: a 浪下跌10%，b 浪反弹至 a 起点的90%后回落，c 浪下破 a 低点；b 浪内部为三浪，c 浪内部为三浪。
    expected: 先归入基础四模式（b 三浪、c 三浪→3-3-3 平台或本体变体）；因 b 未过 a 起点、c 破 a 低点，候选为剪刀式/镰刀式；再用 b 浪分解次数与 c 浪是否“进二退一”区分，输出关键点、做空点、止损（b 高点外1～2点）、目标（c 浪结束）。
    observed: 按 f16 的五类关键点表与 p10 的反弹幅度分档，可产出候选模式与两套排除条件；p05 保证先归四模式再谈衍生。
    missing_conditions: 剪刀式与镰刀式在早期常同形，书中也要求等后市验证；无法唯一确定时必须标“候选”而非“已确认”。
  V3_task_utility:
    passed: true
    expected_benefit: 统一调整结构的命名与关键点，减少“看到三浪就叫调整”的随意标注。
  decision: verified
  canonical_sources: [f06, f16, p05, p06, p09, p10]
  task_ids: [task-02, task-03, task-15]

- id: c06
  capability_id: cap.wave-accurate-counting-skill.complex-correction-wave
  title: 复杂调整与浪中浪（双复杂结构、三浪/三组三浪转化）
  type: procedure
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第三章第一至九节、第二章第九节部分}
  V1_source_sufficiency:
    passed: true
    reason: 复杂调整浪中包含复杂调整/反弹结构的多种组合、双关键点共振、三浪与三组三浪的转化判据，均有逐节说明；f19/f20/p39 可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 一个双节棍式调整浪中已出现剪刀式结构，价格接近 a1 低点与 c1 低点两个关键点。
    expected: 先识别外层双节棍、内层剪刀；当一浪或三浪同时下破两个关键点时，判“双复杂结构共振”，顺调整之势追空，止损最近反弹高点外1～2点，目标外层 c 浪结束。
    observed: 按 f19 的“两关键点共振”流程与 f20 的转化判据，可产出共振追空点与止损；只破一个关键点时降为单复杂结构，不重仓。
    missing_conditions: 内层结构可能继续演变为三组三浪；若无法排除，按多解轻仓处理。
  V3_task_utility:
    passed: true
    expected_benefit: 为“浪中浪”提供可操作的确认点，避免在单层结构里提前重仓。
  decision: verified
  canonical_sources: [f19, f20, p39]
  task_ids: [task-10, task-11]

- id: c07
  capability_id: cap.wave-accurate-counting-skill.triangle-trading
  title: 三角形识别、方向/幅度与两段式交易
  type: procedure
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第八节、第十二至十五节、第二章第八节}
  V1_source_sufficiency:
    passed: true
    reason: 引导/终结倾斜三角形的内部构成、三角形突破方向跟随 b 浪、幅度以对应 c 浪（或同级一浪）结束为准、两个买卖时机与假突破边界，均有原文；f07/f10/f11/p28/p29/p30 可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 一个收敛三角形，a 浪向下、b 浪向上、c 浪向下但未破 a 低点；内部为 3-3-3。
    expected: 方向判为向上（跟随 b 浪，即 a/c 的反方向）；时机一在完整 b 浪（c 浪起点）具备结束条件时轻仓，时机二在颈线上破时加仓；幅度目标为与 a 对应的 c 浪结束；止损放突破后 c 浪起点外1～2点。
    observed: 按 f10/f11 可产出方向、两段式入场、止损与目标；p30 给出 c 浪末端假突破等禁止追单情形。
    missing_conditions: 三角形内部若为剪刀式/浪中浪，时机一不成立，只能等突破；7 个角等异常形态书中未给完整规则。
  V3_task_utility:
    passed: true
    expected_benefit: 把三角形从“画线猜方向”变成“b 浪方向+内部结构+两段式入场”的可执行流程。
  decision: verified
  canonical_sources: [f07, f10, f11, p28, p29, p30]
  task_ids: [task-07, task-09, task-15]

- id: c08
  capability_id: cap.wave-accurate-counting-skill.combination-structure
  title: 组合结构的形成、演变与三种未来
  type: procedure
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第十六节、第二章第九节、第五章第二节}
  V1_source_sufficiency:
    passed: true
    reason: 组合结构“a1b1c1→组合a、a2b2c2→组合b、a3b3c3→组合c”的形成与移位、结束后三种未来（直接推动浪/再组合/b浪再分解），以及组合B浪（X浪）必须是同级别完整三浪，均有原文；f12/p39 可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 五浪上涨后 a1b1c1 三浪调整结束，随后 a2 反弹未过前高，c2 上破 a2 高点。
    expected: 判 a1b1c1=组合a；c2 上破 a2 高点确认 a2b2c2 为组合b；待 a3b3c3 结束形成组合c，在 c3 结束处做多；若后市再以反弹上涨，则组合b分解，按移位规则重标。
    observed: 按 f12 的步骤可产出组合a/b/c层级、c3 做多点与“三种未来”排除条件；p39 校验 X 浪级别。
    missing_conditions: 组合/移位过程复杂，实时标注可能多次改名；需以“是否上破 c 高点/下破 c 低点”的硬信号收敛。
  V3_task_utility:
    passed: true
    expected_benefit: 处理横盘蓄势与反复调整，避免把组合结构当单次三浪而错过后续推动浪。
  decision: verified
  canonical_sources: [f12, p39]
  task_ids: [task-08, task-11]

- id: c09
  capability_id: cap.wave-accurate-counting-skill.trend-position-sizing
  title: 顺势四分法与仓位/确定性管理
  type: framework
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第十七节、第二章第九节、第四章第五节、第五章第一节}
  V1_source_sufficiency:
    passed: true
    reason: 顺推动浪/顺调整/顺上倾/顺反弹四分法、确定性决定仓位、仓位分级（杠杆5-10%/10-20%/20-30%，股票30-50%/可满）、低风险重仓两前提、止损空间小于盈利空间才做，均有原文；f13/f18/f23/p15-p18/p38 可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 账户10万元，当前为日线小浪2 c浪结束、结构确定性高，技术止损距入场2个点，目标距入场20个点。
    expected: 判“顺推动浪之势”做多；按股票口径一般仓位30%～50%，因确定性高且止损近可上调；止损放c浪低点下1～2点；若止损空间扩大到10个点而目标仍20个点，则降仓或等待。
    observed: 按 f13 的仓位分级与 f18 的四分法可产出方向、仓位档、止损；p17/p18 给出“绝对重仓/相对重仓”的分界。
    missing_conditions: 书中仓位比例为经验口径，未给风险价值（VaR）或凯利公式；不同品种点值需换算。
  V3_task_utility:
    passed: true
    expected_benefit: 把“看对却亏钱”的仓位问题纳入流程，明确何时重仓、何时只试单。
  decision: verified
  canonical_sources: [f13, f18, f23, p15, p16, p17, p18, p38]
  task_ids: [task-09, task-11, task-16]

- id: c10
  capability_id: cap.wave-accurate-counting-skill.multi-timeframe-levels
  title: 大小级别一致性与支撑阻力/止损迁移
  type: framework
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第四章第三节（支撑阻力）、第四章第四节（小级别服从大级别）、全书止损规则}
  V1_source_sufficiency:
    passed: true
    reason: 浪形起止点即支撑阻力且精确到点、阻力位随结构变化而迁移、小级别/小周期必须服从大级别/大周期、技术止损随结构移动，均有原文；f21/f22/p19/p34/p35/p11 可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 周线处于大级别C浪下跌，日线出现一个五浪上涨；日线前高为阻力，前低为支撑。
    expected: 判定日线五浪为周线C浪内的锯齿反弹，不可当反转；在日线反弹结束处顺周线调整方向做空，止损放日线反弹高点外1～2点；目标周线C浪结束；若日线上破周线关键阻力并形成推动浪，则重新评估。
    observed: 按 f21 的“先大后小”与 f22 的支撑阻力迁移，可产出方向、关键位、止损；p19 明确冲突时服从大级别。
    missing_conditions: 大级别本身未确立时，不能机械压死小级别；需标多解并轻仓。
  V3_task_utility:
    passed: true
    expected_benefit: 防止“日线看多、周线看空”时的方向混乱，并把止损锚定在结构关键位而非固定比例。
  decision: verified
  canonical_sources: [f21, f22, p19, p34, p35, p11]
  task_ids: [task-12, task-13, task-15]

- id: c11
  capability_id: cap.wave-accurate-counting-skill.horizon-extension-strategy
  title: 中长线/波段/短线策略与延长浪盈利管理
  type: framework
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第一章第十七节、第五章第二节一至五、第四章第六节}
  V1_source_sufficiency:
    passed: true
    reason: 推动浪级别对应短线/波段/中长线、各周期入场与目标、延长浪保底目标+延长目标、复杂结构失败后的反手，均有原文；f14/f15/f26/f27/f25/p20/p21 可查。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 一个日线中浪级推动浪，2浪走成上倾强势调整，当前持有波段多单。
    expected: 判延长浪信号；先设保底目标为同级三浪回调的B浪反弹结束，若同级推动浪上破前高则改持到延长浪结束；止损上移至调整低点外1～2点；若结构失败（上破失败并跌破关键点），按反手流程处理。
    observed: 按 f27 的保底/延长双目标与 f26 的周期分层，可产出持仓周期、目标与止损；f25 给出失败反手条件。
    missing_conditions: 延长浪是否真形成需后市确认；未确认前不得把延长目标当既定事实。
  V3_task_utility:
    passed: true
    expected_benefit: 解决“看对延长浪却早早下车”与“把反弹当延长”的两类错误。
  decision: verified
  canonical_sources: [f14, f15, f25, f26, f27, p20, p21]
  task_ids: [task-13, task-05, task-06]

- id: c12
  capability_id: cap.wave-accurate-counting-skill.trade-plan-builder
  title: 交易计划整合（结构→势→入场→止损→目标→仓位→失效）
  type: procedure
  source_evidence:
    - {source_id: wave-accurate-counting-skill, location: 第五章开篇及第一节、第二节；全书各节交易示例}
  V1_source_sufficiency:
    passed: true
    reason: 浪级定位→结构判定→定势→入场→止损→目标→仓位→失效的完整链条，书中各章均有对应规则，f30 将其整合；每一步都能回指原文。
  V2_executability:
    passed: true
    check_mode: walkthrough
    input: 某标的日线数据、账户资金、风险上限；当前疑似小浪2 c浪结束。
    expected: 输出一张交易计划表：浪级（小浪2/细浪c）、结构（3-3-3或剪刀）、势（顺推动浪）、入场（c浪确立结束）、止损（c浪低点下2点）、目标（小浪3结束）、仓位（按确定性30%～50%）、失效（下破c浪低点且结构重标）。
    observed: 按 f30 的八步流程可填满计划表；若任一项无法确定（如结构多解），表内标“待确认/轻仓”，不得省略。
    missing_conditions: 书中没有账户风险百分比与最大回撤约束；需在模板中作为用户自定义项，不冒充原书规则。
  V3_task_utility:
    passed: true
    expected_benefit: 把分散在五章的规则整合成可执行、可复核的交易计划，直接服务用户的投资分析。
  decision: verified
  canonical_sources: [f30, p11, p13, p37]
  task_ids: [task-15, task-16]
```

## 判定汇总

| 能力 | V1 | V2 | V3 | 判定 |
|---|---|---|---|---|
| C1 逐级数浪 | ✅ | ✅ | ✅ | verified |
| C2 结束条件 | ✅ | ✅ | ✅ | verified |
| C3 顶部捕捉 | ✅ | ✅ | ✅ | verified |
| C4 底部捕捉 | ✅ | ✅ | ✅ | verified |
| C5 模式库 | ✅ | ✅ | ✅ | verified |
| C6 复杂调整/浪中浪 | ✅ | ✅ | ✅ | verified |
| C7 三角形 | ✅ | ✅ | ✅ | verified |
| C8 组合结构 | ✅ | ✅ | ✅ | verified |
| C9 顺势/仓位 | ✅ | ✅ | ✅ | verified |
| C10 大小级别/支撑阻力 | ✅ | ✅ | ✅ | verified |
| C11 多周期/延长浪 | ✅ | ✅ | ✅ | verified |
| C12 交易计划 | ✅ | ✅ | ✅ | verified |

## 去重与合并映射（供审计）

- f01+f02+p01+p04+p32+p33+p07+p08 → C1
- f03+f17+f29+p03+p06+p14+p37 → C2
- f04+f08+f09+p22-p27+p40 → C3
- f05+f24+p13+p40 → C4
- f06+f16+p05+p06+p09+p10 → C5
- f19+f20+p39 → C6
- f07+f10+f11+p28+p29+p30 → C7
- f12+p39 → C8
- f13+f18+f23+p15-p18+p38 → C9
- f21+f22+p19+p34+p35+p11 → C10
- f14+f15+f25+f26+f27+p20+p21 → C11
- f30+p11+p13+p37 → C12
- 合计：上列 12 行共 71 条候选出处引用（各单元 `canonical_sources` 条数之和，去重后为 65 个不同候选 id）
- 未被上述能力吸收的案例（cases.md）作为 A1 素材保留；术语（glossary.md）进入 GLOSSARY。
