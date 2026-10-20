# Changelog — One Trait to Rule Them All

## [2.9.2] — 2026-10-20

Tireless Armies now really means tireless, and a new Army toggle, Swift Armies, gets the armies there.

### Added
- **Swift Armies**, a toggle beside Tireless Armies on the Army tab: embarking costs 90% less (the game's minimum is a tenth), +100%
  land and naval movement speed and +100% winter movement. The no-penalty-after-landing and river and strait bonuses go
  to the armies' commanders and are renewed monthly, so a newly assigned commander may wait up to a month. It applies
  to all of the character's armies and adds harmlessly to Supreme Commander.

### Changed
- **Tireless Armies covers terrain and supply.** On top of no hostile-county attrition and the longer supply, it now
  removes terrain attrition and the supply penalty of every land terrain, and tops every army's supply up to full when
  you grant it and then every month (the game pulses each army every 30 days). Characters who already have Tireless
  Armies get the stronger version automatically, with nothing to redo.
- **Still not covered:** sieges and looting keep their usual 1% a month, since the game gives no way to change them. The
  refill restores supply, not men already lost.
- The Army tab's toggle list is tall enough to show all six toggles without scrolling.

## [2.9.1] — 2026-10-19

The ring army gets a strength setting and a size, a new Army toggle gives it supply, and four Vassals rows act on you.
A player asked for longer battles; Regular troops are the answer.

### Added
- **Ring army strength: Godlike, Elite or Regular.** Three buttons on the Army tab, the current one highlighted.
  Godlike is the army you know, unchanged. Elite is about three times a vanilla best of its kind, Regular only a
  little above it, so battles last. Each level has its own troop types (nine in all) and its own art: Godlike gold,
  Elite blued steel, Regular iron and red. A character with no setting is Godlike, exactly as in 2.9.
- **Count.** A stepper on the Army tab (-1000 / -100 / +100 / +1000, from 100 to 50,000 men, 5,000 by default) sets
  how many men the three raise buttons create. The readout shows the real figure for the level, so Count 100 on
  Godlike reads 500 (whole companies, rounded up).
- **Tireless Armies**, a toggle beside Free and Unlimited Men at Arms: no hostile attrition (raiding included), much
  longer supply, bigger supply limit and capacity. It applies to all of the character's armies and adds harmlessly to
  Supreme Commander.
- **Four Vassals rows that act on you**, on another ruler's panel: become their vassal, break free from them, become
  their tributary, stop paying them tribute. Each greys with a reason when the game would refuse it (their own vassal,
  a lower tier, not your liege, already a tributary).

### Changed
- **The raise buttons create the current level and Count** (Legion, Bowmen, Riders), not a fixed ten companies.
- **Disband covers all nine ring troop types.**
- **Changing level converts the ring regiments** the character holds to the new level, refilled to full strength.
  The level buttons grey ("Send your ring armies home first.") while any ring regiment is raised.

### Credits
- Longer battles: a player's request.

## [2.9] — 2026-10-19

Diplomacy, Summon and Puppets move into the panel, and the event menu retires: right-clicking a character now
opens the panel on them.

### Added
- **A Diplomacy category** with five tabs: Alliances (ally, inherit their alliances, isolate them, end an
  alliance), Vassals (vassal, release, tributary, free from tribute), War & Peace (white peace, win every war
  between you, five-year truce, erase truces), Relations (strong hook, friend, best friend, end a rivalry,
  adoration) and Hostility (strike dead, imprison, free, banish, excommunicate, lift excommunication). It is
  between you and another living character, so on yourself it shows a single line saying so.
- **A Court tab under Realm** (Realm now has eight tabs): summon a master Chancellor, Marshal, Steward,
  Spymaster or Court Chaplain, a champion, a spouse candidate or a gifted ward into the court of whoever the
  panel is open on.
- **Puppet rows on the Puppets tab.** On another character: make them your Secular Ruler, Clerical Ruler or Realm
  Priest puppet, or release them. Your own puppets list stays below, with its Release buttons.
- **Confirm on four permanent Diplomacy actions.** Inherit their alliances, Isolate them, Strike them dead and
  Excommunicate them arm on the first click ("Confirm?") and apply on the second; clicking anything else, or
  switching the panel to someone else, cancels.
- **Every Diplomacy and puppet row greys with a reason on hover** when the game would refuse it (a new alliance
  while at war, ending an alliance that rests on marriage or close family, a tributary of someone else, a best
  friend who is a rival, a vassal of an equal or higher title, and so on), instead of clicking and doing nothing.

### Changed
- **Right-click opens the panel.** The "One Trait" right-click entry now opens the panel directly on whoever you
  clicked, yourself included. The event menu is gone: its Open the panel, Puppets, Summon, Diplomacy and Close
  pages have all moved into the panel. Give a title and Marry are unchanged.
- **Summon uses the court owner's court.** The summoned character joins the court of whoever the panel is open
  on, with that ruler's culture and faith, and a master councillor takes that seat on that ruler's council at
  once, when their government has that seat; the row greys with a reason for a mercenary company, holy order,
  landless adventurer or herder, and for the nomadic and landless-adventurer limits on four of the five seats. On another ruler this no longer touches your own court or council.

## [2.8] — 2026-10-18

The event menu's Character pages move into the panel's Character category, which now has five tabs.

### Added
- **Five Character tabs**: Stats, Identity, Traits & Looks, Family and Legacy. Stats keeps the steppers and
  gains **Stress** (-100 / -10 / +10 / +100, with the current stress shown). The other four hold the moved
  menu options as action rows, each with an icon, a label and one button: Identity (culture, faith and name
  swaps), Traits & Looks (perfect genetics, cleanse, personality, coping, hereditary looks), Family (heir,
  adopt, disown, court) and Legacy (legend, glory, relic and the seven Canonize rows).
- **Confirm on permanent actions.** Disowning, giving or taking hereditary looks, and every Canonize row arm on
  the first click ("Confirm?") and apply on the second; clicking anything else cancels.
- **Canonize rows name the relative** (their father, mother, grandparents and house founder) beside the button.
- **Hover text** on the trait bundles and the Canonize and looks rows says what they do.

### Changed
- The event menu's Family, Character Editor and Modern Systems pages have moved into the panel and left the
  menu. Right-clicking now offers Open the panel, Puppets (on others), Summon (on yourself), Diplomacy (on
  others) and Close.
- Options that used to vanish once done (already their heir, already your culture, already a saint, and so on)
  now stay on the page greyed out, with the game's own reason on hover.
- Rows that can never apply are hidden: give and take rows and every Family row on yourself, "Adopt your
  capital's culture / faith" on yourself, and a Canonize row whose relative does not exist.

## [2.7.1] — 2026-10-15

### Added
- **Prestige, Piety and Renown** on the panel's Character page, each with the usual four buttons (-1,000 / -100 /
  +100 / +1,000). Renown is the character's dynasty's; a lowborn character has none to change.

