# Changelog — Council Automation

## [1.2.2] — 2026-11-19

### Changed
- Updated for the second CK3 1.21 hotfix (1.21.0.3). Regenerated from the patched game; only the
  "Generated from CK3" version line changed. The hotfix's one change to an input file is in
  `99_court_chaplain_values.txt`, and it is to Fabricate Claim's costs, not to
  `court_chaplain_conversion_factors`, so no task, trigger or card changes. The local More Game Rules
  patch is regenerated too (1.0.2), with the same header-only change.

## [1.2.1] — 2026-11-17

### Changed
- Rebuilt for **CK3 1.21** from the game's own council tasks and councillor card
  (`tools/build_council_automation.py`). The 1.20 copies would have undone 1.21's task changes and used
  removed keys (`monthly_county_control_growth_factor`, `development_level`, `change_development_level`).
- Conversion and Promote Culture prefer the county with the highest `popular_opinion`, which is 1.21's name for
  `county_opinion` (the old key no longer exists). Increase Control still prefers the highest `county_control`.
- Increase Control now targets a county whose control is below its 1.21 control baseline (or that has
  corruption), the game's own rule, instead of below 100.
- The councillor card copy follows 1.21's card, which moved the task buttons into the type
  `flowcontainer_council_position_tasks`. The checkbox is unchanged.
- `supported_version` is now 1.21.*. The local More Game Rules patch is regenerated too (1.0.1).

## [1.2] — 2026-10-14

### Added
- **A checkbox on the Court Chaplain, Steward and Marshal cards** in the Council
  window. Ticked: that councillor works on his own. Unticked: you choose his
  tasks. The setting belongs to the position, so a new councillor keeps it. It
  appears only on your own council.
- **A monthly check**: a ticked councillor who is on another task is moved onto
  his task when a county needs it. Ticking a box runs the check at once.
- **Game rule** "Council Automation: Councillors": Off (no checkboxes, no
  automation at all), On with councillors starting manual, or On with
  councillors starting automatic (default; saves from 1.1 start ticked, and
  their boxes show it from the moment the save loads).

### Changed
- The restart when a task ends now happens only for a ticked councillor, a day
  after the task ends. Moving a ticked councillor off his task by hand no longer
  trips CK3's event recursion limit.

## [1.1] — 2026-10-05

### Changed
- **Court Chaplain: faith before rite.** The chaplain now converts every county
  of another faith first, in the usual order of preference, and only turns to
  same-faith counties of another rite when none are left. Before, he could get
  stuck converting rites that a local archbishop converted straight back.
  (Thanks to the player who reported it.)

## [1.0] — 2026-09-30

First release, for CK3 1.20 "Crozier".

### Added
- Court Chaplain (Convert Faith), Steward (Promote Culture) and Marshal
  (Increase Control) start the same task on the next valid county when one
  finishes or is cancelled. Players only.
- County preference: capital, own counties, direct-vassal capitals, sub-vassal
  capitals, then the rest of the realm; highest opinion (or control) first.

### How it is built
- The three task definitions and their "may this county be targeted" triggers
  are generated from the installed game by `tools/build_council_automation.py`,
  so they carry CK3 1.20's rules exactly, plus one added hook.
- Ported from Automatic Council Tasks by Hamzah Hayat (MIT). Its three
  per-task effects became one effect with parameters.
