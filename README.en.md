<h1 align="center">Wave Accurate Counting Skill</h1>

<p align="center"><a href="README.md">中文</a> | English</p>

An AI skill pack for immediate use — it distills the internal-structure wave counting method of 陈晓东's *Accurate Wave Counting: Internal Structure Analysis of Wave Theory and Buy/Sell Point Handling* into 12 capability cards that can be triggered individually or combined.

It is not a book summary, nor a reading response — it breaks the reusable methodology in the book into skill modules that can be triggered, executed and tested.

## What these skills solve

- You can number waves "1, 2, 3, 4, 5" but cannot say which degree the current wave belongs to — and degree is the coordinate that every entry, stop and target hangs on, so a wrong degree makes everything downstream wrong
- When buying a bottom or selling a top you only know "it has fallen a lot / risen a lot", and cannot separate "end condition met" (it may end, probe only) from "end confirmed" (it has ended, add size) — so you go heavy when you should probe, and freeze when you should add
- A correction prints three waves and then says it is not done; wave b subdivides again and again; you cannot tell whether to treat it as scissors, scythe or nunchaku, nor where the key points are
- Your stop is a round percentage instead of 1–2 points beyond the extreme of the wave you are trading, so a single spike takes you out
- Daily says long, weekly says short, and you do not know which to obey; when the structure shifts, support/resistance, stop and position size do not move with it
- You get the direction right and still lose: position size does not match structural certainty, and you keep trading when the stop distance already exceeds the target distance

## What was distilled

12 capability cards, organized in the order "fix the degree first, judge the end second, act third, do the risk math last":

- **Coordinate system**: `jingzhun-wave-levels-skill` (degree-by-degree counting and degree location: nine degrees, a completed five-wave upgrades one degree, waves 1/3/5 must each be a full five-wave at the next smaller degree)
- **Trigger criteria**: `jingzhun-end-conditions-skill` (end condition met versus end confirmed, including the end-point migration)
- **Entry capture**: `jingzhun-top-capture-skill` (impulse top capture, including extensions), `jingzhun-bottom-capture-skill` (correction bottom capture, including c-wave trading)
- **Pattern library**: `jingzhun-correction-patterns` (the correction pattern library: four base patterns plus scissors/scythe/nunchaku and strength grading), `jingzhun-complex-correction` (complex corrections and wave-within-wave), `jingzhun-triangle-trading` (triangle identification, direction/magnitude and two-stage trading), `jingzhun-combination-structure` (how combination structures form, evolve and their three futures)
- **Risk and strategy**: `jingzhun-trend-position-skill` (the four-way trend split with position sizing and certainty management), `jingzhun-multi-timeframe-skill` (large/small degree consistency and the migration of support/resistance and stops), `jingzhun-horizon-extension` (position horizon — long, swing, short — and extension profit management)
- **Integration**: `jingzhun-trade-plan-skill` (the trade plan: degree → structure → trend → entry → stop → target → size → invalidation, in eight steps)

## Two packaging modes: single and pack

The same 12 capability cards are compiled twice, at two granularities. The content is identical; the only difference is how many entries an agent can discover.

| | single (one entry) | pack (compact pack, multiple entries) |
|---|---|---|
| Discoverable entries | **1**: `wave-accurate-counting-skill` | **8**: one source router + 7 promoted standalone skills |
| Where the 12 cards live | All inside the entry's `references/capabilities/`, loaded 1–2 at a time by the router table | 7 high-frequency cards become standalone skills; the other 5 stay in the router's `references/capabilities/` |
| Triggering | Only the entry description participates in matching; routing happens after entry | The 7 high-frequency capabilities are matched directly, one hop fewer |
| Upgrades | Replace 1 directory | Replace 8 directories |

The 7 cards promoted to standalone skills in the pack:

- `jingzhun-wave-levels-skill` — degree-by-degree counting and degree location
- `jingzhun-end-conditions-skill` — end condition met versus end confirmed
- `jingzhun-top-capture-skill` — impulse top capture, including extensions
- `jingzhun-bottom-capture-skill` — correction bottom capture, including c-wave trading
- `jingzhun-trend-position-skill` — the four-way trend split with position sizing
- `jingzhun-multi-timeframe-skill` — large/small degree consistency and stop migration
- `jingzhun-trade-plan-skill` — trade plan integration

The 5 cards left in the router: `jingzhun-correction-patterns`, `jingzhun-complex-correction`, `jingzhun-triangle-trading`, `jingzhun-combination-structure`, `jingzhun-horizon-extension`.

### Which one to install

Pick by the way you work, and **install only one**:

| How you work | Recommended | Why |
|---|---|---|
| You use DSH / Codex / Claude Code with a skills directory and want a clean list | single | Takes 1 slot, loses no capabilities |
| Your daily questions concentrate on "count this wave / is this segment over / where is the top / where is the bottom / how big should the position be" | pack | Those are exactly the promoted standalone skills, matched directly |
| You distribute to several agents or teammates who pick what they need | pack | They can install only the standalone skills they want |
| You want to install once and maintain one directory | single | Upgrades replace a single directory |