### Fixed
- **Free Men-at-Arms now covers every currency.** It only made gold upkeep free, so a tribal ruler still paid
  prestige for their men-at-arms (and warrior monks still cost piety). It now frees the upkeep and recruitment of
  every men-at-arms type, whatever it is paid in (the game prices them in gold, then converts).

## [2.7] — 2026-10-14

The event menu's Succession, Titles, Culture, Buildings and Modern Systems: the Realm pages move into the
panel's Realm category, and refused governments grey out.

### Added
- **Five new Realm sub-tabs**, alongside Government and Laws: Succession, Titles, Culture, Buildings and
  Realm events. Each lists the moved menu options as generated **action rows** -- an icon, a label and one
  button per action -- plus three scrolling lists: Titles' "Their titles" (every county-or-higher title
  this character holds, highest tier first, each with Take -- which brings its vassals -- Claim and
  Destroy), Buildings' "Choose a
  county" (max its buildings, or add a building slot) and Realm events' "Plague a county".
- **Confirm on permanent actions.** Taking an entire realm, destroying a title, finishing every
  great project, releasing all tributaries, upgrading a domicile and unleashing the plague all arm on the
  first click ("Confirm?") and apply on the second; clicking anything else cancels.
- **Refused governments grey out**, with the game's own reason shown on hover, instead of silently applying
  a government CK3 would never let that character hold.

### Changed
- The event menu's Succession, Titles, Culture, Buildings and Modern Systems: the Realm pages have moved
  into the panel and left the menu (Modern Systems: the Character stays).
- Succession now acts on the panel's own character, not always on the player: open the panel on anyone
  landed to change THEIR heir, authority, crowns and creatable titles.
- Titles take, claim or destroy any one of a character's titles, not only their primary.
- Raise and Lower authority are free: no prestige cost and no law cooldown.
- Finish every great project greys out when they have none under way, and Plague greys out on a county
  that already has an outbreak.
