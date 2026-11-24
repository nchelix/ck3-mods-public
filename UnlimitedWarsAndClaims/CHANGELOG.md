# Changelog — Unlimited Wars and Claims

## [1.2] — 2026-11-23

### Added
- **No war truces** (issue #144, a Workshop request). An eighth game rule, "UWC: No war truces"
  (Off / Players / Everyone, **default Off**, so existing campaigns keep vanilla truces unless the
  player opts in). The day after a war ends (victory, defeat, white peace or invalidation), each
  qualifying participant's truces against everyone who fought on the other side are cancelled.
  The attacker's usual 5-year truce goes, and so do the both-way truces of civil and faction wars,
  for the qualifying side only. On Players the AI keeps every truce, including those it holds
  against the player. A truce's source can't be read in script, so a bought or event truce with
  someone who fought on the other side goes too; truces with anyone else are kept. Known gap: a
  great holy war's title recipient who did not fight keeps their truces with the pledged defenders.
  Faction cooldowns (`joining_faction_block`) still apply.
- Built on vanilla's own `cancel_truce_one_way` effect, hooked through the four war-end on_actions
  with the append pattern documented in `_on_actions.info`. New files only
  (`common/on_action/uwc_on_actions.txt`, `events/uwc_truce_events.txt`); no vanilla file is
  replaced and no vanilla on_action effect is overridden. A mod that adds its own truces between
  former enemies at war end will see them cancelled too. The one-day delay avoids depending on the order of
  the casus belli outcome and the on_actions in the war's last tick.
- Findings and the options considered: issue #144.

### Changed
- **New thumbnail**: a painted warlord before a burning castle (AutoSprite, picked from 24 drafts),
  in the style of Warrior Trait, Wear the Mask and Create Alliance, replacing the generic 1.0 image.
  Source in `art/unlimited_wars/`, built by `tools/build_uwc_thumbnail.py`.

## [1.1.2] — 2026-11-18

### Changed
- Rebuilt for the **CK3 1.21 hotfix** of 2026-11-18 (the game still reports 1.21.0). Two of the
  shipped vanilla copies had changed: the Scandinavian adventurer war (`01_fp1_wars.txt`) now
  gives vanilla's halved troop counts again, and the Raiktor claim war's k_epirus condition
  (`00_event_war.txt`) follows vanilla's new `NOT = { ... }` again. 1.1.1 silently undid both.

### Fixed
- **Several titles in one war** no longer applies to eleven wars whose victory can hand over only one
  title. First, six from issue #90 (all fixes in this section were present since 1.0); they keep the
  game's one-title limit, like the merchant duchy and kingdom seizures in 1.1.1:
  - the Varangian adventure (`fp1_varangian_adventurer_conquest`) and the legendary adventure
    (`legendary_adventure`): every target's counties were taken, but only one duchy or kingdom
    title was created or usurped;
  - landless adventurers' duchy, kingdom and empire invasions
    (`ep3_laamp_adventurer_{duchy,kingdom,empire}_invasion`): the defender's directly held
    counties were taken in only one of the selected realms;
  - the nomad kingdom overrun (`mpo_nomad_invasion_cb`): only one kingdom's title and duchies were
    taken.
  The landless county invasion, the nomad duchy overrun and the Scandinavian adventurer war handle
  every target and keep the rule.
- Then five more found by the release review, for the same reason. Their
  victory keeps only the last selected target and resolves that one title, so the other targets
  were not won at all:
  - the county and duchy de jure wars (`individual_county_de_jure_cb`,
    `individual_duchy_de_jure_cb`) and the imperial reconquests (`imperial_reconquest_cb`,
    `japan_imperial_reconquest_cb`);
  - the directed great holy war (`directed_great_holy_war`): the holy war and its title hand-out
    cover one kingdom.
  The "UWC: De jure wars" rule (the main de jure casus belli without Divine Right) is unchanged, and
  the nomad de jure war (`de_jure_cb_nomadic`) keeps the rule: its victory hands over every target.
  Reworking these five to handle every target is planned (issue #141).
- `01_fp1_wars.txt` and `06_ce1_wars.txt` are no longer shipped: their only changed casus belli
  are now left as the game has them. 17 casus belli files (was 19); 51 casus belli may target
  several titles (was 62).
- Wars declared under 1.1.1 keep the targets they were declared with. A multi-title war of one of
  these eleven casus belli that is already running still ends the old way.
- Tooling: `build_unlimited_wars.py --check` now also fails on a generated file it no longer
  produces, and a test fails if a casus belli that may target several titles keeps only one of them.

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
