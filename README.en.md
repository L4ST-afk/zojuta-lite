[中文](README.md) · English

<img src="docs/cover.jpg" alt="Zojuta Lite — ink-wash study of a hollow seven-story brick pagoda crowned by an ancient banyan" width="720">

# Zojuta Lite (禅院塔·籁) · a criteria set

**A set of criteria for auditing your own engineering. It doesn't hand you answers — it hands you the questions worth asking.**

> *Six sides, seven stories, weathered grey brick.*
> *Once its eaves and galleries were stripped away, the tower stood hollow and roofless —*
> *yet a banyan took root at its crown, borrowing not an inch of soil,*
> *dropping aerial roots down the hollow shaft to flourish in the wind, forming a canopy of its own.*
> *So it is taken as the method: trace its origin, demand its measurement, judge only what holds now;*
> *no borrowed rhetoric, no imposed hierarchy — everything kept must still stand elsewhere.*

This is the **criteria layer of the Zojuta main library** — a 2026-11-24 snapshot, 17 volumes, 98 entries.

The main library is not open source. Only the criteria themselves are here: which questions are worth asking, and how far you have to answer them before a question counts as answered. The runtime layer (gate implementations, self-check scripts, catalog governance, release process) stays in the main library, not in this repo.

---

## What this is, and what it isn't

**Is**: 98 criteria, each able to answer one question — *does this run of mine count as a violation?*

**Isn't**: a checklist, a template, a best-practices collection.

Worth spelling out, because it decides how you use it.

A template gives you a note to play; you play it. A criterion gives you a question to ask; you answer it yourself. Wherever a threshold or a definition has to be set from the project's own situation, this collection gives you *how to set it*, never *what to set it to*. That isn't laziness leaving blanks — it's the position. The same criteria applied to different engineering should reach different conclusions.

So you'll see a lot of sentences like:

- "The floor must be derived back from actual execution results, not copied from a document" — not "set the floor at 50"
- "Red or not depends only on whether *headroom − increment* is negative; absolute size is irrelevant" — not "leave 5% headroom"
- "Judging 'absent' must be proven by the response content itself, not supported by the request parameters" — not "query three times"

The numbers live in the evidence section, not in the criterion section. Deliberately: a criterion has to hold across projects; a number only holds at the site where it was born.

## Why it's called 籁 (lài)

籁 comes from the *Zhuangzi*, "Discussion on Making All Things Equal" (齐物论). Ziqi has finished describing the sounds of earth and the sounds of men; Ziyou asks about the sounds of Heaven. The answer:

> 夫吹万不同，而使其自己也，咸其自取，怒者其谁邪！

The wind blows, and the ten thousand hollows each sound differently — yet nothing outside them is setting their pitch. Each hollow sounds according to its own shape; the sound is its own taking. That is the sound of Heaven. *(Rendering ours; the Chinese is the source.)*

Naming a criteria set after it takes exactly that sense: **a criterion does not set the standard for your project; it makes you ask the questions your project's own shape calls for.**

`Lite` names the subtraction — criteria layer only — not a claim that it's thin. `Zojuta` is kept as-is with a suffix added: the main library's Latin name shares a `-juta` tail with a sibling library, and breaking the tail would unpair them.

## How to read one criterion

Four parts, and an entry missing any of them doesn't get in:

| Part | Answers |
|---|---|
| **Problem** | Under what conditions does it go wrong |
| **Mechanism** | Why it goes wrong, by what path |
| **Evidence** | Who measured it under what conditions, and what the readings were |
| **Criterion** | Whether this run of yours counts as a violation, and how to tell |

A complete example (first entry in [`02a-断言记账`](criteria/02a-断言记账.md)):

> **Problem**: when the execution count and the acceptance transcript come from the same derivation source, deleting an assertion and tampering with the transcript in step can still leave the check showing a pass.
>
> **Mechanism**: set two independent floor observations — an execution-count floor and a static AST call-site floor, the latter covering defensive branches that normally never execute. Both floors may only be raised, never lowered.
>
> **Evidence**: in another mutation, one assertion was deleted and the transcript edited at the same time; the execution count came in one below the floor and the call-site count one below, so it was still judged a failure.
>
> **Criterion**: if deleting an assertion and editing the transcript in step still passes the check, this run is a violation. The comparison must be against an independently set floor, not against a number the subject reports about itself.

Note the last clause — *not against a number the subject reports about itself*. That's why it can answer "does this count as a violation": it gives you an operational comparison, not an adjective.

**How to use it**: don't read front to back. Go looking with the thing you're doing right now — you just wrote a gate, go to `02b`; you're reconciling, go to `01b`; you're signing off a delivery, go to `06`. Find the entry, read its criterion, ask yourself whether this run counts.