> Both builds come from the same bundle and carry identical capabilities. **Installing both will double-trigger**, so pick one.

## Examples

### Example 1: the 6124 top — where do the stop and the target go?

**User question**

"The 6124 top in the Shanghai Composite is an obvious top in hindsight. How would you have known it was finished at the time, and where do the stop and target go?"

**How the skill reasons**

- First `jingzhun-wave-levels-skill`: establish which degree of impulse this top belongs to, then subdivide downward from that degree's origin and check whether waves 1, 3 and 5 are each a full five-wave at the next smaller degree
- Then `jingzhun-top-capture-skill`: lock the impulse top down to the last wave of the smallest degree and exit or short at the smallest degree's end condition; stop 1–2 points beyond the high; target the end of the next correction
- Then `jingzhun-end-conditions-skill`: separate "end condition met" (reduce or probe short only) from "end confirmed" (then add)
- If the same-degree impulse keeps taking out the prior high, treat it as an extension and move the top up

**Sample answer**

> First the conclusion: 6124 is a case where "end condition met" was later confirmed as "end confirmed" — at the time you could only act on the former. The method is to subdivide that advance down to the smallest degree and check whether the last wave has completed its five waves there. If it has, reduce or probe short at the smallest degree's end condition, put the stop 1–2 points beyond that high, and aim at the end of the next correction rather than guessing a fixed percentage decline.
>
> One conflict built into the book has to be flagged: the case gives both a "0–100 point zone above 6124" and a "stop at 6126". If you actually enter above 6126, the stop sits below your entry, which cannot be right. So there are only two fixes: narrow the entry zone to 6124–6126, or drop the price stop and use a structural stop — the level at which that degree's structure breaks. This conflict is recorded in section B (boundaries and blind spots) of the card; it is not an oversight.
>
> One more caveat: this is a post-mortem. "End confirmed" only arrives after the following structure completes. In real time you get "end condition met", which calls for a light probe, not a full-size top call.

### Example 2: price is back near the prior low — can I take a light position?

**User question**

"The c wave of this correction does not look finished, but price is already back near the prior low. Can I buy a little?"

**How the skill reasons**

- `jingzhun-bottom-capture-skill`: derive the three internal waves from the correction's degree, then shrink the bottom down to subwave (c) / sub-minuette c of the c wave; probe when the smallest c wave meets the end condition, add only when it is confirmed
- `jingzhun-end-conditions-skill`: confirmation needs two of three — a0 taking out the c-wave high, taking out the a-wave origin, or the subsequent structure validating as expected; without it the end point migrates lower
- If wave b subdivides again, the bottom moves down to c3 and the prior low is not the end
- Finally `jingzhun-trend-position-skill`: stop 1–2 points below the c-wave low, and skip the trade if the stop distance exceeds the target distance

**Sample answer**

> You can try, but accept first that this is a probe, not a bottom call. Reason: the c wave has not confirmed its end, so at best you have "end condition met" — and by the book's division of labour that position only deserves light size; adding waits for confirmation.
>
> Three steps: first, fix the correction's degree and derive how many internal waves it should have; second, shrink the bottom to the smallest degree of the c wave and check whether that smallest c wave has completed; third, put the stop 1–2 points below the c-wave low and aim at the end of the next impulse.
>
> The invalidation condition matters most, so here it is up front: if wave b subdivides further, the bottom migrates down to c3 and the "prior low" you are buying is not the bottom. So either wait for a0 to take out the c-wave high or the a-wave origin (two of three) before adding, or hold the stop 1–2 points below the c-wave low. If the stop distance already exceeds the visible upside, skip the trade — the book's own rule is that you do not trade when the stop space is larger than the target space.

## How these skills were generated

These skills were produced with the **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** RIA-TV++ pipeline, in six stages:

1. **Whole-book comprehension (Adler analysis)** — apply Mortimer Adler's analytical reading method to the book: structure, interpretation, criticism, application
2. **Parallel extraction** — several specialized extractors (frameworks, principles, cases, counter-examples, terminology) mine candidate methodology units from the source text
3. **Triple verification** — every candidate must pass three checks: at least two independent in-book supports (cross-domain), the ability to answer questions the book never explicitly addresses (predictive power), and not being common sense (distinctiveness)
4. **RIA++ construction** — structure each unit along R (quotation) / I (restatement in own words) / A1 (in-book case) / A2 (future trigger scenario) / E (executable steps) / B (boundaries and blind spots)
5. **Zettelkasten linking** — map dependencies, contrasts and combinations between cards, producing the capability index and routing table
6. **Trigger and output testing** — write trigger blind tests (including decoy questions: fire when they should, stay silent when they should not) and output evaluation scenarios for every card; failing cards go back for rework and are re-verified afterwards

The hard part in this book is the degree layer: every entry, stop and target hangs on wave degree, so the first card (degree-by-degree counting) has to be the coordinate system for the whole set, and the other 11 cards take it as input. That is why nearly every `also_read` points back to it.

