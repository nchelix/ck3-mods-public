# Changelog — La Grande Armée

## [1.0] — 2026-09-22

First release. Built for **CK3 1.19 "Scribe"**.

### The idea
Napoleonic warfare arriving roughly nine centuries early — not as an invincible
stack, but as a military revolution with a fuse on it.

### Added
- **`grande_armee_doctrine`** — the corps system as modifiers: movement speed
  and advantage for marching apart and fighting together, a larger and cheaper
  standing army via `men_at_arms_cap` and `men_at_arms_maintenance`,
  `knight_effectiveness_mult` for marshals, `supply_limit_mult` for living off
  the land, and `siege_phase_time` for the grand battery. The trait is also the
  key: every regiment gates on it through `can_recruit`.
- **Five regiments**, recruited and paid for like any other men-at-arms rather
  than conjured: Infanterie de Ligne (gunpowder), La Vieille Garde (heavy
  infantry), Cuirassiers (heavy cavalry), Foot Artillery (siege weapon, set to
  fight in the main phase) and Horse Artillery (archer cavalry — guns that keep
  pace with cavalry, the genuine Napoleonic innovation).
- **Proclaim the Military Revolution** — grants the character's *culture*
  `innovation_gunpowder`, `innovation_standing_armies`, `innovation_royal_armory`,
  `innovation_plate_armor` and `innovation_sappers`. Granting to the culture
  rather than the character is deliberate: the base game spreads innovations
  between neighbouring cultures, so the world militarises around you over
  decades. The advantage is a head start, not a monopoly.

### On the numbers
Calibrated against the installed game rather than guessed. The median vanilla
men-at-arms does **30** damage; the strongest recruitable units, `gendarme` and
`cataphract`, do **125**; war elephants do 250. The Grande Armée sits at
**130–175**, so it beats anything the medieval world can field while remaining
an army that a large enough coalition can grind down.

Costs are script values defined relative to vanilla heavy cavalry (×2) rather
than hardcoded, so they scale with the economy. A professional standing army is
precisely the thing feudal realms could not afford, and it should feel that way.
