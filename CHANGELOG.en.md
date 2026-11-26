# Zojuta Lite · Change Log

`[中文](CHANGELOG.md) · English`

This repository is a **criteria-layer snapshot**, not the master library. In keeping with that, this file records only this repository's own landing and changes, and makes no claim to track the master.

## 0.3.2 — 2026-11-27 (Minimal CI: only the numbers it claims)

- **Problem**: this repo had no CI; volume and entry counts were tallied by hand, so a missed edit could leave the README and the disk disagreeing with nobody noticing.
- **Change**: a single `quality-gate` job in `check.yml` judging three things — (1) `criteria/` must hold 17 volumes and 114 entries (`00-定名.md`'s `##` headings are sections, not criteria), and both READMEs must state those numbers; (2) every relative link resolves on disk; (3) no trailing whitespace, no CRLF.
- **Why only these three**: this repo is a snapshot; criterion content belongs to the main library. What can rot here is exactly "claimed numbers vs disk" and "dirty files".
- **Untouched**: 17 volumes, 114 entries, criterion text.

## 0.3.1 — 2026-11-26 (Facade completion: contribution guide added, criteria untouched)

- `CONTRIBUTING.md` added: snapshot-repo boundaries, the four-part shape of a criterion, numbers kept identical in three places, Chinese/English changed together, CC BY 4.0 attribution.
- Criteria, volumes and entries untouched.

## 0.3.0 — 2026-11-26 (one-time alignment supplement: +1 entry, 113 → 114)

- **One entry added after rewrite**: the new main-library delta was screened individually; "a failed precondition must override the conclusion" is filed in `01b`, keeping the four-part problem/mechanism/evidence/criterion structure and a redaction note.
- **Filing and counts**: `01b` moves from 9 to 10 entries; the collection remains at 17 volumes and moves from 113 to 114 entries. Both README languages and their footers are updated.
- **Boundary unchanged**: this remains a one-time, manually selected criteria-layer snapshot, not the start of automatic tracking; no runtime code is added.
- **Redaction**: tool names, internal paths, dates and reverse-traceable precise readings are removed; the method chain of overriding conclusions, checking value domains, identifying parameter sources and rewriting conclusions is preserved.

## 0.2.4 — 2026-11-25 (a Vudgio review pass; criteria untouched)

- Contrast: column heads `#948D80` (3.10:1) to `#6E6857` (5.23:1); captions `#7A7469` (4.37:1) to `#726C60` (4.91:1); card and chip strokes `#C9C2B4` / `#D6CFC0` (1.67 / 1.35) to `#858072` (3.71 / 3.43).
- Type: the generator's `%d` truncated 11.5 / 13.5 / 15.5 to integers; `%.1f` restores 12.5 / 13.5 / 15.5.
- Layout: output cards now match the left column's height (64 to 96) with text centred; inter-chip arrows 14 to 22px.
- Finish: the footer mark is drawn (stroked circle plus slash) instead of the character "✕"; both SVGs gained `title` and `desc`.
- Wording: `过三条件` to `过三道关`, `阈值自反推` to `自推阈值`.
- One narrow-screen note added under each README image (at 375 the whole diagram scales to 0.32; the table carries the content).
- The four output arrows still start right after the last step rather than at one fixed x: fixing the start left 80-100px of dead space on the short rows, which reads worse than the original 75px spread in arrow length.

## 0.2.3 — 2026-11-25 (a reader-path diagram added; criteria untouched)

- New `docs/readers-path.zh.svg` and `docs/readers-path.en.svg`: three kinds of reader, four paths, drawn as one row per path — who on the left, the two or three moves in the middle, the output on the right.
- Each README embeds its own language version right after "What none of the three should do"; licence follows the body text, CC BY 4.0.
- The diagram carries only reading moves (pick a volume, pick an entry, answer in three grades, borrow the question, derive the threshold); no project names, no entry text, no numbers. The 113 entries, their four-part structure and redaction policy: untouched.

## 0.2.2 — 2026-11-25 (entry points added to the README; criteria untouched)

- Both language versions gain three sections after "How to read one criterion": **three kinds of reader** (self-check / review / agent rule source / your own rubric), **the fifteen-minute path**, and **find the volume by situation** (a 9-row reverse lookup linking each volume).
- One copyable sample each for self-check and agent rules, both rewritten from the first entry of `02a`; the three rewrite conditions are stated: subject is "must / must not", carries a true-or-false comparison, carries no project names or numbers from this collection.
- One navigation line above the contents table: the table is organised by volume; if you have one specific thing in hand, use the situation table.
- The 113 entries, their four-part structure, volume counts and redaction policy: untouched.

## 0.2.1 — 2026-11-25 (licence changed from Apache-2.0 to CC BY 4.0)

- This collection is criteria text, not software: Apache 2.0's patent clause has nothing to license here, and the NOTICE carriage obligation only adds friction for quoters. Moved to CC BY 4.0 — commercial use still allowed, attribution and change marking unchanged (§3(a)(1)).
- `LICENSE` replaced with the official CC BY 4.0 legal code (396 lines); `NOTICE` rewritten for licence, attribution and trademark (now citing §2(b)(2)).
- The 113 entries across 17 volumes, their four-part structure and redaction policy: untouched.

## 0.2.0 — 2026-11-25 (one disciplined supplement: +15 entries, 98 → 113)

- **15 entries added after rewrite**: selected one by one from the master's §2.374–§2.393 delta;
  2 were dropped (general point already covered, rest is runtime implementation), 15 rewritten
  as "principles that stand elsewhere" and filed into volumes. Each keeps the four-part
  problem/mechanism/evidence/criterion structure plus a redaction note.
- **Filing**: `02b` +3, `01a` +3, `01b` +1, `04b` +2, `07` +4, `08` +1, `06` +1 — now 17 volumes, 113 entries.
- **Redaction**: project names, paths, internal IDs, script names, commands, field names, model names,
  dates, and reverse-traceable precise readings all removed or made relative; §2.389 and §2.390
  (same layer) merged into one.
- **Statement synced**: Chinese and English READMEs and the snapshot statement now read "baseline
  2026-11-24 snapshot, one supplement 2026-11-25, still not tracking the master automatically".
  This is not the start of tracking — it is a one-time manual selection.
- **Boundary unchanged**: still a criteria-layer snapshot, no runtime code; outward check still required before push.

## 0.1.0 — 2026-11-24 (first landing, snapshot fixed)

- **17 volumes / 98 criteria** landed, grouped by theme, under `criteria/`.
- **`LICENSE`**: the full official Apache License 2.0 text (202 lines), attributed `Copyright (c) 2026 L4ST-afk`.
- **`NOTICE`**: shipped as required by §4(d), stating what this repository is and that it contains no third-party assets.
- **`README.md` / `README.en.md`**: seven sections in the Chinese original, mirrored by seven in English.
- **`docs/cover.jpg`**: the cover image — an ink-wash hollow seven-storey brick pagoda crowned by an ancient banyan; the eight inscription lines were checked character by character against the spec in `docs/封面.md`.
- **`AGENTS.md`**: commit identity, content boundaries, and the pre-push check; states that this is a snapshot layer with no runtime code.

### Snapshot statement

The criteria are fixed at the 98 entries of 2026-11-24. Whether and when to append is a separate decision; until then this repository does not move with the master.
