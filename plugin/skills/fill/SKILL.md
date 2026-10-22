---
name: fill
description: Fill a design-workspace prototype with life-like synthetic data from a sealed domain catalog. Use when creating or changing a prototype that shows product data (tables, lists, dashboards, metrics), when the user asks for realistic or synthetic data, or after a new design is created. First fill only. Never connect to live data or GitHub.
---

# Fill synthetic data

This skill is the only allowed way to invent product data for a prototype. The steps below are hard stops, not suggestions.

Catalogs live at `${CLAUDE_PLUGIN_ROOT}/catalogs/` (from this file: `../../catalogs/`).

## Hard stops

1. **First fill only.** If the screen already has designer-accepted data, leave it. Fill empty slots only, or when the product/domain changed.
2. **Read `catalogs/index.json` first.** It is the allow-list. A domain with `ready: false` or a name not on that list does not exist. Do not invent a domain.
3. **Pick exactly one ready domain before inventing a row.** Use the spec, the conversation, and each pack’s `whenToPick`. If two ready packs could fit, **ask once**. If none fit, **stop** and say so.
4. **Read only that pack:** `domain.json`, then `screens.json` (if present), then `fields.json` (if present). Do not open another pack. Do not open GitHub. Do not call a live API. Do not use memory of a schema from an earlier chat.
5. **Use only fields, enums, and formulas in that pack.** Identifiers follow `domain.json` `identityRules` (`SYN-C-` / `SYN-U-` / `@example.edu`). Heroes that claim to describe a portfolio must match the invented portfolio.
6. **Place the disclaimer** from `domain.json` `disclaimer` on the left of the Wrapper top bar (`breadcrumbSlot`). First line only. Do not put it in a card. Do not add extra metadata on the screen.
7. **Say the choice** to the designer: `<Domain title> · <screen title>`. Example: `Insights · Course Readiness`.
8. If the designer removes the disclaimer, warn with `domain.json` `removedDisclosureWarning`. Do not put the mark back.

## Do not

- Fetch `instructure/looker-canvas-admin-analytics-v2` or any other source repo during fill
- Mix two domains on one screen
- Use a `ready: false` pack “just this once”
- Replace data the designer already changed

## After the fill

One line: what domain, what screen, how many invented rows. Then hand the preview back.
