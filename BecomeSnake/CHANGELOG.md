# Changelog — Become the Snake

## [1.2] — 2026-09-22

Adds a deeper tier and inheritance, and removes the gate that made the mod look
broken.

### Fixed
- The basic scaled look is **no longer behind `should_show_disturbing_portrait_modifiers`**.
  That setting governs leprosy sores and plague buboes; scales do not belong in
  that company, and gating them meant any player with the option switched off
  applied the trait and saw nothing at all. The new full-reptile tier keeps the
  gate.

### Added
- **`fake_scaly_serpent`** — heavier scaling, a colder skin shift, an eye colour
  shift, `blind_eyes` for a milk-pale serpent stare, and eyebrows removed
  outright rather than merely thinned.
- **`fake_scaly_bloodline`** — the scaled look with `inherit_chance = 100` and
  `both_parent_has_trait_inherit_chance = 100`. Not genetic, since genetic
  traits cannot declare an inheritance chance; same shape as vanilla's
  `pure_blooded`.
- **Make Their Children Snakes** — applies the bloodline to existing children,
  which inheritance alone does not reach.
- Tinted icons for the two new traits.

### Changed
- All three looks are mutually exclusive via `opposites`, and the remove
  interaction clears whichever is present.

### Changed
- **All decisions removed; the mod is interaction-only.** Self-targeting works
  on interactions -- 332 base game interactions carry an explicit
  `scope:actor != scope:recipient` guard, which only makes sense because
  self-targeting is possible by default -- so the decisions were redundant. They
  were also the only part of this mod carrying version rot: every decision file
  needed a BOM, the `picture` block form, and `ai_check_interval`.
- The flavour text from the removed decisions was folded into the matching
  interaction descriptions, so none of the writing was lost.

## [1.1] — 2026-09-22

Compatibility update for **CK3 1.19 "Scribe"**. No gameplay values were changed:
the trait, interactions, and decisions do exactly what they did before.

### Fixed
- `common/traits/fake_scaly_trait.txt` and `common/decisions/BecomeSnake.txt` were
  missing their UTF-8 BOM, which meant CK3 silently skipped both files entirely.
  The trait and the decision were not functioning at all before this update.
  BOM added to both, content otherwise unchanged.
- `supported_version` raised from `1.2.*` to `1.19.*`.
- Removed `index = 702` from the trait. Manual trait indexes were dropped in
  CK3 1.4 and are now assigned by the engine.
- `common/decisions/BecomeSnake.txt` used the old CK3 1.2 `picture = "path.dds"`
  syntax. Every decision in the current base game uses the block form
  (`picture = { reference = "path.dds" }`); the flat-string form no longer
  appears anywhere in vanilla and was very likely failing to resolve the
  illustration. Rewritten to the block form for both decisions, same file
  referenced.

### Verified, unchanged
- Every key in `fake_scaly_trait.txt` (`physical`, `desc`) checked against
  `game/common/traits/_traits.info`. No modifier keys are used, so there was
  nothing to validate against the game's live modifier list. No duplicate
  keys were present.
- `common/character_interactions/00_fake_scaly.txt` checked against
  `game/common/character_interactions/_character_interactions.info`.
  `category`, `common_interaction`, `use_diplomatic_range`,
  `ignores_pending_interaction_block`, `desc`, `is_shown`, `on_accept`, and
  `auto_accept` are all still current. `is_shown` correctly scopes to
  `scope:recipient` for an interaction (decisions use bare character scope
  instead, which `BecomeSnake.txt` already did correctly).
- `gfx/portraits/portrait_modifiers/fake_scaly_modifiers.txt` checked in full
  against `game/gfx/portraits/portrait_modifiers/_portrait_modifiers.info`.
  The `usage` / `dna_modifiers` / `weight` structure is exactly the schema's
  documented shape, and every gene and template referenced
  (`gene_scaly` + `scaly`, `skin_color`, `eye_accessory` + `bloodshot_eyes`,
  `gene_eyebrows_shape` / `gene_eyebrows_fullness` + `no_eyebrows`) still
  exists in `game/common/genes/`. The block is in fact near-identical to the
  vanilla disease trait `scaly`'s own portrait modifier
  (`game/gfx/portraits/trait_portrait_modifiers/00_trait_modifiers.txt`),
  including its use of `should_show_disturbing_portrait_modifiers` inside the
  weight modifier — vanilla's own `scaly` trigger uses the same key, so it is
  a real, still-supported check, not stale script. This file needed no
  changes.

### Added
- Interaction icons (`icon_personal`, the base game's generic personal/
  cosmetic-interaction icon) and `interface_priority` on both interactions,
  so they no longer fall back to the "missing interaction" icon and sort
  predictably in the friendly-interaction menu.
- Localization for all 9 languages CK3 1.19 ships (was English only). The
  eight new languages carry English text as a clearly marked placeholder,
  which stops non-English players seeing raw keys like
  `become_scaly_interaction`.

### Known issues (not fixed — see report)
- `gfx/interface/icons/traits/fake_scaly.dds` and
  `gfx/interface/illustrations/decisions/decision_snake_gfx.dds` are not
  actually DDS files. Both are PNG images saved with a `.dds` extension
  (confirmed via file header: `89 50 4E 47` "PNG", not `44 44 53 20` "DDS ").
  The trait icon is also 1368x1272 truecolor PNG, nowhere near the base
  game's 120x120 uncompressed BGRA8 trait icon format. CK3's texture loader
  expects real DDS containers; a renamed PNG is very likely a broken/invisible
  texture in-game, independent of the version-rot issues fixed above. This is
  an art-asset problem, not a script problem, and re-encoding image data is
  outside the scope of this pass — left as-is and reported rather than
  guessed at.

## [1.0]

Initial release, targeting CK3 1.2.