- Destroy their primary title: a duke or higher loses it as before; a count's county (which CK3 cannot
  destroy) goes to their liege, or to you if they are independent -- a count with no other county becomes
  landless.
- Max buildings fills the free slots the game itself would build in; a slot added with Add slot is yours to
  build in.

### Fixed
- Switching between the administrative governments (administrative, celestial, meritocratic, steppe
  administrative, Ritsuryō) did nothing once the ruler already had one of them; the switch now also
  converts the estate and the noble-family title the way the game does for that government, for the ruler
  and for their administrative vassals.
- Max buildings fills the slots its own upgrades open (an upgraded holding gains slots the first pass
  could not see), so a county is full after one click.
- Upgrade the domicile builds each tier in turn; it used to fail, since the game will not build a top tier
  over an empty one.
- Take every title and Pressed claims on all their titles no longer try to move or claim capital baronies
  (the game refuses them; the county already carries its baronies).

## [2.6] — 2026-10-13

The panel grows a sidebar, and the first menu pages move into it.

### Added
- **A sidebar.** The One Trait panel's tabs are now categories down the left
  side, with the content on the right: Character, Traits, Realm, Sanctum, Army
  and Puppets. The window is wider.
- **Character:** age, gold, court grandeur, influence, merit and legitimacy, each
  shown with its current value and four buttons, two steps down and two up.
  An adult never drops below 16. A child stepped to 16 comes of age for
  good, so that step asks for a second click. Court grandeur needs a royal
  court.
- **Realm**, for landed rulers:
  - **Government:** all fifteen governments in one list, the current one
    marked. A second click on the same row confirms the change.
  - **Laws:** the six succession laws and five gender laws, the current ones
    marked, applied with one click.

### Changed
- The menu's Government, Succession law and Gender law pages, the Body page's
  four age presets and Modern Systems' grandeur, influence, merit and
  legitimacy options have moved to the panel and left the menu.
- Laws can now be changed for any ruler the panel is open on, not only for
  yourself.
- You can make yourself a Theocracy (playable since CK3 1.20).
- Each succession law is offered to every government the game itself offers
  it to, where the menu page was open to feudal and tribal rulers only.

## [2.5.1] — 2026-10-13

CK3 1.20.1.

### Changed
- The generated war and puppet files follow two small changes in CK3 1.20.1: the
  Frankokratia leader protection in three wars' AI scores, and one puppet
  type's priority.

## [2.5] — 2026-10-07

The One Trait panel.

### Added
- **The One Trait panel**: a window opened by the new round button beside your
  portrait (on yourself) or from the menu's first option (on whoever you
  right-clicked). Four tabs:
  - **Traits:** all 21 traits as rows with their icons, each switched On or Off
    with one click, plus Remove every trait.
  - **Sanctum:** raise it, tear it down, and wake or still each of its eleven
    powers, with new painted icons. Locked until the Sanctum stands. Invoke
    every power now.
  - **Army:** Supreme Knights, Unlimited Knights, Unlimited and Free
    Men-at-Arms as switches; raise the Legion, Bowmen or Riders; disband them.
  - **Puppets:** each of your puppets with its portrait and type, and Release.
- **Give a title** (right-click): any title you hold except your primary,
  picked from a list. Never to anyone above you.
- **Marry** (right-click): any of your unmarried family to any of theirs,
  from two lists showing only those who can wed; a child is betrothed;
  optionally matrilineal.

### Changed
- The menu's Traits, Army and My Puppets pages, and Buildings' Sanctum page,
  now open the panel. Titles' three "give" options and Family's marry and
  betroth options became the two new actions.

## [2.4.2] — 2026-10-02

Canonize.

### Added
- **Canonize a relative** (Character Editor): make any of the right-clicked
  character's departed kin a saint of their own faith: father, mother,
  grandparents, house founder or dynasty founder. Uses the game's own
  canonization (By God Alone): the Saint trait, sainthood in the faith, and
  relics from their remains.

## [2.4.1] — 2026-10-01

Scourge of the Gods.

### Added
- **Become the Scourge of the Gods** (Modern Systems, The Realm): the vanilla
  conquest with the game's Scourge of the Gods modifier guaranteed. Vanilla
  only ever grants it to AI conquerors.

### Changed
- **Become a Conqueror** now rolls for Scourge of the Gods with the Conqueror
  Bonuses game rule's odds, as vanilla does for AI conquerors: never on Default
  or None, 5% on Random, 0.5% on Reduced Random, always on Extreme.

