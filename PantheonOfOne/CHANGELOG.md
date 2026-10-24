# Changelog — Pantheon of One

## [2.4.1] — 2026-10-23

The faith follows its god.

### Fixed
- When you found or reform a faith as the enthroned god, your faith, your head title, your devout followers (Devotion 50 or more) and your children now follow you into it, and the Great Temple's holy site moves with you (#26). The old faith is left without a head, and followers below Devotion 50 convert on the usual schedule. Put your Great Temple's county in devout hands before reforming: a holder who stays on the old faith leaves the temple dormant.
- A follower who may not marry (a monk, a priest, a betrothed) no longer prays for a spouse (#30).
- No more error.log lines when kin are murdered (#29).

### Known issue (base game)
- When a sitting Head of Faith reforms, CK3 1.20 also drops the Unreformed doctrine from the old faith and names its schism popup after the old faith ("The Old Ásatrú Schism"). Both come from the base game's own reform code, which is handed the old faith in this case; Pantheon does not change them.

## [2.4] — 2026-10-22

The god intervenes: followers can pray to be freed, raiders on holy ground answer to you, and a demigod's marriage can be ended. Tested on CK3 1.20.1.2.

### Added
- Freedom prayers: a landed follower, or one at Devotion 75 or more, held in someone else's prison prays to be freed (at most once a year). Grant it for Worship and they walk out, gain Devotion and count as Blessed; the jailer resents you for ten years.
- The Freedom Great Prayer and Bless: Freedom. A valuable prisoner or an enemy war leader of your faith can ask to be freed as a Great Prayer, at the Great price; Bless: Freedom frees any imprisoned follower you choose.
- Freeing a demigod: the new Free from prison interaction (and a Free them button on the Children tab) opens another ruler's prison for your child.
- Raiders on holy ground: when a raiding army starts on your land you are asked whether to thin it, break it, annihilate it or let it pass. A raider you strike is Marked by the god for ten years, and any raid a Marked raider starts on your land is destroyed at no cost.
- Raiders as Judgement targets: a raider who struck your land can be judged for five years.
- A raided follower's grievance: a follower whose barony is raided by anyone you do not protect (a fellow believer too) holds a light grievance, with a lighter oath and no Strike.
- Dissolve the union: end your demigod child's marriage. They come home to your court; the price and the Devotion lost depend on why (by your choice, the match went sour, the spouse left the faith), and the spouse resents it.
- The selected-follower strip: the follower you select in the Followers tab shows in a strip across the whole window, on every tab, with Change and Divine Conception buttons.

## [2.3.2] — 2026-10-21

A fix release. Tested on CK3 1.20.1.2.

### Fixed
- A widowed or divorced demigod is free again: she no longer stays "Wed into a house of the faithful", and Lend and Wed work for her.
- A god's child no longer triggers vanilla's unwed-mother or married-mother "bastard" pop-ups (Beyond All Doubt). A pregnancy whose mother or real father is a god is never a bastard pregnancy.
- A god's child shows the Pregnant trait once the pregnancy is known.
- Less error.log noise: the Wrath judgement page's tooltips no longer log missing Devotion, and gaining a title or a war ending no longer logs an undefined `title`, `attacker` or `defender` scope.
- Demigods are no longer born sickly: vanilla's reveal event could mark a god's pregnancy so the newborn fell Sickly a few weeks after birth.

### Added
- Divine Conception counts as a blessing: the follower shows as Blessed in the Followers tab for the usual blessing period.
- The Children tab says who Lend and Wed act on (the follower selected in the Followers tab), or asks you to select one.

## [2.3.1] — 2026-10-21

A clean-up release with no gameplay changes. Tested on CK3 1.20.1.2.

### Removed
- The old right-click menu pages from before the 2.0 window (the boon pages, Your Blessed, the old demigod picker).
  Players could no longer reach them; the Pantheon window and the interactions do everything they did. Their
  tooltips live on under new names, word for word.

## [2.3] — 2026-10-21

The panel release: the window gets side tabs and a Prayers tab, prayers wait for your answer, and the Children tab
becomes the place to send a demigod. Tested on CK3 1.20.1.2.

### Added
- **Side tabs.** The Pantheon window is wider (1000 px) with its tabs in a column on the left, like One Trait's
  panel: Followers, Prayers, Children, The God, Temple.
- **The Prayers tab**, with three sub-tabs, each counted:
  - **Prayers:** every open prayer, oldest first: who prays, for what, the time left and the price, with Grant,
    Send a sign, Send a child and Refuse (Turn them away for strangers).
  - **Retribution:** every open call for Divine Retribution, one per attacker, with its answers.
  - **Great Prayers:** your sworn oath: who it is for, the offender, the wrong, what fulfils it, and a button to
    pass judgement.
  The tab's button counts everything waiting.
- **A reminder while anything waits:** an alert in the row at the top of the screen lists the open prayers, calls
  and oath, and the Pantheon button shows a count badge.
- **Bide your time:** after swearing an oath, the Judgement page can be closed without acting; the oath waits under
  Great Prayers.
- Grant and Send a sign show their Worship cost again, in the event and the tab.
- **Prayers wait for you.** The prayer and Retribution events gain **Let it wait**: the prayer stays open in the
  Prayers tab. Up to six prayers can be open (Great Prayers and Great Boons are not limited). An unanswered prayer
  lapses after six months: the follower loses 5 Devotion (a stranger just goes away). A prayer that no longer makes
  sense (the follower died, left the faith, or the need is gone) closes quietly. The price is fixed when the prayer
  arrives and is shown in the event and the tab; you pay once, wherever you answer.
- **The Children tab is the demigod picker.** Send a child (from a prayer, the Prayers tab or Retribution) opens the
  Children tab with a banner: choose a child, each row shows Send (greyed with the reason when that child can't go),
  or Cancel. Closing the window keeps the choice waiting. Outside a send, each demigod row has Lend and Wed for the
  follower selected in the Followers tab.
- **A praying marker** on follower rows; click it to open the Prayers tab.
- Debug helpers (debug mod): open prayers of each kind, age and expire them, start Retribution calls, swear oaths,
  show the pending send.

### Changed
- **Great Prayer oaths keep their word.** The wrong is remembered when you swear. A torture oath is fulfilled only by
  Strike down or Maim (other wrath leaves it open). Wrath on someone else, a Judgement or a Retribution no longer
  silently ends the oath, and "Stay your hand" breaks it only on the oath's own page. If the offender dies by other
  means, the oath is released without penalty.
- Divine Retribution remembers each attacker separately: two wars at once no longer overwrite each other.

### Fixed
- Backing out of the old Send-a-child menu used up the prayer without answering it.
- Turning away a stranger's prayer showed a toast claiming "Devotion -15".

### Compatibility
- Saves from 2.2.2: a prayer or Retribution event still waiting is picked up; an oath already sworn gains the new
  rules (its wrong shows as "the wrong done to them" if it can't be recovered).

## [2.2.2] — 2026-10-20

Bug fixes and one change. Tested on CK3 1.20.1.

### Fixed
- **Imprisonment no longer errors (#5).** The imprisonment grievance hook ran even when an imprisonment had no
  imprisoner, logging errors every time. It now does nothing unless there is an imprisoner and a prisoner.
- **A Divine Conception is no scandal for the mother's husband (#6).** He no longer gets "Slept with My
  Spouse" or "Unfaithful", and no rivalry (rival, nemesis, grudge or a growing grudge) that this union caused;
  rivalries he already had are left alone. He keeps "My spouse bore the god's child". Only the secrets about
  this union's child are removed now, not the parents' other scandals.
- **The god's own spouse is left in peace (#8).** She no longer gets "Unfaithful" or "Slept with My Spouse"
  from the conception, and no longer gets the "My spouse bore the god's child" line, which was always meant
  for the mortal parent's spouse only.
- **A demigod is never a bastard (#8).** The conception now marks the child as a concubine's child and not a
  known bastard, and clears the bastard flags vanilla's pregnancy events set, at the pregnancy reveal and at
  the birth, so the god's household is not asked to legitimize anyone and does not resent it
  ("Legitimized a Bastard"). A safety net strips any bastard, wild-oat, disputed-heritage or legitimized
  brand from a demigod each month, with the opinions a legitimization cost. Known limit: if you answer
  vanilla's "name the father" pregnancy event after the day it fires, that answer is not undone.
  Known issue (#14): an unmarried follower's AI may still publicly name the god as the father (vanilla's
  "Beyond All Doubt"); the cleanup removes its Adulterer trait and opinions, and the child is unaffected.
- **Demigods no longer carry the Child of Concubine trait.** Preventing the bastard brand makes the game treat the
  child as a concubine's child, which gave a -1 Diplomacy trait; it is removed at birth and by the monthly safety
  net (existing demigods lose it too).
- **Demigods no longer leave the god's court (#12).** Every demigod carries the vanilla "blocked from
  leaving" flag, so "has no reason to remain in your Court" no longer applies. Lend, Wed, Call home and
  Send-a-child are unchanged. Not covered: a family move by the whole court, or a character event that moves
  a demigod by hand.
- **Men-at-arms flavor text (#9).** The Host of Heaven and the Guardians show a flavor line instead of the raw key.

### Changed
- **The Great Temple building shows its real tier (#7).** The five tiers are chained, so the map window badge
  reads I to V, and each tier's description says "Tier N of 5. Raise it further from the Temple tab of the
  Pantheon window." Vanilla's own gold Upgrade stays unavailable.

### Migration
- Saves from 2.2.1: on the god's first monthly tick, every living demigod gets the flag, bastard and
  legitimized brands are removed from living demigods with the "Legitimized a Bastard" opinions they caused,
  and the god's own spouses lose the "My spouse bore the god's child" line. Not recovered: demigods who
  already left, events already shown, and the "Unfaithful" and "Slept with My Spouse" opinions or rivalries
  2.2.1 already created (they cannot be traced to this mod).

## [2.2.1] — 2026-10-20

Bug fixes, and a notice when the miracles are ready. Tested on CK3 1.20.1.

### Fixed
- **The window's Worship income now includes the temple (#1).** The header showed the base income per season;
  the credit also applies the Great Temple's Worship bonus and Age of faith's doubling. Both now read one
  number, so the header matches what arrives.
- **A prayer out of debt really clears the debt (#2).** The "poor and in debt" prayer now cancels the
  follower's debt (negative gold is brought to zero; gold they have is never touched). A ruler who holds a
  county also receives Bountiful Harvest, as before; a landless one no longer shows a harvest they cannot
  have, and instead shows "Debts forgiven" for the usual blessing period. The prayer's text says which. The
  old Bless menu pages no longer offer land blessings to a landless follower, as the Bless interaction
  never did. An answered prayer is now charged exactly once, at the price its button showed.
- **Great Boon and Great Prayer recipients show as Blessed (#4).** A follower granted a Great Boon (asked or
  unasked) or whose Great Prayer you answered now carries a blessing for the usual blessing period, shown on
  their row in the Pantheon window ("Great Boon: ..., until ...", "Great Prayer answered, until ...") and on
  the Your Blessed page, counted as Blessed, and kept on your Blessed list until it ends.

### Added
- **Worship before and after (#3):** hovering any option, button or interaction that spends Worship now also
  shows your balance and what it will be afterwards ("Worship: 900 -> 300"), computed from the same price the
  option checks and charges: prayers (grant, sign, send), Great Boons, Judgement and the land wraths,
  Retribution, Bless, Lend and Wed, Divine Conception, and founding or upgrading the temple.
- **The Heavens Stir:** when the miracle cooldown ends and the Great Temple is active at its fifth tier, you
  are told once that the miracles are ready. If the temple is dormant at that moment, the notice comes when it
  wakes. Casting a miracle first cancels it.

### Notes
- No save migration. Harvest markers already on landless characters from 2.2 simply run out as before (they
  only stopped that one prayer meanwhile), and Great Boons granted before 2.2.1 are not retro-fitted with a
  blessing line.

## [2.2] — 2026-10-15

The Great Temple. Tested on CK3 1.20.1.

### Added
- **The Great Temple:** a special building the god founds on a holy site of their own faith, or their own
  capital, in five tiers (Shrine, Sanctuary, Temple, High Temple, Great Temple). Each tier costs Worship
  and takes years to build, and compounds every tier before it:
  - +10/20/30/40/50% Worship income.
  - -0/10/20/25/30% boon and Great Boon prices.
  - +0/0/1/2/3 Divine Host stacks.
  - +0/0/1/2/3 Devotion a quarter for followers whose capital is within the temple's growing range.
  - County bonuses of its own: opinion and development, piety for its holder, control growth, and a fort
    level.
- The temple never replaces a wonder; its county must be in faithful hands, or its powers sleep until it
  returns. A build under way pauses while the county is out of faithful hands
  and resumes where it left off.
- A site another god's temple is already being built on, or already stands on, cannot be taken for yours.
- **Four miracles**, once the temple reaches its fifth tier, on a shared twenty-year cooldown:
  - **Mass conversion:** every county within the temple's reach takes the god's faith at once.
  - **Age of faith:** for ten years, Worship income doubles, followers nearby gain extra Devotion, and the
    faith's fervor burns at its height.
  - **Divine victory:** every war a follower leads against an unbeliever ends in their favour.
  - **The Wrath of Heaven:** a right-click calamity on any ruler — disaster, plague and fear fall on a huge
    swath of the world around their capital, sparing the god's own domain and the temple's own county but
    no one else, not even the god's own followers caught elsewhere in the strike.
- Founding the temple on a county that is not already a holy site of the faith makes it one, where the
  faith has room for one (creation can be refused if the faith is already at its holy-site maximum), with
  its own modest holy-site bonuses.
- **The Temple**, a new tab in the Pantheon window: the holy-site list before founding, then the temple's
  tier, state, bonuses and a five-step ladder.

## [2.1] — 2026-10-13

Great Boons. Tested on CK3 1.20.1.

### Added
- **Great Boons:** the faithful may ask for six impossible gifts:
  - **Raise my house** (4,800 Worship): create the crown they are owed.
  - **Save my dying kin** (2,400 Worship): heal their kin and grant Vigor.
  - **Win this holy war** (4,800 Worship): end their holy war in victory.
  - **Give me an heir** (2,400 Worship): grant a child who follows the succession law.
  - **Bring the land to the faith** (3,600 Worship): convert their domain.
  - **Restore my fortune** (1,800 Worship): clear their debt and restore their gold.
- They may ask by prayer, or you may grant a valid request unasked from the Pantheon window. An unasked gift inspires twice the awe and has no cooldown.
- **Refuse:** the follower loses Devotion according to the size of the request.

### Changed
- Healing and Vigor keep their existing effects and now share their foundation with Great Boons.

## [2.0.1] — 2026-10-07

### Fixed
- In a game where you are not (yet) a god, the new actions' Worship checks no
  longer fill error.log with "pantheon_worship not set".

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
