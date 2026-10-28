<h1 align="center">Wave Accurate Counting Skill</h1>

<p align="center"><a href="README.md">中文</a> | English</p>

An AI skill pack for immediate use — it distills the internal-structure wave analysis method from Chen Xiaodong's *Accurate Wave Counting* into 12 capability cards that can be triggered individually or combined: fix the wave degree and structure first, then judge "end conditions met / end established", enter at the top of an impulse wave or the bottom of a correction with a technical stop 1–2 points beyond the extreme, target the end of the next-degree structure, and size the position by structural certainty.

It is not a book summary, nor a reading response — it breaks the reusable methodology in the book into skill modules that can be triggered, executed and tested.

## What these skills solve

- You can see a "five-wave advance" but cannot say which degree it belongs to, whether waves 1/3/5 can be subdivided, or whether this is an impulse or a zigzag rebound — get the degree wrong and direction, targets, stops and position size are all wrong
- You treat "end conditions met" as "the end", pile in near the end point, and then the structure subdivides again and the end point shifts
- You try to pick tops and bottoms as a single point; the book's method compresses the top or bottom into a zone tied to "the last wave of a named degree meeting end conditions"
- Corrections become unreadable: scissors, scythe, nunchaku, triangles, combination structures and waves-within-waves morph into each other, and you cannot tell which rule set should locate the end
- The daily chart says up and the weekly says down, and you do not know which one wins; when the structure changes, you do not know whether support/resistance and stops should migrate with it
- Direction right, sizing wrong: heavy when you should be light, a token probe when you should add, or a fixed-percentage money stop standing in for a structural stop

## What was distilled

12 capability cards, organized in the order "set the coordinates first, judge the end second, capture the top or bottom third, land on sizing and a plan last":

- **Coordinates and end diagnosis**: `jingzhun-wave-levels` (degree-by-degree wave counting and degree location), `jingzhun-end-conditions` (end conditions met versus end established)
- **Top and bottom capture**: `jingzhun-top-capture` (impulse-wave top capture, including extensions), `jingzhun-bottom-capture` (correction-bottom capture, including c-wave trades)
- **Correction family**: `jingzhun-correction-patterns` (the correction pattern library: four base patterns plus scissors/scythe/nunchaku and strength grading), `jingzhun-complex-correction` (complex corrections and waves within waves), `jingzhun-triangle-trading` (triangle identification, direction/magnitude and two-stage trading), `jingzhun-combination-structure` (how combination structures form, evolve, and their three possible futures)
- **Trend, degree and horizon**: `jingzhun-trend-position` (the four-way trend test with position sizing and certainty management), `jingzhun-multi-timeframe` (degree consistency, support/resistance and stop migration), `jingzhun-horizon-extension` (positioning horizon and profit management in extensions)
- **Integration**: `jingzhun-trade-plan` (assembling the trade plan)

## Two packaging modes: single and pack

The same 12 capability cards are compiled twice, at two granularities. The content is identical; the only difference is how many entries an agent can discover.

| | single (one entry) | pack (compact pack, multiple entries) |
|---|---|---|
| Discoverable entries | **1**: `wave-accurate-counting-skill` | **8**: one source router + 7 promoted standalone skills |
| Where the 12 cards live | All inside the entry's `references/capabilities/`, loaded 1–2 at a time by the router table | 7 high-frequency cards become standalone skills; the other 5 stay in the router's `references/` |
| Triggering | Only the entry description participates in matching; routing happens after entry | The 7 high-frequency capabilities are matched directly, one hop fewer |
| Upgrades | Replace 1 directory | Replace 8 directories |

The 7 cards promoted to standalone skills in the pack:

- `jingzhun-wave-levels-skill` — degree-by-degree wave counting and degree location
- `jingzhun-end-conditions-skill` — end conditions met versus end established
- `jingzhun-top-capture-skill` — impulse-wave top capture, including extensions
- `jingzhun-bottom-capture-skill` — correction-bottom capture, including c-wave trades
- `jingzhun-trend-position-skill` — the four-way trend test with sizing and certainty
- `jingzhun-multi-timeframe-skill` — degree consistency, support/resistance and stop migration
- `jingzhun-trade-plan-skill` — assembling the trade plan