## Contents (17 volumes / 98 entries)

| Volume | Entries | Covers |
|---|---|---|
| [`00-定名`](criteria/00-定名.md) | — | Where the name comes from (not criteria; sits at the front) |
| [`01a-阈值与对照`](criteria/01a-阈值与对照.md) | 6 | Thresholds need a physical basis; comparisons must be same-source, same-environment |
| [`01b-口径与计数`](criteria/01b-口径与计数.md) | 8 | Define the counting convention first; the measuring instrument needs checking too |
| [`02a-断言记账`](criteria/02a-断言记账.md) | 5 | Assertion-count floors, booking non-PASS results, criteria must be executable |
| [`02b-闸门设计`](criteria/02b-闸门设计.md) | 6 | A gate must be able to go red, and red must mean the world changed |
| [`03a-锚点与引用`](criteria/03a-锚点与引用.md) | 7 | Anchor validity needs a convention; an excerpt is evidence |
| [`03b-解析与切块`](criteria/03b-解析与切块.md) | 7 | Stable identity for parsed lines, structural skeleton, dedup |
| [`04a-状态真相`](criteria/04a-状态真相.md) | 6 | On disk, or an API returning 200, still isn't "in use" |
| [`04b-就绪与收敛`](criteria/04b-就绪与收敛.md) | 7 | Self-check saying ready isn't "in use"; baselines refresh only on write |
| [`05-副作用与写入安全`](criteria/05-副作用与写入安全.md) | 7 | What evidence you need before, during, and after a write |
| [`06-交付与验收`](criteria/06-交付与验收.md) | 7 | Completion has four layers; a preview passing isn't a delivery passing |
| [`07-协作与评审`](criteria/07-协作与评审.md) | 8 | Parallel seats, handoff, relay, triaging external models |
| [`08-探测与瓶颈`](criteria/08-探测与瓶颈.md) | 7 | The economics of probing: fix the shape before you talk about calls |
| [`09-迁移与归档`](criteria/09-迁移与归档.md) | 3 | Whole-tree byte-exact moves, full hash reconciliation, compute goes to the data |
| [`10-排版与渲染`](criteria/10-排版与渲染.md) | 6 | Metrics, increments, three-way comparison, end-to-end build |
| [`11-依赖与就绪`](criteria/11-依赖与就绪.md) | 5 | A name isn't an existence; conjunctive conditions need each end proven |
| [`12-文档治理`](criteria/12-文档治理.md) | 3 | Assign ownership first, derived views, goals that can't be expressed |

## Where these came from

Not thought up. Stepped in.

Every "Evidence" section is a real failure: a gate green while the thing was broken, a reconciliation that matched because both sides copied the same source, a self-check reporting ready when nothing had run, a delivery reported complete that the user couldn't open. These criteria are the scars those incidents left.

So they share one feature: **they all point at "looks right but isn't."** That's the real subject of this collection. If you remember one line, remember this one — green doesn't mean correct.

## Snapshot notice

**This repo is a 2026-11-24 snapshot: 98 entries. It does not track the main library.**

The main library is still growing (374 entries at present), and the redaction screening was done entry by entry, not as an automated pipeline. So what you have here is "what this criteria set looks like," not "the latest version."

- Criteria are method, not software. Method doesn't need to follow version numbers.
- Whether to add more later is a separate discussion. This repo makes no update-cadence commitment.
- Every entry has been redacted: project names, paths, internal ids, dates, and precisely reverse-lookupable readings have been stripped or turned into relative quantities. The numbers kept are the ones the criterion needs in order to stand.

If you find an entry whose evidence section was redacted into something that no longer holds up — all abstraction, no support for the conclusion — that's our mistake. Open an issue.

## License and attribution

**Apache License 2.0** — full text in [LICENSE](LICENSE), copyright attribution in [NOTICE](NOTICE).

Apache 2.0 rather than MIT, because it pins down two things that matter materially for a criteria set:

- **Patent grant (§3)**: contributors explicitly grant a patent licence. This collection gets applied to real engineering, and users need that certainty.
- **Attribution and change marking (§4)**: redistribution must keep the copyright notice, the full licence text and the NOTICE; modified files must carry a prominent statement of what changed.

**Attribution requirement** (how §4 lands here): when you use, modify, or distribute this, keep `Copyright (c) 2026 L4ST-afk`, keep the full [LICENSE](LICENSE) text, keep [NOTICE](NOTICE); if you changed the content and redistribute it, state at the change what you changed.

Apache 2.0 grants no trademark rights (§6) — the names 禅院塔·籁 and Zojuta Lite are not licensed along with the text.

---

**Zojuta Lite (禅院塔·籁)** · criteria-layer snapshot 2026-11-24 · 98 entries / 17 volumes
