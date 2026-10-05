# Changelog — Council Automation

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