The 5 that stay inside the router and are not standalone: `jingzhun-correction-patterns`, `jingzhun-complex-correction`, `jingzhun-triangle-trading`, `jingzhun-combination-structure`, `jingzhun-horizon-extension`.

### Which one to install

Pick by the way you work, and **install only one**:

| How you work | Recommended | Why |
|---|---|---|
| You use DSH / Codex / Claude Code with a skills directory and want a clean list | single | Takes 1 slot, loses no capabilities |
| Your daily questions concentrate on "which degree / is it over / where is the top / where is the bottom / how big / conflicting timeframes / build me a plan" | pack | Those 7 are exactly the promoted standalone skills, matched directly |
| You distribute to several agents or teammates who pick what they need | pack | They can install only the standalone skills they want |
| You want to install once and maintain one directory | single | Upgrades replace a single directory |

> Both builds come from the same bundle and carry identical capabilities. **Installing both will double-trigger**, so pick one.

## Examples

### Example 1: can I sell the top near 6124, and where does the stop go?

**User question**

"The Shanghai Composite is around 6124. Is the five-wave advance finished? Where do I sell the top, and where does the stop go?"

**How the skill reasons**

- `jingzhun-wave-levels`: fix the degree first — this is treated as daily-degree primary wave {3}; the impulse must start at the end of the previous higher-degree correction, with a complete three-wave structure to the left of that start, otherwise everything downstream is wrong
- `jingzhun-top-capture`: verify the impulse (are waves 1, 3 and 5 each a complete lower-degree five-wave structure; does wave 2 hold above the start of wave 1, does wave 4 avoid overlapping the top of wave 1, is wave 3 not the shortest), then subdivide {v} down to minute wave (v) and, if needed, to subminuette v
- `jingzhun-top-capture`: check the six extension signals one by one; with signals but no hard confirmation — "after {v} meets end conditions only a lower-degree correction follows, then a same-degree impulse breaks above the {v} high" — treat it as an ordinary top and do not hold for extension targets
- Targets are not fixed percentages: short-term = end of the next-degree correction, swing = end of this degree's A, B, C, long-term = end of the previous degree's A, B, C

**Sample answer**

> Do not treat "the five waves are done" as a conclusion. Fix the degree first: this is handled as daily-degree primary wave {3}, whose start is the end of the previous higher-degree correction, and the left side of that start must show a complete three-wave structure. Then subdivide {v} down to minute (v) and subminuette v; the top candidate zone sits where "the last wave of the smallest usable degree meets end conditions" — a zone, not a predicted point. Give a yes/no/to-be-verified verdict on each of the six extension signals, but a signal is not a fact: the hard confirmation is that {v} meets end conditions, only a lower-degree correction follows, and then a same-degree impulse breaks the {v} high. Without that, you plan for the fallback target, not the extension target.
>
> On execution, this book case contains a conflict you have to state out loud: it gives both a "0–100 points above 6124" zone and a "technical stop at 6126". If you enter above 6126, the stop sits below your entry and the risk is uncontrolled. In practice either narrow the executable zone to 6124–6126, or switch to a structural stop and cut the position — do not apply the "zone" and the "stop" mechanically at the same time. This was found in stage-4 stress testing; the book does not resolve it.
>
> Two more boundaries: the 1–2 point stop convention assumes good liquidity and no gaps, and A-share T+1 plus price limits will break it; the book reports no per-trade P&L for this case, and the method itself has no out-of-sample statistical backing.

### Example 2: is this correction over — can I start buying?

**User question**

"It has been falling for so long. Is the c wave finished? Can I buy a little now?"

**How the skill reasons**

