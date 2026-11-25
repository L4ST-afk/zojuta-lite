# Zojuta Lite · Change Log

`[中文](CHANGELOG.md) · English`

This repository is a **criteria-layer snapshot**, not the master library. In keeping with that, this file records only this repository's own landing and changes, and makes no claim to track the master.

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
