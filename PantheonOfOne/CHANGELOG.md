# Changelog — Pantheon of One

## [2.0] — 2026-10-07

The Pantheon window.

### Added
- **The Pantheon window**, opened by the new button above your portrait, or by
  Divine Will (on a follower it opens with them selected; on yourself, The God
  tab):
  - **Followers:** every ruler of your faith and everyone who has prayed to
    you, with their skills, Devotion and blessings. Sort by Devotion or any
    skill, or show only the blessed. Pin one to bless, lend, wed or judge them
    from the window.
  - **Children:** your demigods and where each one serves or whom they wed,
    with Call home; and the houses that carry your blood, with Reveal.
  - **The God:** Worship and its income, Take the Throne, Proclaim, Forswear
    and Embrace (now confirmed first), an open oath and a spreading plague.
- **Your powers are right-click actions** that show every option at once,
  with its price, and grey out with the reason when it can't be used:
  **Bless** (all eleven blessings), **Divine Conception**, **Lend a demigod**
  and **Wed a demigod** (pick your child, and their spouse, from sortable
  lists), **Call home**, **Reveal the divine blood**, **Pass Judgement** and
  **Wrath upon their lands**.

### Changed
- **Wrath upon their lands** strikes the county you choose, not always the
  capital.
- Judging the offender of a sworn Great Prayer from the window or a
  right-click answers the prayer.
- Divine Will opens the window instead of its old pages.

### Fixed
- A demigod is only knighted where their faith allows it.

## [1.6] — 2026-10-07

Demigods as instruments.

### Added
- **Your children...** (Divine Will on a landed follower, under Bless their life):
  - **Lend a demigod** to their court for ten years, as their champion, on
    their council (the seat that fits their best skill) or as commander of
    their army. 600 Worship; the ruler gains 20 Devotion. Recall them early at
    the cost of 10 Devotion; they come home if their host dies or converts.
  - **Wed a demigod into their house:** the ruler, or an unmarried child or
    sibling of theirs. A son weds matrilineally, so the children are of their
    house. 900 Worship; the ruler gains 30 Devotion.
  - **Godsblood:** a demigod's children carry your blood in secret. **Reveal
    their divine blood** (once per house) and every Godsblood of the house
    becomes **Godsblooded** (health, every skill, prowess, fertility), and the
    dynasty gains 1,000 prestige.