## [2.4] — 2026-10-01

Government and Summon.

### Added
- **Government** (Modern Systems, on any landed ruler): make them Feudal, a
  Clan, Tribal, Nomadic, Administrative, Ecclesiastical, a Republic or a
  Theocracy, or one of the regional governments: Celestial, Meritocratic,
  Ritsuryō, Sōryō, Mandala, Wanua or a Meritocratic Khanate. Their tribal,
  nomad and herder holdings convert to suit, and their landed lay vassals
  follow them; cities, temples and churches are untouched. Administrative
  and its relatives come with estates, noble families and governors, as the
  game's own conversion does. Republic and Theocracy are never offered on
  yourself, since the player cannot play them.
- **Summon** (on yourself): a master Chancellor, Marshal, Steward, Spymaster
  or Court Chaplain, seated at once; a champion; a spouse candidate; or a
  gifted ward. Each joins your court, of your culture and faith.

## [2.3] — 2026-10-01

Hostility, Culture and Court.

### Added
- **Hostility** (Diplomacy, on someone else): strike them dead (they die
  "under mysterious circumstances", with no murder secret, tyranny or crime;
  never offered on your heir), throw them in your dungeon or free them from
  any prison, banish an unlanded courtier or guest, excommunicate them, or
  lift their excommunication.
- **Culture** (Modern Systems, on anyone): unlock every innovation of a
  culture's current era and the eras before it, or of every era. Regional and
  culture-specific innovations are left out. Full cultural acceptance between
  your culture and theirs, both ways.
- **Bring them to my court** on the Family page, for anyone unlanded, from
  any court.

## [2.2] — 2026-09-30

Diplomacy.

### Added
- **Diplomacy** (on someone else), in four pages:
  - **Alliances**, everything from the Create Alliance mod: ally with
    anyone, landed or not; inherit their alliances; isolate them; end your
    alliance.
  - **Vassals and Tribute:** make them your vassal (no war, no acceptance,
    even from another liege), release a vassal, make them your tributary,
    or free them.
  - **War and Peace:** white peace in all their wars, win every war you are
    fighting against each other, a five-year truce, or erase your truces.
  - **Relations:** a strong hook, friend, best friend, end a rivalry, or
    make them adore you.
  - Ending an alliance or freeing a tributary takes effect at the start of
    the next day; the option hides at once and its tooltip says so.
- **Marriage** on the Family page: marry or betroth them to you or to your
  heir, whatever their faith or rank. Nobody already married or betrothed is
  offered.

## [2.1] — 2026-09-30

Titles and Succession.

### Added
- **Titles** (on someone else): take their primary title, every title they
  hold, or their whole realm; destroy their primary title; give yourself
  pressed claims on all their titles; or give them up to three of your own
  titles. There are no penalties, so it doubles as revoke.
- **Succession** (on yourself): any succession law (for feudal and tribal
  realms) and any gender law; **My heir takes everything** (primogeniture,
  and no elective titles); raise or lower your authority one step at a time;
  be crowned or anointed; and create every title you qualify for at once.
  No waits, no costs.

## [2.0] — 2026-09-30

One right-click, one menu, and Puppet Master.

### Changed
- **Right-click shows one entry: One Trait.** It opens the menu on whoever you
  clicked. Embrace and Finish Embracing, and the forty-odd right-click options
  they unlocked, are gone; everything they did is in the menu.
- **Traits** is now three pages: Body and Mind, Riches and Renown, and Rule and
  War, holding all twenty-one traits, plus **Remove every One Trait trait**.
- **Army** gains the knights and men-at-arms toggles.

### Added
- **Family**: designate someone your heir, adopt them into your house, or
  disown them.
- **Puppet Master** (By God Alone): make a ruler your Secular Ruler Puppet, or
  any clergy your Clerical Ruler or Realm Priest Puppet, whatever your faith,
  even someone else's puppet. Then act through them from the game's own
  puppets row when you right-click anyone.
- **My Puppets**: right-click yourself to see the puppets you hold, release
  any of them, or release them all.
- Family and Puppets only appear for someone other than yourself, and
  Puppets only when they could be one.

### Updating from 1.x
- Traits and bonuses already on your characters stay. Only the way you reach
  them has changed.

## [1.11] — 2026-09-30

The Wars of the One.

