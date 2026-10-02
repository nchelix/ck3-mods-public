# Changelog — Create Alliance

## [1.2] — 2026-09-22

The first release that adds features rather than just keeping the mod running.
The base game grew its own negotiated alliance interaction years ago, so this
update leans into what vanilla will not do.

### Added
- **Alliances no longer require land.** Dropped the `is_landed = yes` gate, so
  any character can be allied — courtiers, claimants, and above all landless
  adventurers. This is safe rather than a hack: the game's `is_alliance_valid`
  scripted rule has no landed or ruler requirement, it only asks for a
  qualifying bond, and `perk_negotiated_alliance_opinion` is one it accepts.
  Verified against `common/scripted_rules/00_rules.txt`.
- **Inherit Their Alliances** — allies every character the target is allied to.
  Uses `every_ally` with the same idiom vanilla uses in its own war scripts.
- **Isolate Them** — breaks every alliance the target holds, via `break_alliance`
  inside `every_ally`, again matching vanilla's own usage.

### Changed
- All four interactions now declare `interface_priority`, and Isolate Them uses
  `icon_remove_from_bloc`.
- `create_alliance_interaction`'s guard rewritten from a nested `NOT` with two
  children to an explicit `NOR`. Behaviour is identical — multi-child `NOT`
  reads as NOR — but the intent is now unambiguous.

### Not verified in game
The two new interactions iterate over a character's allies and were checked
against vanilla's own use of `every_ally` and `break_alliance`, but nobody has
yet watched them run. Worth a look before relying on them.

## [1.1] — 2026-09-22

Compatibility update for **CK3 1.19 "Scribe"**. No gameplay values were changed:
the interactions do exactly what they did before.

### Compatibility
- `supported_version` raised from `1.2.*` to `1.19.*`.
- Verified every key used in `00_create_alliance.txt` against the 1.19
  character interaction schema (`_character_interactions.info`): `category`,
  `common_interaction`, `use_diplomatic_range`, `ignores_pending_interaction_block`,
  `desc`, `is_shown`, `on_accept`, `auto_accept`, `ai_will_do`, `interface_priority`
  and `icon` are all still valid keys.
- Verified `interaction_category_diplomacy` still exists in
  `common/character_interaction_categories/`.
- Verified the effects and triggers used in the interaction bodies —
  `allow_alliance`, `create_alliance`, `is_allied_to`, `is_landed`, `is_ai`,
  `add_opinion`/`remove_opinion` — are all still present in the base game, and
  that the opinion modifier `perk_negotiated_alliance_opinion` still exists.
- Nothing needed changing here; the script was already schema-clean.

### Fixed
- `localization/german/create_alliance_interaction_l_german.yml` had its
  `# Localization by RHSoldat` credit comment ahead of the `l_german:` header.
  CK3 requires the language key to be the first line of the file, so the file
  was silently ignored by the game. Reordered so `l_german:` is line one and
  the credit comment is line two; the translated text itself was not touched.

### Added
- `icon = alliance` on both `create_alliance_interaction` and
  `break_alliance_interaction`. Neither had an icon before, so the menu was
  falling back to a missing sprite. `alliance.dds` is the same icon vanilla's
  own `negotiate_alliance_interaction` uses for the same concept
  (`gfx/interface/icons/character_interactions/alliance.dds`).
- `interface_priority` on both interactions (60 and 59) so they sort
  predictably in the diplomacy menu instead of defaulting to the bottom.
- Localization for all 9 languages CK3 1.19 ships (was English and German
  only). The seven new languages carry English text as a clearly marked
  placeholder, which stops non-English, non-German players seeing raw keys
  like `create_alliance_interaction`.

### Known issues
- None found. Unlike the trait-icon situation in WarriorTrait, this mod ships
  no custom art, so there was nothing to resample.

## [1.0]

Initial release, targeting CK3 1.2.
