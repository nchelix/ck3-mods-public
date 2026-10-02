# Changelog — OP Troops (The Immortal Army)

## [1.2] — 2026-09-22

Adds two more regiment types.

### Added
- **`op_troops_cavalry`** (base type `heavy_cavalry`, icon `heavy_cavalry`) and
  **`op_troops_archers`** (base type `archers`, icon `bowmen`). Identical stats
  to the original; the base type is what matters, since it governs how enemy
  regiments counter them and how they act in each combat phase.
- Four more spawn interactions, so each of the three regiments can be spawned
  inheritable or not. Eight interactions in total, all behind the existing menu
  toggle.

### Changed
- The men-at-arms file is now generated from one shared shape rather than three
  hand-maintained copies, so the terrain table and counter list cannot drift
  apart between regiments.

### Considered and rejected
A siege variant. The base type `siege_weapon` sets `fights_in_main_phase = no`,
so such a regiment would sit out every battle — and the existing regiments
already carry `siege_tier = 4` and `siege_value = 5`, so siege was covered.

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
the Immortal Army is exactly as strong as it was before (damage/toughness/pursuit/
screen all still 1000, stack size still 500, still free to spawn).

### Compatibility
- `supported_version` raised from `1.2.*` to `1.19.*`.
- Added the missing UTF-8 BOM to `descriptor.mod` and to
  `common/decisions/OPTroopsSpawn.txt`. Without it, the game was silently
  skipping the decision file entirely — the "Spawn Immortal Army" decisions
  did not exist in-game at all, regardless of any other content in this mod.
- `common/men_at_arms_types/optroops_regiment_types.txt`: `type = house_guard`
  is no longer a valid base men-at-arms type. `house_guard` is itself a
  *specific* regiment (`house_guard = { type = heavy_infantry ... }` in the
  base game's `00_maa_types.txt`), not one of the base archetypes a custom
  MaA can inherit from. Changed to `type = heavy_infantry`, the archetype
  `house_guard` itself now inherits from. This is the single highest-risk fix
  in this mod: left unfixed, this MaA type likely fails to load correctly.
- Same file: `can_recruit = no` replaced with `special_recruit_only = yes`.
  The base game's own schema doc (`game/common/men_at_arms_types/_men_at_arms_types.info`)
  explicitly says to use `special_recruit_only` instead of the old
  can-never-recruit pattern; `can_recruit = no` no longer appears anywhere in
  the base game. Behaviour is unchanged: op_troops was, and still is, only
  obtainable through the decision/interactions in this mod, never through the
  normal recruitment UI.
- Same file: removed `house_guard = 1` from the `counters` block.
  `counters` entries must name a base archetype (`archers`, `pikemen`,
  `heavy_infantry`, etc. — confirmed against every `counters` block in the
  base game's men-at-arms files); `house_guard` is a specific regiment, not
  an archetype, and was never a valid entry there. Removing it changes
  nothing observable, since it never validly counted against anything.
- Same file: `icon = house_guard` pointed at `house_guard.dds`, which no
  longer exists anywhere in the base game (checked
  `gfx/interface/icons/regimenttypes/`, the folder the game actually reads a
  men-at-arms icon from). Repointed to a new `immortal_army` icon shipped
  with this mod (see **Added** below).
- `common/decisions/OPTroopsSpawn.txt`: converted `picture = <bare path>` to
  the current `picture = { reference = "<path>" }` block form. Every single
  decision in the installed game's `common/decisions/` (431 of them) uses the
  block form; the bare-path shorthand this mod used is 1.2-era and does not
  appear anywhere in 1.19.
- Same file: added `ai_check_interval = 0` to both decisions. Every single
  decision in the base game (431/431, no exceptions) declares either
  `ai_check_interval` or `ai_goal` — this is apparently a hard requirement in
  the current decision schema that didn't exist in 1.2. `0` means "AI never
  considers this," which matches the existing `ai_will_do = 0` exactly, so no
  behaviour changes for the player or the AI.
- Verified `spawn_army`'s fields (`levies`, `men_at_arms { type, stacks }`,
  `location`, `inheritable`, `uses_supply`, `name`) are all still current by
  cross-referencing live 1.19 uses in `common/casus_belli_types/00_event_war.txt`
  and `common/decisions/dlc_decisions/tgp/tgp_china_decisions.txt`. No changes
  needed in either the decision or the interaction file.
- Verified every terrain key in `terrain_bonus` (`plains`, `drylands`,
  `desert`, `hills`, `mountains`, `desert_mountains`, `wetlands`, `forest`,
  `jungle`, `taiga`) against `game/common/terrain_types/00_terrains.txt`. All
  ten are still valid.
- Verified every key in `common/character_interactions/00_optroops_interaction.txt`
  (`category`, `common_interaction`, `use_diplomatic_range`,
  `ignores_pending_interaction_block`, `desc`, `is_shown`, `on_send`,
  `on_accept`, `auto_accept`) against `_character_interactions.info` and
  live base-game interactions. `interaction_category_diplomacy` still exists.
  No structural changes needed here beyond the icon additions below.

### Added
- A new icon, `immortal_army.dds`, shipped in this mod at both
  `gfx/interface/icons/regimenttypes/immortal_army.dds` (the folder the
  engine actually reads a men-at-arms type's icon from) and
  `gfx/interface/icons/character_interactions/immortal_army.dds` (the folder
  interaction icons come from). It is a byte-for-byte copy of the base game's
  `regimenttypes/heavy_infantry.dds`, matching the regiment's corrected
  `type = heavy_infantry`. The base game removed `house_guard.dds` and never
  had a house_guard-specific icon in the interactions folder at all, so this
  is a deliberate reuse of vanilla art rather than a guess at a filename.
- Icons on all four character interactions, which previously had none and
  were falling back to a default/missing icon in the interaction menu:
  `open_optroop_menu` and `close_optroop_menu` use the base game's
  `icon_combat` (matching the convention used in this repo's WarriorTrait
  mod); `inheritable_optroop_interaction` and `non_inheritable_optroop_interaction`
  use the new `immortal_army` icon.
- Localization for all 9 languages CK3 1.19 ships (was English only). The
  eight new languages carry English text as a clearly marked placeholder,
  which stops non-English players seeing raw keys like `op_troops`.

### Known issues / not fixed
- `max_sub_regiments = 100` combined with `stack = 500` is a real concern,
  not something this update touched. Per the current schema doc: "If
  positive, only one regiment of this type can be created, and have this
  maximum size." If that clamp is enforced the way it reads, a freshly
  spawned Immortal Army stack may cap out at 100 troops rather than the 500
  advertised in the decision/interaction text and tooltips, regardless of
  `stack = 500`. This may or may not have been true back in 1.2 too — it
  wasn't possible to confirm the old semantics from static files alone, and
  changing the number would be a balance change, which is out of scope here.
  **Recommend loading the mod in-game and checking the actual troop count
  after spawning before relying on the "500" flavor text.**
- The interior consistency of `damage/toughness/pursuit/screen = 1000` plus
  100 flat terrain bonuses plus counters of `1` against every archetype is
  extremely strong by design (this is an "OP Troops" mod) and was left
  exactly as-is, per instructions not to rebalance.
- `Thumbnail.png` was not touched; not evaluated for this update.

## [1.0]

Initial release, targeting CK3 1.2.