### Added
- Five casus belli of your own, for anyone with the One Trait. They cost
  nothing, need no border or claim, and ignore the usual bans on
  theocracies, tributaries and pacifists:
  - **Conquest of the One**: any title at any tier, anywhere. Win it, plus
    every county you occupy, half their gold, and their family in your
    dungeon.
  - **Subjugation of the One**: they keep their land, but they and all their
    vassals become yours.
  - **Tribute of the One**: they become your tributary.
  - **Ransom of the One**: no land changes hands; they pay five years of
    income, owe you a strong hook, and their family are your prisoners.
  - **Blitz of the One**: Conquest, fast. Your levies and regiments refill as
    you declare, war score climbs from your first siege, and taking their
    capital wins it.
- Each war has its own icon.

### Changed
- The One Trait War is now Conquest of the One: any tier instead of kingdoms
  only, and no longer limited to your borders. Wars already under way carry on.

## [1.10] — 2026-09-30

Chosen of God, for By God Alone.

### Added
- **Chosen of God**, a new trait on the menu's Traits page:
  - spiritual fulfillment set to the top the moment it is granted, and it
    never falls: calm, protection from hostile schemes, and every perk
    the top level unlocks;
  - four personal tenets instead of one;
  - every level of piety pays: +3 to every skill and +50% stress
    loss per level;
  - converting your faith, founding a rite and hiring holy orders cost
    nothing;
  - clergy, zealots, your religious head and religious vassals adore you.

## [1.9] — 2026-09-29

The Army of the One.

### Added
- Three elite men-at-arms regiments, each overwhelming in its own way:
  - **Legion of the One** (infantry): cannot be killed, and takes castles.
  - **Bowmen of the One** (archers): the most raw damage on any field.
  - **Riders of the One** (heavy cavalry): nothing that flees survives.
- All three counter every troop type in the game, cost nothing, and come
  with their own art.
- Anyone with the One Trait can recruit them, free, from the game's own
  Men-at-Arms panel. The new **Army** page in the One Trait menu grants a
  full regiment of 5,000 at once, or disbands them all.
- They are ordinary regiments: they reinforce, and pass to your heir.
- **The gilded host** (experimental): an army made mostly of One Trait
  regiments marches on the map in white and gold, whatever its culture.

### Changed
- Updated for **CK3 1.20 "Crozier"**.

### Fixed
- The One Trait War casus belli no longer logs an error on load: it carried
  `min_ai_score`, a setting the game has not accepted for years.

### Removed
- The right-click "Spawn an Army of the One Trait". Armies already spawned
  in your saves keep working.

## [1.8] — 2026-09-29

Each trait does one thing.

### Changed
- **Unlimited Fame and Glory** is split in two. **Unlimited Wealth** keeps
  the gold: income and tax tripled. The new **Unlimited Fame** takes
  prestige, dynasty renown, piety, legitimacy, influence and merit.
- **Supreme Manager of the Realm** keeps ruling and court: county control,
  opinion, development, grandeur, artifacts, free titles. The new **Master
  Builder** takes construction: every building and holding at once, now
  free in gold, piety and prestige, and domiciles too.
- **Supreme Commander** no longer carries travel safety; that belongs to The
  Wanderer's Road.

### Added
- A **Traits** page in the One Trait menu: Unlimited Fame, Master Builder,
  and Blessing of the Horde and The Wanderer's Road, moved from The Realm
  page.

### Fixed
- Domiciles were built **twice as slowly**, not twice as fast, from 1.3 on:
  `domicile_build_speed` is a construction-time modifier, and the trait set
  it to +100%. Master Builder now makes domicile construction instant.
- Master Builder's tooltip read -10000%; its values are now written as the
  game writes them (-100%). The effect is unchanged.
- The Supreme Manager interaction no longer promises fast buildings.

### Existing saves
- A character who had Unlimited Fame and Glory now has only Unlimited
  Wealth, and a Supreme Manager no longer builds for free. Add Unlimited
  Fame or Master Builder from **One Trait menu → Traits**.

## [1.7] — 2026-09-29

A Buildings menu, and a wonder that does things.

### Added
- **Buildings → Construction**: max every building in the capital county,
  the whole domain, or the whole realm (vassals included); fill every empty
  barony with a holding; add building slots to the capital; max duchy
  capital buildings; finish every great project; rebuild ruined great
  buildings.
- The "max" cheats are generated from the installed game's own building
  files by `tools/gen_building_upgrades.py`, so they cover every building
  chain, DLC ones included, and are re-generated after each patch.