- **Send one of your children** to answer a Host prayer (as commander) or a
  Spouse prayer (as their spouse), and in Divine Retribution (as the
  defender's commander).
- No one else may propose to your demigods; only you decide whom they wed.
- On a demigod, Divine Will offers only to call them home.
- **A god wears the saint's halo.**

### Fixed
- No fertility or spouse prayers while a child is already on the way, and none
  from couples past childbearing age.
- Demigods are never born sickly or inbred.
- A god's ailments now fade within a month, not a season.

## [1.5] — 2026-10-06

Great Prayers.

### Added
- **Great Prayers:** your most devout (90+ Devotion) remember who wronged them:
  a murdered parent, child, sibling or spouse; a war lost to an unbeliever; a
  holy site seized; imprisonment; torture. In their next prayer they beg you
  for vengeance against that one.
  - **Swear vengeance** and choose your wrath. Answer it and they are yours:
    Devotion 100, **Avenged by the God** (more piety and prestige) and their
    love, a thank-offering of half the wrath's cost, and twice the awe across
    the faith.
  - **Refuse:** -30 Devotion. **Swear, then stay your hand:** a broken oath,
    -60.
  - The tortured want worse: only Strike down or Maim answers them.
  - At most one Great Prayer every two years; it comes before ordinary prayers.
- A god travels in perfect safety.

### Fixed
- A god who forswore mortal offspring no longer has the occasional child.
- Divine Retribution no longer answers wars between two unbelievers over land
  holding one of your holy sites, and no longer logs errors for some wars.

## [1.4] — 2026-10-05

Wrath.

### Added
- **Pass Judgement** (right-click): turn your wrath on enemies of your faith,
  apostates who left you, and sinners and criminals among your followers.
  - **Strike the person:** strike them down, maim them (a limb, their sight,
    or a grievous wound), or curse them for ten years.
  - **Strike their lands:** Pestilence (a minor plague), The Great Dying (a
    great plague that will spread, perhaps to your own faithful), or a
    Disaster (flood, earthquake or famine by terrain, and a building falls).
  - A sin weighs less than a crime: sinners can only be cursed or maimed.
    Gods, demigods and your devout are never judged; one wrath per target
    every five years.
- **Divine Retribution:** when someone of another faith makes war on a devout
  follower or on one of your holy sites, or anyone makes war on you: smite the
  aggressor, curse their lands, send the Host, or let mortals settle it.
- **Devotion answers your wrath:** strike an enemy and your followers are in
  awe; strike one of your own and the faithful fear you while the wavering
  resent it.

### Fixed
- Error-log noise from the yearly Devotion pass, and from characters who died
  while on your Blessed or prayer lists.

## [1.3] — 2026-10-02

Prayers and Devotion.

### Added
- **Prayers:** your followers pray to you when in need, and you answer:
  **Grant** (the boon, +20 Devotion), **Send a sign** (a quarter of the cost,
  +5) or **Refuse** (-15). They ask for the Host when losing a war, Fertility
  when married and childless, a spouse and children when alone, Healing when
  sick or wounded, Vigor when old, Warding in a plague, a Harvest in debt, or a
  named divine gift. A toast tells you how each answer landed.
- **Strangers** of other faiths sometimes pray too: help them and they follow you.
- **Devotion** (0-100) for every follower, shown in Divine Will. Devout
  followers (75+) give double Worship and never leave; wavering ones (below 25)
  give none, and may turn to another faith. Your Blessed lists the wavering.
- Game rule **Prayer Frequency**: Rare, Normal, Frequent or Off.
- Demigods are born with every best gene: beauty, genius, physique and fecund.

### Changed
- **Earned Godhood boons cost three times as much** (Host 1800, gift 900,
  lands and life 600). Sandbox is unchanged.
- Worship weighting now follows Devotion instead of piety level.

## [1.2] — 2026-10-01

Divine Conception, and keeping track of your blessed.

### Added
- **Divine Conception** (Bless Their Life): a god fathers a child on a follower,
  a goddess bears one. The child is born a Demigod. An ineligible pairing costs
  nothing and says why.
- **A god's child is an honour, not a scandal:** no adultery or fornication, no
  scandalous secrets, no angry or jailing spouse (who is honoured instead), and
  the mother gains piety and opinion of you. Demigods are legitimate, of the
  god's house, and born without any negative congenital trait.
- **Your Blessed** (Divine Will on yourself): who carries your gifts, and until
  when. A divine gift shows as Gift of the God on the follower, with its
  countdown.
- **Expiry notices** when a boon fades, under the new game rule **Boon Expiry
  Notices** (All, Divine Gifts Only, Off).
- **Guardians of the Holy Seat:** a permanent regiment of divine guardians when
  you take your throne.

### Changed
- A god feels no stress.
- When you cannot afford a page of boons, one "Not enough Worship" line says so
  (CK3 shows at most three unavailable options).

## [1.1] — 2026-10-01

Divine Offspring, and a god's own menu.

### Added
- **Divine Will on yourself**, from the moment you Ascend: Take Your Throne in
  Heaven, Proclaim Your Divinity, and Divine Offspring all live here. Ascend is
  the only decision.
- **Proclaim Your Divinity:** on a branched rite, one click and it becomes a
  faith of its own, with you as its god. If a rite cannot break free, the game
  tells you to make your own.
- **Divine Offspring:** forswear mortal children, or have your children born as
  **Demigods** (gifted, beautiful and brilliant, but mortal).
- **A seasonal notification** showing the Worship gained and your total.
- A god pays nothing to convert, create or reform a rite, or hire holy orders,
  and has no puppet, holy-site or once-per-life limit on creating rites.
- The faithful adore their god; +3 personal tenet slots.
- Icons for Demigod and Divine Will.

### Changed
- Taking your throne makes you **independent**.
- Boons you cannot afford say how much Worship they need.

## [1.0] — 2026-10-01

The first release: Foundation and Boons.

### Added
- **Ascend to Godhood** and **Take Your Throne in Heaven**: become a god and the living Head
  of your faith, ruling from an impregnable Holy Seat. Founding a new faith in your own name
  first is optional.
- **Divine**: immortal, +30 to every skill and +100 prowess. No hostile scheme against you
  can succeed, and no prison can hold you.
- **Worship**, earned every season from the counties and rulers of your faith; devout rulers
  give twice as much.
- **Divine Will** (right-click a follower): grant them a divine gift (Champion, Warlord,
  Sovereign or Sage), bless their lands (harvest, walls, warding from plague), bless their
  life (vigor, fertility, a blessed lineage), or send the Host of Heaven into one of their
  wars. Every boon fades in time.
- Game rule **Divine Economy**: Earned Godhood or Sandbox God.
