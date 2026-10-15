# Changelog — Unlimited Wars and Claims

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