- **Buildings → The Sanctum of the One**, a special building only One Trait
  can raise. It makes its county unassailable and wakes eleven powers you
  switch on and off one by one:
  - **Builder**: The Realm Builds Itself, Golden Age
  - **Dominion**: One Faith, One People
  - **The Eye**: All-Seeing, The Leash, No Dissent
  - **The Forge**: Relic Forge, Hall of Champions, Eternal Levies
  - **Tribute**: World Tribute
- The Sanctum passes to your heir with its powers, pauses them if its
  county is lost, and never replaces an existing wonder.
- You can see the Sanctum work: each power reports in your message feed
  when it acts (how many counties, secrets, hooks, how much tribute), the
  Situations list shows where it stands and which powers are on, and
  **Invoke every awakened power now** runs them all at once.
- The Sanctum's powers are grouped on one page per school (Builder and
  Dominion, The Eye, The Forge and Tribute), each explaining its powers.
- New art: a painting of the Sanctum for its story in the Situations list,
  and a silhouette building icon in the same style as the game's own
  wonders.

## [1.6] — 2026-09-28

Every trait now reaches the systems CK3 has added since 2020.

### Added
- **Blessing of the Horde**, a new trait for nomads: herds grow three times
  larger and faster, pastures regrow and never wear out, and the horde hits
  harder.
- **The Wanderer's Road**, a new trait: very fast, safe travel for anyone,
  and for landless adventurers, a camp that never runs out of provisions and
  pays gold, prestige, piety and influence every month.
- **Become a Conqueror** starts CK3's own conquest story: the Conqueror trait,
  vassals offering armies and gifts, and the conqueror casus belli.
  **End the conquest** stops it with no penalty.
- All three are on the menu under Modern Systems → The Realm.

### Changed
- **Unlimited Fame and Glory**: monthly influence and merit (flat and
  multiplied), +3 merit levels, +10 legitimacy a month, triple income and tax.
- **Unnatural Long Life**: immune to epidemics and other disease, +100 years
  of life expectancy, healthy in old age.
- **Ultimate Schemer**: contracts and political schemes are instant, ten
  more contract slots, enemy schemes capped at 0%, and agents always join.
- **Completely Loveable**: long-reign opinion builds twice as fast; your
  legends spread six times as fast.
- **Unlimited Dread**: tyrannical acts cost no tyranny.
- **Endless Fertility**: children inherit good genetic traits, with no
  inbreeding.
- **Supreme Manager of the Realm**: court grandeur climbs, artifacts never
  decay, and creating titles costs no gold or piety.
- **Supreme Commander**: no army upkeep or recruitment cost, and free,
  penalty-free landings.

### Fixed
- **Remove One Trait** left Ultimate Schemer and Celibate behind. It now
  removes every One Trait trait.

## [1.5.1] — 2026-09-28

### Fixed
- **Unlimited Dread** barely raised dread. It set a dread target of +200 but
  current dread only drifts toward its target by 0.5 a month, so reaching the
  cap took around eight years. The trait's `monthly_dread = 100` shows in the
  tooltip but the engine does not apply it. Granting the trait now sets dread
  to 100 at once, and a +4000% dread gain replaces `monthly_dread`, so any
  dread lost to events comes back within months. Characters who already have
  the trait catch up the same way.
- `dread_loss_mult` read `-100` (-10000%) where `-1` (-100%) was meant.

## [1.5] — 2026-09-28

All-new artwork. Every icon in the mod was made for it; none is base-game art
any more.

### Changed
- **Traits** — all 16 trait icons are new, as framed square tiles: a gold
  eight-point star behind a round medallion, each trait with its own emblem
  and centre colour. The same art is the grant interaction's icon.
- **Menu actions** — every other interaction is a new round medallion:
  knights, men-at-arms, the army, the family actions, and the menu itself.
  Square means a trait you grant; round means an action.
- The bright/faded rule from 1.3 is unchanged: each Remove, and Finish
  Embracing the One Trait, is its option's art desaturated and darkened.
- 64 icons in all, built from source art in `art/one_trait/` by
  `tools/build_one_trait_icons.py`.

### Removed
- Four icons nothing referenced (`add`, `remove`, `on`, `off`), left over
  from 2020.

## [1.4] — 2026-09-27

A character editor, inside the menu you already use.

