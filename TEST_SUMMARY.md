# Stage 4 压力测试摘要

> 本文件汇总《精准数浪》能力包的阶段 4（触发与执行压力测试）材料与结论。
> 数据来源：归档 `审计过程/流水线与测试/test-prompts.json`、`test-prompts-per-skill/`、`test-results.md`、`审计过程/PIPELINE_STATE.md`，以及本仓库现有 `evals/` 与各 skill 目录。

## 测试范围

- **skill 数量：9 个可加载 skill**
  - `single/` 1 个：`wave-accurate-counting-skill`（单入口，内含 12 张能力卡的路由与 references）
  - `pack/` 8 个：7 个晋级能力（`jingzhun-wave-levels-skill`、`jingzhun-end-conditions-skill`、`jingzhun-top-capture-skill`、`jingzhun-bottom-capture-skill`、`jingzhun-trend-position-skill`、`jingzhun-multi-timeframe-skill`、`jingzhun-trade-plan-skill`）+ 1 个路由入口 `wave-accurate-counting-skill-router`
  - 能力卡共 12 张：7 张 promoted 独立成 skill；另 5 张（模式库、浪中浪、三角形、组合结构、延长浪）随 router 的 `references/capabilities/` 分发
- **test-prompts 文件：10 个**
  - suite 级 2 份（内容相同）：`evals/test-prompts.json`、`single/wave-accurate-counting-skill/test-prompts.json`，各 51 条
  - 每 skill 1 份共 8 份：`pack/<skill>/test-prompts.json`，合计 48 条
  - 去重后用例总数 **99 条**（suite 51 + per-skill 48；同一批用例在不同目录各有副本，未重复计入）
- **覆盖类型**
  - suite 级：`should_trigger` 25 / `should_not_trigger` 18 / `edge_case` 8
  - per-skill：`should_trigger` 25 / `should_not_trigger` 16 / `edge_case` 7
  - `output_case`：**JSON 中无该类型条目**。执行输出用例以 24 份独立输出文件（归档 `流水线与测试/outputs/c1-normal.md … c12-boundary.md`）记录，未并入 test-prompts.json
- 触发用例同时覆盖“该触发”与“诱饵（不该触发）”两类，并针对近邻能力设置了跨 skill 混淆用例（tp-2 / tp-6 / bc-6）

## 结构检查

| 检查项 | 方法 | 结果 |
|---|---|---|
| JSON 可解析性 | 对仓库内全部 `test-prompts.json` 执行 `json.load` | 10/10 通过，无语法错误 |
| frontmatter | 检查 9 个 `SKILL.md` 是否以 `---` 开头并含 `name` / `description` | 9/9 通过 |
| 六段完整性 | 检查 `bundle/cards/`、`single/`、`pack/` 下能力卡是否含 R / I / A1 / A2 / E / B 六段 | 36 份卡片全部齐全，0 缺段 |
| 用例字段 | 每条用例含 `id` / `type` / `prompt`，suite 级另含 `expected_choice` | 符合 |
| candidates 文本性 | 递归复制归档 `审计过程/candidates/` | 5 个 `.md`（cases / counter-examples / frameworks / glossary / principles），无图片、无 PDF |

## 结果

- **skills：9**
- **test_json：10**
- **通过情况**（摘自归档 `test-results.md`，测试时间 2026-10-17，宿主/模型 ZCode / deepseek-flash）：
  - 触发测试：**51/51**。首轮 48/51，3 条（tp-2、tp-6、bc-6）因 description 边界重叠误选，修订 description 后重测 3/3；其余 48 条未改动，作为回归保留
  - 诱饵容错：18 条 `should_not_trigger` 全部未误触发被测入口
  - 执行测试：12 能力 ×（正常 + 边界）= **24/24** 完成并通过字段核对；12 项边界任务全部给出“不能 / 降级 / 未确认 / 回避”的明确处理
  - 未做的验证：跨模型复测、样本外统计检验、真实资金回测——这些不作为“已证明有效”的依据
- **说明**：上述数字来自原流水线的测试记录；本仓库本次只做材料归位与结构核对，未重新跑触发/执行测试，也未改动任何用例预期。2026-10-24 复核轮曾按方法论修订 tp-2 的预期并留痕（见 `test-prompts.json` notes）

## 可接入 darwin-skill 的后续动作

1. **回归样本固化**：`single/<入口>/test-prompts.json` 与 `pack/<skill>/test-prompts.json` 可直接作为回归基线，每次改 `description`、路由表或能力卡内容后重跑触发测试，重点盯 tp-2 / tp-6 / bc-6 这三条历史误选用例。
2. **按 skill 粒度回归**：per-skill 文件已跟着 skill 走，可按“改了哪张卡就只跑哪个目录”的方式做增量回归，避免全量 51 条每次都跑。
3. **补 output_case**：当前 JSON 只有触发类用例，执行质量靠 24 份输出文件人工核对；建议把执行契约（结论 / 结构 / 关键位 / 止损 / 目标 / 仓位 / 失效条件 / 状态）抽成可自动比对的结构化用例。
4. **补跨模型复测**：现有结果只在 ZCode / deepseek-flash 上取得，换模型后应重跑并单独记录，不与本轮结果混算。
5. **把测试发现转成用例**：顶部区与止损冲突（6124 案例）、止损距离与仓位的量化映射、股票与杠杆品种的仓位基数口径、数据不足时的降级规则，这 4 条遗留问题适合各补 1 条边界用例。
