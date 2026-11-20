# Changelog

## 1.1 — 2026-11-19

Compatibility update for **CK3 1.21** (including both November hotfixes). Requires
Renovatio Imperii 1.1+. No balance changes: support, pledges and the uprising work
exactly as in 1.0.

- Popular support tiers use 1.21's `popular_opinion_add` (renamed from
  `county_opinion_add`). Without this, Sympathetic / Supportive / Fervent counties had
  no effect on the people's opinion of their lord. Values unchanged (−5 / −10 / −20),
  as vanilla kept its own small penalties unchanged across the rename.
- The Rise for Rome war (rally point and new capital) and Receive the Patrimony (which
  county is granted) now rank counties by 1.21's `prosperity_level`, which replaced
  `development_level`. Vanilla's landless peasant war, which the uprising is adapted
  from, made the same change.
- `supported_version` raised from `1.20.*` to `1.21.*`.
- Everything else was checked against 1.21 and still holds: effects, triggers,
  modifiers, casus belli, interaction, decision, secret and trait fields, the
  `on_birthday` and `on_title_gain` hooks, and the vanilla effects, opinions,
  traits, regions and loc keys the mod uses. No file or key collides with 1.21.

## 1.0 — 2026-09

First release. Requires Renovatio Imperii 1.1+.

- Commission a Julian Genealogy: a 1–2 year chain that makes a landless adventurer a
  Pretender to Rome, descended from Caesar or Augustus — and leaves a Forged Lineage secret.
- Popular support per county (Sympathetic / Supportive / Fervent): Bread and Games, Speak in
  the Forum, and renown. Support fades where the camp is not.
- Noble pledges: Seek Their Pledge.
- Road 1: Raise the Standard and the Rise for Rome war — an uprising of your supportive
  counties, with detachments from your pledgers.
- Road 2: Receive the Patrimony — a pledger grants you a county; you become their vassal,
  with a strong hook and an oath.
- Either road makes you Renovatio's Roman Claimant, ready for its reconquest war.
- Exposure: doubters may uncover the forgery. A young cause collapses; a legend survives it.
- Heirs of a landless pretender inherit the claim.