### Added
- **Character Editor**, a new first entry on the One Trait menu, leading to three
  pages that each end in **Back**:
  - **Identity** — give or take culture and faith between you and the
    right-clicked character, or have them adopt the culture or faith of their
    capital or yours. Reroll their first name from their culture, or give them
    yours. Changes the character only, never their lands.
  - **Traits** — four curated bundles: *perfect genetics* (removes every bad
    congenital trait, grants Beautiful, Genius, Herculean, Pure-blooded,
    Fecund, Strong and Shrewd), *cleanse* (diseases, wounds, non-genetic
    madness, the frailties of age), *personality copy* in either direction,
    and *break every vice* (unhealthy coping traits).
  - **Body** — set age to 16, 25, 40 or 60, and copy hereditary looks
    (inherited features and colouring, not hairstyle or beard) in either
    direction. A child can only be brought to 16, and comes of age as normal.
- Options that would change nothing are hidden, so an option disappearing
  after a click confirms it worked.
- `tools/validate_mod.py` now fails any trait key the mod names that the game
  does not define, so a patch that renames a trait is caught before release.

### Corrected
- The 1.3 entry below said the menu was "fully localized". It is not:
  all nine languages carry the keys, but eight of them show the English
  wording until translations arrive.

## [1.3] — 2026-09-24

A second menu, with localization keys for all nine languages, for the systems that need a value rather than
a toggle.

### Added
- **Modern Systems menu.** Opened from the existing One Trait menu's new
  **Modern Systems** option, sitting alongside **Close**. It leads to two
  pages, **The Character** and **The Realm**, each ending in a **Back** entry
  that returns to Modern Systems.
  - **The Character** (11 options + Back): court grandeur (add, plus a reset
    to zero), influence (add, plus a drain of 10000), merit (add, plus a
    drain), legitimacy (add, plus a drain), become a mythical legend, accolade
    glory, and grant a relic of the One Trait.
  - **The Realm** (6 options + Back): fill the herd (plus a drain), unleash a
    plague on the capital, upgrade the domicile, end the Iberian and Persian
    struggles, and release all tributaries.
  - **17 cheat options in total, covering 12 game systems that postdate the
    mod's 2020 origin.**
- All nine languages the game ships now carry real localization for the new
  menu — `one_trait_menu_l_<language>.yml`, 37 keys each, English text
  mirrored into the other eight pending translation, matching how the rest of
  the mod's localization already works.

### Artwork
- **Twelve interactions had no icon** and fell back to a generic CK3 default:
  the knights, unlimited knights, men-at-arms and free men-at-arms grants with
  their four matching removes, plus designate heir, both adopt entries and
  disown. All now have their own art, so nothing in the mod borrows a base
  game fallback. 68 icons in total.
- **`open_one_trait_menu` and `close_one_trait_menu` shipped identical rose
  art**, so the entry that opens the menu looked exactly like the one that
  closes it — a large part of why the menu was hard to find in a 48-entry
  list. Close is now the faded version of the rose it undoes.
- The set now follows one rule: **bright means granting, faded means
  removing**. An option and its Remove are the same picture in two states.
- `tools/build_one_trait_icons.py` regenerates the thirteen icons it owns from
  vanilla art and the mod's own previously unused shield and coin art. Two
  approaches are recorded in it as abandoned so they are not retried: nudging
  free men-at-arms a few degrees of hue off the men-at-arms shields, which is
  invisible at menu size, and tinting the two adopt icons blue and rose, where
  any rotation strong enough to see turned the child purple.

### Unchanged
- The original 46 One Trait interactions are untouched. **The player's
  right-click list grows by exactly one entry** — Embrace the One Trait still
  opens a single menu; everything else lives behind it.

### Note on reversibility
Of the 17 new options, five let you undo what the matching option granted:
the court grandeur reset, and drains for influence, merit, legitimacy and the
herd. Six others — becoming a legend, accolade glory, the relic, the plague,
the domicile upgrade and releasing tributaries — have no inverse, and their
labels now say so. **The plague in particular has no cure**:
`create_epidemic_outbreak` has no undo effect in the game, so once it is
unleashed on a capital it must run its course. This is a deliberate
departure from the rest of the mod, where every trait cheat still has a
matching Remove.

## [1.2] — 2026-09-22

New artwork throughout, and the modern systems the mod predates.

### Changed
- **All 55 icons replaced.** Each is built from the base game's own painted
  trait and interaction art, resampled to the right size and given a gold wash
  at 0.55 blend so the set reads as a family rather than as plain vanilla
  icons. Chosen by rendering a strength ladder and looking at it: 0.40 was
  indistinguishable from vanilla, 0.70 turned the teal backgrounds olive and
  lost the palette.
- Icon filenames are unchanged, so no script references needed touching.