- `jingzhun-end-conditions`: mark four key points first — the c-wave extreme, the c-wave high, the a-wave start, the b-wave high; if one is missing, label it before judging anything
- `jingzhun-end-conditions`: separate "met" from "established" — a0 breaking the c-wave high is preliminary establishment, breaking the a-wave start is stronger establishment; then check whether the market actually produces the impulse it is supposed to run
- `jingzhun-bottom-capture`: compress the bottom to the smallest c wave; "end conditions met" on that wave allows only a light probe, "end established" allows adding; the stop goes 1–2 points below the low that established the end
- `jingzhun-trend-position`: size by certainty, never heavy in a B wave; a c-wave trade is counter-trend by nature, so a "big payoff" is not a reason to size up
- If the b wave breaks above the a-wave start, the correction turns upward-sloping, the bottom workflow is void, and you switch to trading the upward-sloping structure long

**Sample answer**

> What I can give you now is a state, not a yes/no on buying. After labelling the a, b, c legs and the four key points, first check whether end conditions are met — that only says the minimum structure for this degree is satisfied and it may end, not that it has ended; it can still subdivide or extend. The add signal is "end established": a0 breaking the c-wave high counts as preliminary, breaking the a-wave start as stronger, and the market must then run the impulse it is supposed to run, not just a rebound or a three-wave move.
>
> That maps to two actions. At "met", the price is good but fragile and the stop is easily hit, so only a light probe with the stop 1–2 points beyond the extreme. After establishment, or when b0 pulls back near the c-wave low, the price is worse but the stop is definite, so you can add. The book says explicitly that the best risk-reward is usually the second, not the "met" moment.
>
> Plan one more scenario in advance: if price later breaks the c-wave low, the old b becomes a, the old c becomes b, a0 becomes c, the end point shifts down, and the whole plan must be relabelled. The book's 2319.74 case is exactly this — end conditions were met and the shape even looked like a strong triangle, yet price broke down to 1849 and the yearly (b) was judged to have subdivided. So even with "met plus a pretty pattern", only the stop protects you, not conviction.

## How these skills were generated

These skills were produced with the **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** RIA-TV++ pipeline, in six stages:

1. **Whole-book comprehension (Adler analysis)** — apply Mortimer Adler's analytical reading method to the book: structure, interpretation, criticism, application
2. **Parallel extraction** — several specialized extractors (frameworks, principles, cases, counter-examples, terminology) mine candidate methodology units from the source text
3. **Triple verification** — every candidate must pass three checks: at least two independent in-book supports (cross-domain), the ability to answer questions the book never explicitly addresses (predictive power), and not being common sense (distinctiveness)
4. **RIA++ construction** — structure each unit along R (quotation) / I (restatement in own words) / A1 (in-book case) / A2 (future trigger scenario) / E (executable steps) / B (boundaries and blind spots)
5. **Zettelkasten linking** — map dependencies, contrasts and combinations between cards, producing the capability index and routing table
6. **Trigger and output testing** — write trigger blind tests (including decoy questions: fire when they should, stay silent when they should not) and output evaluation scenarios for every card; failing cards go back for rework and are re-verified afterwards

The book's own structure shapes the distillation: it is not a pattern dictionary but a layered argument — language layer (nine wave degrees) → pattern layer (the correction family) → timing layer (end conditions met versus end established) → risk layer (stops, targets, sizing) → strategy layer (trend and horizon) — so the cards are cut along that line rather than split evenly by chapter.

## Testing and verification

This repository publishes the test material from the generation process alongside the skills: `evals/` holds the trigger and execution test cases, the execution outputs and the item-by-item scoring log — including the failures and the revisions, not just the passes.

- **Trigger blind tests**: 51 cases (should_trigger 25, should_not_trigger 18, edge_case 8). The first round scored 48/51; 3 misroutes (tp-2, tp-6, bc-6) were fixed by tightening description boundaries and re-tested, ending at 51/51
- **Execution tests**: 12 capabilities × normal / boundary = 24 items, all passing field checks; every boundary task produced an explicit "cannot / downgrade / unconfirmed / avoid" verdict instead of forcing a confident conclusion
- **Recorded issues**: the 6124 "top zone" versus "stop 6126" execution conflict, the missing quantitative link between stop distance and position size, different sizing conventions for stocks versus leveraged instruments, and the requirement to label "unconfirmed" when data is insufficient — these went into needs-review and into the boundary sections of the affected cards
- **Not done**: cross-model re-testing, live or out-of-sample statistical testing, real-money backtests. None of the above counts as proof of effectiveness

