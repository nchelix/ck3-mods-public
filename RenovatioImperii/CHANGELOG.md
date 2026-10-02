# Changelog — Renovatio Imperii

## [1.2] — 2026-09-28

Art only. No script changes.

### Changed
- **New Roman Claimant trait icon:** a gold imperial crown in a laurel wreath,
  replacing the placeholder. 120x120 uncompressed BGRA, like vanilla trait icons.

## [1.1] — 2026-09-24

Bug fixes found by reading a live game's `error.log`. No content changes.

### Fixed
- **The scholar's fee was never charged.** `renovatio.0004` option b used
  `add_gold = -100`. CK3 rejects negative `add_gold` outright — the log reads
  `Negative value in: {}` — so the option handed over its 50 prestige for
  free. Now `remove_short_term_gold = 100`, which is what vanilla uses to
  charge the player. (Negative `add_prestige`, used in `renovatio.0003.a`, is
  fine and unchanged; vanilla does the same.)

### Removed
- **A dead `ai_score_mult` block on `renovatio_cb`.** It added
  `frankokratia_leader_protection_value`, which does not resolve in that
  context. The block came across verbatim when the CB was adapted from
  vanilla's `imperial_reconquest_cb`, and the base game logs the identical
  error from `00_dejure_war.txt` — so this is Paradox's bug, not ours. Dropped
  rather than echoed. Its `value = 1` was the default, so AI war scoring is
  unchanged.

## [1.0] — 2026-09-23

First release. Built for **CK3 1.19 "Scribe"**.

### The idea
Vanilla treats the Roman claim as a trophy: `restore_roman_empire_decision`
requires already holding `e_byzantium` and completely controlling fourteen
Mediterranean duchies, and `imperial_reconquest_cb` requires already being
Roman emperor to use it. You win the empire, then receive the tools for
claiming it. This mod inverts that: proclaim first, fight for it after, which
is what Charlemagne, the Ottonians, the Bulgarian tsars and the Ottomans
actually did. Proclaiming grants a claim and an identity, not land. If you
cannot make it stick, you die a pretender.

### Added
- **`proclaim_heir_to_rome_decision`** — king tier or higher, `prestige_level
  >= 4`, costs 1000 prestige, and gated by `can_claim_rome_trigger`: either
  Latin or Byzantine cultural heritage, or holding a county in the old
  Empire's Mediterranean or Iberian heartland. Excludes anyone who already
  holds a Roman hegemony or the trait, so a reigning Byzantine emperor cannot
  proclaim against himself.
- **`roman_claimant`** — a fame-category trait modelled on vanilla `augustus`
  and reusing its unused art: monthly prestige and influence, vassal opinion,
  and a strong `same_opinion` between rival claimants who otherwise despise
  each other.
- **`renovatio_cb`** — adapted line-for-line from vanilla's
  `imperial_reconquest_cb`, with one change: `allowed_for_character` checks
  `has_trait = roman_claimant` instead of already being Roman emperor. Scoped
  to `custom_roman_full_borders` de jure territory so it cannot be pointed at
  Scandinavia.
- **Five named opinion modifiers** so the reaction shows up in the opinion
  breakdown with a reason instead of as an invisible number:
  `renovatio_usurper_opinion` (-40, Constantinople), `renovatio_rival_claimant_opinion`
  (-30, the HRE), `renovatio_papal_approval_opinion` (+25, conditional on
  courting the Pope), `renovatio_restorer_opinion` (+15, Latin and Byzantine
  cultures), `renovatio_presumption_opinion` (-10, decaying over 20 years,
  everyone else).
- **A six-event chain**: the proclamation itself, Constantinople's reply,
  the Pope's coronation offer, antiquarians and self-declared senators turning
  up at court, a rival AI claimant, and a judgement event that reads how far
  the claim has actually gone — pretender, regional power, or genuinely
  restored — and responds accordingly. Fired from the decision and from
  `on_action` (`on_birthday`, `on_yearly_playable`) with one-time flags and
  cooldowns so nothing refires every year forever.
- **AI proclamation**: the same decision, weighted in `ai_will_do` toward
  plausible candidates (existing emperors, high prestige, Byzantine cultural
  heritage) and hard-capped at one AI claimant at a time via a `factor = 0`
  modifier, so a rival claim stays an event rather than background noise.

### Deliberately out of scope
- **No new title.** Vanilla's `restore_roman_empire_decision` and siblings
  are untouched and still create the actual hegemony. This mod is the road
  there, not a replacement finish line.
- **No guaranteed success.** The claim can fail. That is the honest outcome
  for most rulers who reach for Rome.

### Notes on the build
- The decision's illustration is vanilla's own
  `ep3_decision_roman_restoration.dds` — the art `restore_roman_empire_decision`
  itself uses — rather than a guessed filename that turned out not to exist.
- Localized into all nine supported languages; English is fully written, the
  other eight currently carry English text pending translation.