### Added
Modifiers from systems that postdate the mod, placed on the traits they belong
to rather than as new menu entries:

| Trait | Added |
| --- | --- |
| Supreme Commander | `travel_danger`, `accolade_glory_gain_mult` |
| Supreme Manager of the Realm | `court_grandeur_baseline_add`, `domicile_build_speed` |
| Unlimited Fame and Glory | `legitimacy_gain_mult`, `monthly_dynasty_prestige_mult` |
| No Stress | `stress_loss_mult` |

Knight effectiveness, knight limit and the men-at-arms cap were deliberately
left out: the mod already grants all three through its own modifier toggles, and
duplicating them on a trait would stack silently.

## [1.1] — 2026-09-22

Compatibility update for **CK3 1.19 "Scribe"** (was targeting 1.2). The scheme
trait had to be rebuilt because the system it was written against no longer
exists; everything else preserves its original values.

### Fixed
- **The mod was almost entirely non-functional.**
  `common/character_interactions/00_one_trait_interaction.txt` had no UTF-8 BOM,
  and CK3 skips script files that lack one. All 1,561 lines and 47 interactions
  — the whole menu system — were not being read.
- `supported_version` raised from `1.2.*` to `1.19.*`.
- Removed `index` from all 15 traits. Manual trait indexes were dropped in 1.4.
- `one_trait_commander` declared `hard_casualty_modifier` and
  `enemy_terrain_advantage` twice each. Four interactions declared `auto_accept`
  twice. Collapsed; values were identical so nothing changed.
- The `one_army` regiment had the same rot as the OP Troops mod: `type =
  house_guard` is no longer a base troop type (it is now a specific regiment
  built on `heavy_infantry`), `can_recruit = no` no longer exists, a `counters`
  entry named `house_guard` was silently doing nothing, and the icon pointed at
  an image the game no longer ships.

### Rebuilt: the scheme trait
CK3 reworked schemes around **success chance** and **phase duration**. The
entire "scheme power" vocabulary this trait used was removed — 28 of its
modifiers no longer existed. Rewritten to express the same intent:

| Intent | Now expressed as |
| --- | --- |
| Your schemes always succeed | `owned_{personal,hostile,political}_scheme_success_chance_add` plus the matching `_max_add` |
| Resolve immediately | `{personal,hostile}_scheme_phase_duration_add` |
| Stay hidden | `owned_scheme_secrecy_add` |
| Nobody schemes on you | `enemy_*_success_chance_add`, `enemy_scheme_secrecy_add`, enemy phase duration |
| Many schemes at once | `max_{personal,hostile,political}_schemes_add` |

The `_max_add` entries matter. The game caps scheme success at **95%**
(`HOSTILE_SCHEME_MAX_SUCCESS_CHANCE` and friends in `common/defines`), so
without raising that ceiling the trait would still fail one scheme in twenty.
The original could not have delivered certain success on 1.19 at any value.

This also removed about twenty redundant per-scheme lines (`murder_`, `seduce_`,
`elope_`, `sway_` and so on) — the generic success chance covers all of them.

### Fixed: the giant trait
`dna_modifiers` sat inside the trait block, where the engine cannot use it; no
base game trait carries one. Moved to
`gfx/portraits/portrait_modifiers/one_trait_giant_modifiers.txt`, matching how
the other mods in this repo do portrait work. It also used
`mode = modify_multiply` with `value = 0`, which zeroes the height gene rather
than maximising it, so the giant was most likely not a giant. Now
`mode = add` at full strength. Both `gene_height` and the `giant_height`
template were verified to still exist in 1.19.

### Fixed: county control
`monthly_county_control_change_add_even_if_baron` no longer exists. The only
surviving `_even_if_baron` form is `monthly_county_control_growth_factor_even_if_baron`,
which is a factor rather than a flat add, so the old value of `100` would have
meant +10,000%. Set to `10`.

### Changed
- Every trait now has a separate description for contexts with no character
  attached. All 16 previously pointed both branches of their `first_valid` at
  the same key, and that key names a character — so the encyclopaedia entry was
  trying to resolve a name that was not there.
- All 55 icons converted to the formats the base game uses: trait icons to
  120x120 and interaction icons to 100x100, both uncompressed BGRA8. The mod's
  artwork drops from roughly 20 MB to 2.5 MB.
- Localization for all nine languages the game ships, instead of English only.
  The eight new languages carry English text as a clearly marked placeholder.

## [1.0]

Initial release, targeting CK3 1.2.
