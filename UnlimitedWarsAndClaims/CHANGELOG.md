# Changelog — Unlimited Wars and Claims

## [1.1.1] — 2026-11-17

### Changed
- Rebuilt for **CK3 1.21** from the game's own files. The 1.20 copies would have undone 1.21's
  casus belli changes and used keys 1.21 renamed (for example `development_level`).
- 19 generated casus belli files instead of 17: 1.21's new `gdp_merchant_wars.txt` and
  `gdp_republic_wars.txt` are now shipped, so "Several titles in one war" also covers the merchant
  county seizure and three republic casus belli (62 in all, was 58). The merchant duchy and kingdom
  seizures keep the one-title limit: on victory the game hands over the counties of only one target
  title, so a second duchy or kingdom would be won without its counties. The other two new 1.21 files (`00_gdp_burgher_wars.txt`,
  `00_gdp_guelph_ghibelline_wars.txt`) have no one-title limit and are not touched.
- `supported_version` is now 1.21.*.

## [1.1] — 2026-10-26

### Added
- **Unlimited invasions.** A game rule, "UWC: Unlimited invasions" (Off / Players /
  Everyone, default Players): a qualifying attacker may declare invasions as often as they
  like, skipping vanilla's once-per-lifetime limit. A clan ruler also skips the clan
  invasion's house-unity cooldown, lifetime and pending checks, so a house-unity reward
  never leaves a player worse off than the rule alone.
  The invasion victory screen no longer warns that they cannot invade again.
- **Unlimited kingdom holy wars.** A game rule, "UWC: Unlimited kingdom holy wars" (Off /
  Players / Everyone, default Players): a qualifying attacker may declare kingdom-level
  holy wars as often as they like, and the victory screen no longer warns that they cannot
  declare another. Ordinary holy wars and great holy wars are untouched.
- **Unlimited subjugation.** A game rule, "UWC: Unlimited subjugation" (Off / Players /
  Everyone, default Players): a qualifying attacker may declare tribal subjugation as
  often as they like, and the victory screen no longer warns that they cannot do it again.

### Changed
- All seven game rule names now start with a red "UWC:" (was "Unlimited Wars and Claims:"
  in purple), so they are easy to spot in the long list of game rules.
- 17 generated casus belli files instead of 16: `00_subjugation.txt` is now shipped
  (plus `00_war_and_peace_triggers.txt`, as before). The once-per-lifetime flags are still
  set on declaration; they are harmless once the rules skip them.
- Three more hand-written scripted triggers (`uwc_unlimited_invasions_trigger`,
  `uwc_unlimited_holy_wars_trigger`, `uwc_unlimited_subjugation_trigger`).

## [1.0] — 2026-10-14

First release, for CK3 1.20 "Crozier".

### Added
- **Several titles in one war.** A game rule, "Unlimited Wars and Claims: Several titles
  in one war" (Off / Players / Everyone, default Players): a qualifying attacker may pick
  several titles as one war's objective, where the casus belli normally allows one.
- **Several claims in one war.** A game rule, "Unlimited Wars and Claims: Several claims
  in one war" (Off / Players / Everyone, default Players): a qualifying attacker presses
  several claims in one war without Chronicle Writing (own claims) or Divine Right
  (claims for others).
- **De jure wars.** A game rule, "Unlimited Wars and Claims: De jure wars" (Off /
  Players / Everyone, default Players): a qualifying attacker may use the de jure casus
  belli without Divine Right.
- **War with raised armies.** A game rule, "Unlimited Wars and Claims: War with raised
  armies" (Off / Players / Everyone, default Players): a qualifying attacker may declare
  war while their armies are raised, as long as none stands in the defender's lands --
  the game's own rule for the governments allowed to do this.

### How it is built
- The 16 affected casus belli files and `00_war_and_peace_triggers.txt` are generated from
  the installed game by `tools/build_unlimited_wars.py`, so they carry CK3 1.20's rules
  exactly, plus four hand-written scripted triggers (`uwc_shared_titles_trigger`,
  `uwc_multiple_claims_trigger`, `uwc_dejure_wars_trigger`, `uwc_raised_armies_trigger`)
  that read the four game rules above.
- A fresh build of the idea behind Allow Multiple Claims and Unlimited Wars
  (Workshop 2453372701); none of the original's files are used.