## Repository layout

```text
wave-accurate-counting-skill/
├── README.md                      ← the Chinese version
├── README.en.md                   ← you are reading this
├── LICENSE                        ← MIT
├── BOOK_OVERVIEW.md               ← whole-book comprehension (Adler, stage 0)
├── verified.md                    ← triple-verification verdicts for the 12 units
├── single/                        ← one-entry mode
│   └── wave-accurate-counting-skill/
│       ├── SKILL.md               ← entry: triggers + router table + loading rules
│       ├── BUILD_MANIFEST.json    ← build manifest and file hashes
│       └── references/
│           ├── overview.md        ← whole-book overview
│           ├── capability-index.md  ← full intent and keyword index
│           ├── cheatsheet.md      ← decision-rule quick reference
│           ├── glossary.md        ← terminology
│           └── capabilities/      ← the 12 capability cards
├── pack/                          ← multi-entry mode (compact pack)
│   ├── BUILD_MANIFEST.json
│   ├── capability-destinations.json
│   ├── wave-accurate-counting-skill-router/
│   │   ├── SKILL.md               ← source router entry
│   │   └── references/
│   │       ├── capabilities/      ← the 12 cards, called internally by the router
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
└── evals/                          ← trigger and execution test records
    ├── test-results.md             ← item-by-item scoring and revision log
    ├── test-prompts.json           ← 51 trigger/near-miss/boundary cases
    ├── test-prompts-per-skill/     ← per-entry case files for the 8 entries
    ├── blind-A.md                  ← blind-test record A
    ├── blind-B.md                  ← blind-test record B
    ├── entrypoints.md              ← entry inventory
    └── outputs/                    ← 24 execution outputs (12 capabilities × normal/boundary)
```

## How to use

Clone the repository first:

```bash
git clone https://github.com/raphael-y7/wave-accurate-counting-skill.git
```

### Install single (the one to try first)

```bash
# macOS / Linux
cp -r wave-accurate-counting-skill/single/wave-accurate-counting-skill ~/.agents/skills/
```

```powershell
# Windows
Copy-Item -Recurse .\wave-accurate-counting-skill\single\wave-accurate-counting-skill "$env:USERPROFILE\.agents\skills\"
```

### Install pack

Copy only the directories that contain a `SKILL.md`; do not copy the two json files under `pack/` into the skills directory:

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

> `~/.agents/skills` is the DSH skills directory; with another agent, use its own skills directory (Claude Code uses `~/.claude/skills`, for example).

### How to check it is installed

Ask "is this correction over — is the c wave finished?" and see whether the agent first asks for the a, b, c key points and keeps "end conditions met" apart from "end established", instead of handing you a "buy the bottom". With single it reads the entry first and follows the router table into a card; with pack the matching capability is hit directly.

## Source

- *Accurate Wave Counting* by Chen Xiaodong
- Distilled from the whole book, 12 capability cards produced

## Notice

This repository publishes only the distilled skills, indexes and quick-reference rules. It does not contain the original PDF, EPUB, OCR files, screenshots or the full book transcript. Quotations that appear inside the cards serve only to mark the methodological source and keep it auditable.

Every numeric criterion in the book (the nine wave degrees, the 1–2 point technical stop, the 0.382/0.5/0.618 correction depths, the position-size bands) is an induction from cases and experience; the book offers no statistical backtest, its cases are mostly labelled after the fact, and "certainty" has no scoring table. Test them against your own instrument and horizon, and state the convention you use. Nothing here is investment advice.

## License

[MIT](https://opensource.org/licenses/MIT)
