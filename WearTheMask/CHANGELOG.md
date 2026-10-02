# Changelog — Wear The Mask

## [1.2] — 2026-09-22

Adds a fourth mask and puts the dread tiers to work.

### Added
- **`wearing_bandaged_face`** — uses the `head_bandage` template from the same
  base game gene the mask already uses, so no DLC is involved. Pure cosmetic,
  like the plain mask. Its own portrait entry and tinted icon.
- Dread conversion on the two dread tiers, using modifiers that did not exist
  when the mod was written:
  - Dread Mask: `monthly_dread`, `dread_decay_mult`,
    `monthly_prestige_gain_per_dread_add`.
  - Mask of Extreme Dread: the above at higher values, plus
    `intimidated_vassal_tax_contribution_mult`,
    `intimidated_vassal_levy_contribution_mult`,
    `knight_effectiveness_per_dread` and `tyranny_loss_mult`.
  - No existing value was reduced; all of this is additive.

### Changed
- All four masks declare `opposites` against each other, so only one can be worn
  at a time, and the remove interaction clears all four.
- The mask portrait entry lists its three wearing traits explicitly and the
  bandage has a separate entry, so the two looks never apply together.

### Note on the tgp masks
The base game also ships `tgp_chinese_face_mask` and `tgp_japanese_face_mask`
templates. They were left alone deliberately: their art may be tied to the China
and Japan content, and a mod that quietly does nothing for players without a
particular DLC is worse than one offering fewer masks.

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
the three mask traits and the decision/interaction that grant them work exactly
as they did before.

### Compatibility
- `supported_version` raised from `1.2.*` to `1.19.*`.
- Added the missing UTF-8 BOM to `common/decisions/TriggerTheMask.txt` and
  `common/traits/wear_mask_trait.txt`. Without it CK3 silently skips a script
  file rather than erroring, so this mod's traits and its decision were not
  being read by the game at all. This was the actual reason the mod appeared
  broken, not anything version-specific.
- Removed `index = 700/799/800` from the three traits. Manual trait indexes
  were dropped in CK3 1.4 and are now assigned by the engine.
- Removed `good = yes` from `wearing_dread_mask` and `wearing_very_dread_mask`.
  `good` only has an effect on genetic traits (it marks a genetic trait as
  positive for portrait/inheritance purposes); none of these three traits are
  genetic, so the key was inert. Confirmed against
  `game/common/traits/_traits.info`.
- Verified every remaining key in `wear_mask_trait.txt` against
  `_traits.info` and the base game. `physical`, `desc` and its
  `first_valid`/`triggered_desc` structure are structural trait properties,
  unchanged. `dread_baseline_add`, `dread_loss_mult`, and `dread_gain_mult`
  are still live character modifiers in 1.19 (confirmed in
  `common/modifier_definition_formats/00_definitions.txt`); dread as a system
  has changed several times over the years but these three keys survived.
  No duplicate keys were present in any of the three trait blocks.
- Verified `common/character_interactions/00_wear_mask.txt` against
  `game/common/character_interactions/_character_interactions.info`. All six
  interactions use only current keys (`category`, `common_interaction`,
  `use_diplomatic_range`, `ignores_pending_interaction_block`, `desc`,
  `is_shown`, `on_send`/`on_accept`, `auto_accept`) and
  `interaction_category_friendly` still exists as a category. No duplicate
  keys, no changes needed beyond the version bump.
- Verified `common/decisions/TriggerTheMask.txt` against
  `game/common/decisions/_decisions.info`. `title`, `desc`,
  `selection_tooltip`, `confirm_text`, `is_shown`, `effect`, and `ai_will_do`
  are all still valid decision keys, unchanged.
  `picture` was not: all four decisions used the bare, unquoted 1.2-era form
  `picture = gfx/interface/illustrations/decisions/decision_personal_religious.dds`.
  Every decision file shipped with 1.19 uses the current block form
  (`picture = { reference = "path.dds" }`) exclusively -- a repo-wide search
  of `common/decisions/*.txt` in the base game found zero remaining uses of
  the bare string form. Converted all four to
  `picture = { reference = "gfx/interface/illustrations/decisions/decision_personal_religious.dds" }`
  and confirmed that illustration file still ships in 1.19. This is a syntax
  fix only; the same image is shown, so no gameplay/visual change.

### Investigated, not changed
- `gfx/portraits/portrait_modifiers/mask_wear_modifier.txt` was checked key
  by key against `game/gfx/portraits/portrait_modifiers/_portrait_modifiers.info`
  and multiple vanilla files (`01_beards_base.txt`, `03_headgear_religious.txt`,
  `04_headgear_armor.txt`, `00_custom_special.txt`). Findings:
  - The gene `special_headgear_face_mask` and its `face_mask` accessory
    template still exist in `common/genes/08_genes_special_visual_traits.txt`
    and are still used by vanilla (Iranian/Chinese/Japanese face coverings),
    so the mask will still render.
  - All 40 `gene_bs_*` morph genes used to flatten facial features under the
    mask still exist in `common/genes/01_genes_morph.txt`.
  - The group/weight structure (`usage = game`, `dna_modifiers`, `weight = {
    base = ... modifier = { add = ... <trigger> } }`, plain `has_trait = x`
    inside a weight modifier) is still exactly how vanilla writes trait-linked
    portrait modifiers today (see `01_beards_base.txt` line 57,
    `05_headgear_situational.txt`, `99_special.txt`). No structural rot here.
  - Not changed, but noted as pre-existing and outside the scope of a
    compatibility update: the `beards`/`no_beard` accessory block uses
    `mode = modify`, which per the schema only takes effect on a character
    whose beard gene template already matches `no_beard` (it adds to existing
    strength rather than replacing the beard). Vanilla mask/veil examples
    that need to guarantee no beard shows use `mode = add` or `mode = replace`
    instead. This looks like a pre-existing logic quirk from the original
    2020 script (not something 1.19 broke), so left untouched under the
    "compatibility only" rule.
- Trait icons (`wearing_mask.dds`, `wearing_dread_mask.dds`,
  `wearing_very_dread_mask.dds`) were compared against the base game's
  `brave.dds` reference format (120x120, uncompressed BGRA8, no mipmaps, 128
  byte header, 57728 bytes). All three mod icons are ImageMagick-produced
  DDS files at 448x528, DXT1 (`wearing_mask.dds`) or DXT5 (the other two)
  compressed, with a mipmap count of 1. They do not match the vanilla trait
  icon format in dimensions, compression, or size, but were not converted per
  instructions — see report for the risk this carries.

### Added
- Localization for all 9 languages CK3 1.19 ships (was English only). The
  eight new languages carry English text as a clearly marked placeholder
  across all three localization files (`mask_event`, `mask_interaction`,
  `traits_mask`), which stops non-English players seeing raw keys.

## [1.0]

Initial release, targeting CK3 1.2.
