# Changelog — Become Albino

## [1.2] — 2026-09-22

Adds inheritance and a route to the base game's own albino trait.

### Added
- **`fake_albino_bloodline`** — the same portrait change, but with
  `inherit_chance = 100` and `both_parent_has_trait_inherit_chance = 100`. Not
  genetic, because genetic traits cannot declare an inheritance chance; this is
  the same shape vanilla uses for `pure_blooded`. Declared `opposites` against
  the plain trait so a character cannot hold both.
- **Grant True Albinism** — an interaction that applies the base game's own
  `albino` trait, which did not exist when this mod was written. It is genetic
  and carries `dread_baseline_add = 15`, `same_opinion = 10` and
  `general_opinion = -10`, so it is a gameplay choice rather than a cosmetic one.
- **Make Their Children Albino** — applies the bloodline trait to every existing
  child, since `inherit_chance` only affects children born afterwards.
- A tinted icon for the bloodline trait.

### Changed
- All three looks are mutually exclusive, and Remove Albino clears whichever is
  present, the vanilla trait included.
- The portrait modifier's weight now triggers on either mod trait, so one entry
  serves both rather than duplicating the gene block.

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

Compatibility update for **CK3 1.19 "Scribe"**. No gameplay values were changed.

### Compatibility
- `supported_version` raised from `1.2.*` to `1.19.*`.
- Removed `index = 701` from `fake_albino`. Manual trait indexes were dropped
  in CK3 1.4 and are now assigned by the engine.
- Verified every key in `fake_albino_trait.txt` against `_traits.info`: the
  trait only declares `physical = yes` and a dynamic `desc`, both still valid.
  No modifiers are present, so there was nothing to check against the base
  game's modifier list, and no duplicate keys were found.
- Verified every key in `00_fake_albino.txt` against
  `_character_interactions.info`: `category`, `common_interaction`,
  `use_diplomatic_range`, `ignores_pending_interaction_block`, `desc`,
  `is_shown`, `on_accept`, and `auto_accept` are all still current, and
  `interaction_category_friendly` still exists. No duplicate keys found.
- Verified `BecomeAlbino.txt` against `_decisions.info`. `picture` is now
  documented (and exclusively used by every base-game decision file) as a
  block with a `reference` field rather than a bare path string; converted
  both decisions to that form. Every base-game decision also now carries
  `ai_check_interval` or `ai_goal`; added `ai_check_interval = 0` ("never
  checked") to both decisions, matching the existing `ai_will_do = 0` so AI
  behaviour is unchanged.
- Verified `fake_albino_modifiers.txt` against how the base game writes
  portrait modifiers today — see "Portrait modifier findings" below. No
  changes were needed.

### Fixed
- Nothing needed fixing beyond the deprecated `index`. No duplicate keys were
  found in the trait or interaction blocks.

### Added
- Localization for all 9 languages CK3 1.19 ships (was English only, across
  all three localization files). The eight new languages carry English text
  as a clearly marked placeholder, which stops non-English players seeing raw
  keys like `become_albino_interaction`.

### Portrait modifier findings
`gfx/portraits/portrait_modifiers/fake_albino_modifiers.txt` uses the classic
weighted-group pattern (`group = { entry = { dna_modifiers = {...} weight =
{ base = 0  modifier = { add = 100  has_trait = fake_albino } } } }`). This
pattern is **still live in 1.19** — vanilla's own `special_beardless_eunuch`
group in `gfx/portraits/portrait_modifiers/99_special.txt` uses the identical
structure today, with no wrapping "species" block. All three genes referenced
(`skin_color`, `hair_color`, `eye_color`) and both morph genes
(`gene_eyebrows_shape`, `gene_eyebrows_fullness`) still exist in
`common/genes/`. No changes were made to this file.

Notable: CK3 has since shipped a **real vanilla `albino` trait** with its own
entry in the newer `gfx/portraits/trait_portrait_modifiers/00_trait_modifiers.txt`
system (`group_name = { entry = { traits = {...} dna_modifiers = { human =
{...} } } }`). Its `dna_modifiers` block is byte-for-byte identical to this
mod's — same skin/hair/eye color shifts, same eyebrow morphs — strongly
suggesting the original mod author copied vanilla's own albino values in 2020.
The one structural difference in the new system is that `dna_modifiers` there
is wrapped in an extra `human = { ... }` species block; that wrapper does not
appear anywhere in the older `portrait_modifiers` folder (including the still
-current `special_beardless_eunuch` example above), so it is not needed for
this mod's file to keep working.

### Icon findings — NOT fixed
`gfx/interface/icons/traits/fake_albino.dds` does **not** match the base-game
trait icon format and was left as-is per instructions (report only, no
conversion):

| | required (vanilla `brave.dds`) | actual (`fake_albino.dds`) |
|---|---|---|
| dimensions | 120 x 120 | 516 x 504 |
| compression | uncompressed BGRA8 | DXT5 (compressed) |
| mip levels | 1 (no mipmaps) | 1 |
| header | 128 bytes | 128 bytes, but carries an embedded `IMAGEMAGICK` signature in the reserved header bytes |
| file size | 57,728 bytes | 260,192 bytes |

The icon will very likely still render in-game (CK3 accepts DXT5 and
non-square textures for many UI elements), but it does not match vanilla's
strict trait-icon spec, and its size is off by more than 4x. Recommend
resampling to 120x120 uncompressed BGRA8 in a follow-up pass, matching how
`WarriorTrait`'s icon was fixed.

### Not fixed / out of scope
- Trait icon format (see above) — reported, not converted, per instructions.
- No French/German/etc. translations were written, only clearly marked
  English placeholders, matching `WarriorTrait`'s approach.

### Observations (not gameplay bugs)
- `fake_albino`'s dynamic `desc` block has a `triggered_desc` branch (for when
  `this` doesn't exist) and a fallback branch, but both point at the exact
  same localization key, `trait_fake_albino_desc`. This makes the
  `first_valid`/`triggered_desc` wrapper functionally inert — unlike
  `WarriorTrait`, which uses genuinely different keys for the two branches.
  This isn't broken, just redundant; left unchanged since it doesn't affect
  behaviour.
- This mod fully overlaps with the vanilla `albino` trait added since 2020
  (identical portrait effect, similar concept). Not a bug, just worth knowing
  before publishing an update.

### Enhancement ideas (not implemented)
- Fix the trait icon format (see above).
- Add `interface_priority` to the two character interactions so they sort
  predictably, as done for `WarriorTrait`.
- Add an icon override or `picture` variety for the two decisions instead of
  reusing the generic `decision_personal_religious.dds` illustration.
- Give the `become_albino`/`remove_albino` interactions dedicated icons
  instead of relying on interaction-menu defaults.
- Real (non-placeholder) translations for the eight added languages.

## [1.0]

Initial release, targeting CK3 1.2.
