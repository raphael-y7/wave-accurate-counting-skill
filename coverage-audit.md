# 覆盖审计（阶段 0 任务清单 → 候选 → 判定 → 交付去向）

- 基准：`BOOK_OVERVIEW.md` 的 task-01～task-16（独立于候选池建立）
- 候选池：frameworks 30 / principles 40 / cases 41 / counter-examples 30 / glossary 39
- 结论：16 项任务全部有候选与明确去向；其中 12 项为 active 能力，4 项作为能力内步骤/参考交付。
- 未覆盖/不足：无“完全无候选”的任务；存在 6 项条件缺口（见文末），已记入 needs-review.md，不计为已覆盖的可执行能力。

| task_id | 读者任务 | 原文位置 | 候选 | 判定 | 最终去向 |
|---|---|---|---|---|---|
| task-01 | 判定基础浪/细分浪级别 | 一章一节（表1-1、图1-1）、一章六节、三章八节 | f01,f02,p01,p04 | verified | C1 逐级数浪（promoted: jingzhun-wave-levels-skill） |
| task-02 | 识别推动/调整、3-3-3/5-3-5/锯齿/平台 | 一章二至三节、二章一节、五章八节 | f28,p05,p06,p07,p32,p33 | verified | C1 + C5 模式库（C5 router） |
| task-03 | 识别剪刀/镰刀/双节棍/组合 | 一章三、十二、十六节、二章 | f06,f16,f12,p05,p09,p10,p39 | verified | C5 模式库；C8 组合（均 router） |
| task-04 | 判断具备结束条件/确立结束 | 一章五节、二章一/二/十节、四章二节 | f03,f17,f29,p14,p37 | verified | C2 结束条件（promoted: jingzhun-end-conditions-skill） |
| task-05 | 捕捉推动浪顶部 | 一章五节一、五章二节 | f04,f08,p22-p27,p40 | verified | C3 顶部捕捉（promoted: jingzhun-top-capture-skill） |
| task-06 | 捕捉调整浪底部 | 一章五节二、四章五/六节 | f05,f24,p13,p40 | verified | C4 底部捕捉（promoted: jingzhun-bottom-capture-skill） |
| task-07 | 三角形方向/幅度/买卖点 | 一章八、十二至十五节 | f07,f10,f11,p28,p29,p30 | verified | C7 三角形（router） |
| task-08 | 组合结构识别与买卖点 | 一章十六节、二章九节 | f12,p39 | verified | C8 组合结构（router） |
| task-09 | 买卖时机与仓位控制 | 一章十七节、四章五节 | f13,f23,p15,p16,p17,p18,p38 | verified | C9 顺势/仓位（promoted: jingzhun-trend-position-skill） |
| task-10 | 复杂调整/浪中浪 | 三章全章 | f19,f20,p39 | verified | C6 复杂调整（router） |
| task-11 | 调整结构演变与确定性 | 四章一/二节 | f17,f18,f20,p15 | verified | C2/C9（promoted）+ C6 router |
| task-12 | 支撑阻力与大小级别一致 | 四章三/四节 | f21,f22,p19,p34,p35 | verified | C10 大小级别（promoted: jingzhun-multi-timeframe-skill） |
| task-13 | 中长线/波段/短线与延长浪 | 五章二节 | f14,f15,f26,f27,p20,p21 | verified | C11 多周期/延长浪（router） |
| task-14 | 锯齿与推动浪区分 | 五章二节八 | f28,p32,p33,p07,p08 | verified | C1（promoted） |
| task-15 | 技术止损/目标位 | 全书交易示例 | p11,p12,p13,p35,p37 | verified | C10 + C12（promoted）+ 各卡 E 段 |
| task-16 | 形成可执行交易计划 | 一至五章综合 | f30,p11,p13,p37 | verified | C12 交易计划（promoted: jingzhun-trade-plan-skill） |

## 案例覆盖

- cases.md 41 条：historical_case 18（上证指数 998→6124→1664→3478→2319 等）、book_case 3、workbook_example 20（作者自绘结构示意图）。
- 已选用为 A1 的代表案例：998→6124 周线推动浪（C1/C3）、6124→1664 调整（C2/C4）、3478 后复杂调整（C5/C6）、三角形与组合结构图（C7/C8）、上倾强势调整与延长浪（C11）。
- 未选用案例：以逐段历史叙事为主、缺少可复用规则者，进 references.md。

## 反例覆盖

- counter-examples.md 30 条，已映射到各卡 B 段：结束点附近追单、逆大级别、把小级别当大级别、把反弹当反转、忽略延长浪、止损过远/过近、确定性不足重仓、锯齿当推动、复杂结构简单化等。

## 条件缺口（计入 needs-review，不作为已验证能力）

1. 1～2 个点止损在个股/不同品种上的点值换算，原书未给统一口径。
2. 股票仓位 30%～50%/满仓的基数（账户资金还是可用资金）未明确。
3. “0.618 以下区域为弱势”的措辞存在“回撤更深”与“低于 0.618”两种读法。
4. 三角形 7 个角等异常形态的完整规则未展开。
5. “确定性高”无评分表或阈值，只能按已排除的分解数量定性。
6. 目标位未达而结构反转时的退出规则，书中仅有零散“及时止盈/小赢出局”。
