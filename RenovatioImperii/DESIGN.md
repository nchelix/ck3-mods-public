# Renovatio Imperii — design

**Status:** design, not yet implemented.
**Target:** CK3 1.19 "Scribe".

## The gap this fills

Crusader Kings treats the Roman claim as a trophy. `restore_roman_empire_decision`
requires you to already hold `title:e_byzantium` *and* completely control
fourteen Mediterranean duchies. `imperial_reconquest_cb` is gated on
`is_roman_emperor_excluding_byzantium_trigger` — you must already hold
`h_roman_empire` or `h_eastern_roman_empire` to use it.

So in vanilla you win the Roman Empire and *then* receive the tools for claiming
it. Historically that is backwards. Charlemagne, the Ottonians, the Bulgarian
tsars and later the Ottomans all proclaimed Roman succession long before they
held Rome, and then spent their reigns trying to make the claim stick.

**This mod lets you proclaim first and fight for it after.** You do not get the
empire. You get a claim, an identity, and a great many enemies.

## What the base game already provides

Verified against the installed copy, not assumed:

| Thing | Status |
| --- | --- |
| `h_roman_empire`, `h_eastern_roman_empire` | Hegemony titles, exist |
| `augustus`, `august`, `born_in_the_purple`, `former_emperor` | Real traits with finished art |
| `imperial_reconquest_cb` | Exists, gated behind already being emperor |
| `restore_roman_empire_decision` and three siblings | Exist, endgame-gated |
| `e_byzantium`, `e_latin_empire` | Exist |

Rome is modelled as a **hegemony** in 1.19, not an empire title. The mod should
respect that rather than inventing a parallel title.

## The three pieces

### 1. Proclamation

A decision with real prerequisites. Proclaiming has to mean something or the
world's outrage rings hollow.

Requirements, all of which must hold:

- Tier of king or higher
- A meaningful prestige level, spent on the proclamation
- **Plausibility**: either a culture descended from Rome (Latin or Byzantine
  heritage), or holding at least one county that was part of the old Empire
- Not already a Roman claimant, and not already holding a Roman hegemony

### 2. What you gain

- **`roman_claimant`** — a fame-category trait modelled on vanilla `augustus`:
  prestige and influence gain, strong same-opinion among fellow claimants,
  vassal opinion. Uses vanilla's unused `augustus` art.
- **`renovatio_cb`** — a casus belli against former Roman territory, available
  to a claimant rather than to an emperor. Scoped to de jure regions of the old
  Empire so it cannot be pointed at Scandinavia.

### 3. How the world answers

This is the point of the mod. The claim is cheap; the consequences are the game.

| Reactor | Opinion | Reasoning |
| --- | --- | --- |
| Byzantine emperor and vassals | Strongly negative | There cannot be two Romes |
| Holy Roman Emperor | Strongly negative | A rival claimant, and they were first |
| The Papacy | Conditional | The Pope crowned emperors; court him and he approves, bypass him and he does not |
| Latin and Byzantine cultures | Positive | A plausible restorer |
| Everyone else | Mildly negative | Presumption |

All as opinion modifiers, so they show in the character's opinion breakdown with
a readable reason rather than as an invisible number.

## The event chain

Six events, fired from the proclamation and from on_actions thereafter. Each has
real choices rather than a single acknowledge button.

1. **The Proclamation** — immediate. Sets the tone, and how you frame it shapes
   the first reactions.
2. **Word Reaches Constantinople** — a letter event. The eastern emperor is
   unimpressed, and says so.
3. **The Pope's Offer** — coronation in exchange for concessions. Accept and
   gain legitimacy at a price, refuse and keep your independence.
4. **Antiquarians and Senators** — flavour with teeth: people turn up wanting to
   serve the restored Rome. A courtier, a modest boost, or a fraud.
5. **A Rival Claimant** — an AI ruler proclaims too. The contest begins.
6. **Judgement** — a culmination that reads how far you have actually got and
   responds accordingly.

## Rival claimants

AI rulers may proclaim, through the same decision with an `ai_will_do` weighted
towards plausible candidates — Byzantine and Latin cultures, high prestige,
kings and emperors. Rare rather than common, so it stays an event rather than
background noise.

Rival claimants view each other with hostility. Two claimants in the same world
should feel like a problem that needs resolving.

## Deliberately out of scope

- **No new title.** Vanilla's restoration decisions still work and still create
  the hegemony. This mod is the road there, not a replacement finish line.
- **No guaranteed success.** Proclaiming grants a claim, not land. If you cannot
  make it stick, you die a pretender, which is the honest outcome.

## Risks

- **Events are new ground for this repo.** Nothing built here so far fires on
  its own. Expect the event chain to need in-game testing that the validator
  cannot substitute for.
- **AI proclamation is unpredictable by nature.** The weighting will need
  tuning against an actual observed game, not reasoning alone.
- **The validator does not check event syntax, CB syntax or on_actions.** Those
  will need extending, or the first real test is the game itself.
