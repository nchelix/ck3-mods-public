# Changelog — Allied AI War Fix

## [1.0] — 2026-10-14

### Added
- When the AI weighs an offensive war, only its **AI** allies count towards its side's strength
  (`root_military_strength_higher_than_military_target_value`); players are never assumed to join.
- Built from CK3 1.20's own `00_war_values.txt` by `tools/build_allied_ai_war_fix.py`, with only those two
  conditions added, so nothing 1.20 added is lost. A fresh build of the idea behind Allied AI Offensive War
  Fix (Workshop 3260179649, CK3 1.12), whose file predates 1.20.