## Testing and verification

This repository publishes the test material from the generation process alongside the skills: the item-by-item scoring log is `test-results.md` at the repository root — including the failures and the rework, not just the passes; the trigger and boundary cases live in each skill directory's `test-prompts.json`, and the full 51-case entry-level suite is `single/wave-accurate-counting-skill/test-prompts.json`.

- **Trigger blind tests**: 51 cases (should_trigger 25 / should_not_trigger 18 / edge_case 8). The first round scored 48 / 51; three cases were mis-routed because descriptions overlapped (for example "how do I set the stop and target near 6124" was pulled into the trade-plan card). After the descriptions were tightened and re-tested, all three hit, ending at 51 / 51
- **Decoy tolerance**: all 18 should_not_trigger cases stayed silent against the entries under test
- **Execution tests**: 12 capabilities × normal / boundary = 24 items. All 12 normal tasks completed with the required fields, and all 12 boundary tasks returned an explicit "cannot / downgrade / unconfirmed / stand aside" answer instead of forcing a confident conclusion
- **Open issues from testing**: 4 items went to needs-review — the conflict between the top zone and the stop level, the missing quantitative mapping from stop distance to position size, the different position-size bases for stocks and leveraged instruments, and the downgrade rules when data is insufficient
- **Not verified**: cross-model re-testing, out-of-sample statistical tests and live-capital backtests; none of these is claimed as proof of effectiveness

## Repository layout

```text
wave-accurate-counting-skill/
├── README.md              ← Chinese version
├── README.en.md           ← you are reading this
├── LICENSE                ← MIT
├── BOOK_OVERVIEW.md       ← stage 0 output: Adler whole-book analysis
├── DIGEST.md              ← stage 5 output: reader-facing distilled long-form essay
├── INDEX.md               ← stage 3 output: skill map + dependencies
├── verified.md            ← 12 units that passed triple verification
├── TEST_SUMMARY.md        ← stage 4 output: stress-test summary
├── CANGJIE_ADAPTATION.md  ← cangjie adaptation notes
├── GITHUB_REPO.md         ← repository metadata
├── test-results.md        ← test result records
├── candidates/            ← stage 1 output: raw candidate pool
│   ├── frameworks.md      ← framework and method candidates
│   ├── principles.md      ← principle / rule / calculation candidates
│   ├── cases.md           ← case candidates from the book
│   ├── counter-examples.md← counter-example and boundary candidates
│   └── glossary.md        ← terminology candidates
├── rejected/              ← stage 1.5 output: rejected units + reasons
├── bundle/                ← compilation source of truth
│   ├── verified.yaml      ← capability metadata, criteria and destinations
│   ├── cards/             ← capability card sources (six sections)
│   └── book/              ← overview.md + glossary.md
├── single/                ← single-mode build (one entry + all capability cards)
│   └── wave-accurate-counting-skill/SKILL.md  ← entry: triggers + routing table + loading rules
└── pack/                  ← pack-mode build (one router + 7 promoted skills)
    └── */SKILL.md         ← 8 skills, each shipping a test-prompts.json
```

## Usage

Clone the repository first:

```bash
git clone https://github.com/raphael-y7/wave-accurate-counting-skill.git
```

### Install single (recommended first try)

```bash
# macOS / Linux
cp -r wave-accurate-counting-skill/single/wave-accurate-counting-skill ~/.agents/skills/
```

```powershell
# Windows
Copy-Item -Recurse .\wave-accurate-counting-skill\single\wave-accurate-counting-skill "$env:USERPROFILE\.agents\skills\"
```

### Install pack

Copy only the directories that contain a `SKILL.md`; do not copy the two JSON files under `pack/` into your skills directory:

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

> `~/.agents/skills` is the DSH skills directory; with another agent, use its own skills directory (for example `~/.claude/skills` for Claude Code).

### How to verify the install

Ask: "Has the c wave of this correction finished, can I take a light position, and where does the stop go?" If the agent enters the `jingzhun-end-conditions-skill` and `jingzhun-bottom-capture-skill` judgement flow — separating "end condition met" from "end confirmed" and putting the stop 1–2 points below the c-wave low — instead of giving generic "mind the risk" commentary, the install works. With the single build it reads the entry first and then routes to a card; with the pack build the matching capability is hit directly.

## Sources

- *Accurate Wave Counting: Internal Structure Analysis of Wave Theory and Buy/Sell Point Handling* by 陈晓东

## Notice

This repository publishes distilled skills, indexes and rule quick references only. It contains no PDF, page images (PNG) or full-book transcript of the source book. Quotations that appear in the capability cards serve solely to attribute methodology and keep the material auditable.

All levels and numeric criteria in the book (degree symbols, the 1–2 point stop buffer, position-size tiers, and case values such as 6124 / 4778 / 2319 / 2566–2952) are case- and experience-based rules without statistical backtesting; test them on your own instruments and declare the convention you use. Nothing in this repository is investment advice.

## License

[MIT](./LICENSE)
