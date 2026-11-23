# Current design

Plain language, no formulas, no lore.

---

## Elevator pitch

Tower defense with pre-defined static Maze. Each decision simultaneously defines the creeps to spawn against your enemies
and the towers to defend you. Tower and Creep upgrades are pre-defined and unlocked by owning both sides of a 'named' synergy.
Each player controls one of four zones, which can be set up as FFA or 2v2. Leaked creeps move on to your ally's maze and back to
you in an endless circuit until killed. Loss occurs for the team as a whole if total count of living creeps within allied zones overruns a threshold.
Towers can have equipped items which grant RPG stats. All unit (tower and creep) stats and abilities scale from formulas using these RPG stats as coefficients.

---

## Possible player fantasies fulfilled by the game

The fantasies the rules are built to deliver. Each one is reachable by a different route, and none of
them is the "correct" way to play.

- **The tide.** Numbers as a strategy: a late board sending a full wave down the road and burying
  somebody. This is why every ability a building unlocks adds another creep to the wave.
- **The few perfect pieces.** The opposite bet: a small, expensive cluster that kills everything that
  walks in and never leaks. This is why stars make a building better and why the slot count is tight.
- **The carry.** One building that becomes the whole plan, fed merges and items until it does most of
  the work on its own, with the rest of the board there to keep it alive.
- **The support.** Placement and auras that make a cluster — yours, or a teammate's — worth more than
  its parts.
- **The planner.** Winning before the first fight by building the set of buildings that switch each
  other on.
- **The reader.** Building the counter because the enemy's towers, stars, items and creeps are all
  visible on the board and all public.
- **The comeback.** Surviving the bad round and climbing back into the match instead of being deleted
  from it.
- **The teammate.** Splitting offence and support with an ally, sharing bounty and sharing death.

---

## Resources
- **Gold** - Granted for creep kills and spent on equippable items. 100 gold granted per round split evenly between all spawned units, leaking allows the next player to capture the bounty associated with that unit. Allies split the bounty but have separate wallets and can't spend each other's resources or trade it. Each equipped item costs 500 gold (same cost means they need to be balanced between each other).
- **Wood** - Granted for _____ and spent on tower star-level upgrades
- **Food** - Granted on a timer and spent on tower purchases
- **Your income never depends on what your enemies build.** Nothing is paid to you per creep they send,
  so an enemy cannot starve you by building small or inflate you by building big. What varies with
  them is your *danger*, never your wallet.
- **Streak** A bonus gold bounty each round for being leak free, multiplied by the length of the streak (resets if you leak a creep)

## The map and placement

- **Fixed and hand-authored.** Symmetrical by design. No maze building, no blocking, no rerouting, no
  path pressure of any kind.
- **One zone per player:** walls, one entrance, one exit, and a single road between them.
- **Build spots are fixed and placed along the road.** A spot's value is what stretch of road it can
  see: a spot that sees a long stretch, or sees the same stretch twice, is better than one that catches
  a corner briefly. No random spot bonuses, no spot upgrades.
- **Fewer spots than a player could fill.** Around twenty to twenty-five per zone (tunable) against a
  board of about fifteen towers, so placing them is a choice and the map is not a wall of towers.
- **Patch sizes vary.** Some clusters are tight enough that auras overlap; some are strung along a long
  stretch for coverage. That is what makes proximity matter at all.
- **Placement is the second-order decision, not the first.** Proximity matters only through things the
  player can see, such as auras. A player who ignores
  placement and builds centrally should still be able to win; a player who reads it should be rewarded.

---

## Creeps and affinity

- **Every creep is tagged by who spawned it.** That tag is fixed for its whole life: relative to any
  given player, a creep is *allied* or *enemy*, and that never changes.
- **Eliminated players have their towers destroyed and no longer spawn creeps** 
- **A creep only walks enemy zones.** It spawns into the first enemy zone, walks the entire path, teleports to the next enemy,
	and continues the circuit infinitely until death.
- **What that means per mode:** in a duel your creeps circle your opponent's road for the rest of the
  match; in a team game they circle the enemy team's roads; in a free-for-all they make the rounds of
  every opponent.
- **All creeps in a match come from players' buildings.** The game does not spawn authored waves and
  there is no wave table anywhere.
- **Creep variety comes from what people build.** A good unit has a clear identity and well-known
  strengths and weaknesses an opponent can see and answer.

---

## Buildings: one purchase, two jobs

- **Every building is both defence and offence.** It fights in your zone and it produces creeps that
  go out to enemy zones.
- **There is no separate "send" system.** The creeps that attack other players are exactly the creeps
  your buildings produce. Nothing is bought, queued or aimed separately, and there is no menu that
  says "send this at that player".
- **Many build paths must exist.** A building may be a bruiser that fights and soaks, a dedicated
  carry, a support piece, or a hybrid — the same way a MOBA lets one character fill two roles
  depending on how it is built. Designers are free to be creative here.
- **No single choice is forced to be strictly attack or strictly defence.** What must hold is that the
  options stay balanced against each other, not that every decision is a coin-flip between two pure
  halves.

---

## What a building is, and how it grows

**Every building has exactly four abilities: one passive and three combos.**

- **Free passive ability** It is an ability that unlocks without needing a combo with another 'named' synergies.
- **Each combo ability is switched on by another building standing on the board.** It makes the
  building fight better *and* it adds a new creep to the wave — a different body from the passive's.
  So a fully unlocked building sends four kinds of creep in one round, and a board of fifteen sends
  sixty at the absolute ceiling.
- **Every unlock is defence and offence at once.** There is no way to buy offence without defence, and
  no way to buy defence that does not also put bodies on the road. Spawn requires no additional resources.
  Abilities may require mana to cast causing a tower to become less effective with insufficient mana regen.
- **There is no web screen, and no tech tree.** The "web" is a *cognitive* web: the internal dependency
  structure of which buildings switch on which. You read it from your own board and from the ability
  cards, and it looks different every match because it depends on the buildings you own.
- **A building can switch on several partners at once.** One well-chosen building could satisfy the
  conditions of several others simultaneously, which is part of the planning puzzle.
- **Duplicates prevented per player** You cannot build 2 copies of one tower.
- **Items are the scaling factor.** Each building can be equipped with one item maximum, and the item is cloned onto its spawned creeps.
	Items are purchased with a separate resource (Gold).
- **No selling** - A placed tower and chosen upgrade is permanent. No refunds, no undo. A choice is a commitment. Purchased items can be moved between towers.
- **Star levels** - A separate resource (Wood) can be spent to increase the star level of a tower (shown as a floating # indicator above the head by the health bar).
	The base RPG stats all have per-level scaling which have different formulas per unit, which in turn makes a higher level stronger in both offense (creeps) and defense (tower attacks).

**The six stats, as the engine actually defines them** (from `CombatTuning.cs`):

| Stat | What it gives |
|---|---|
| Strength | attack damage, tenacity, armour |
| Agility | attack speed, movement speed, cooldown reduction |
| Vitality | health, mana, life steal |
| Intelligence | spell damage, mana regeneration, magic resistance |
| Wisdom | magic penetration, healing and regeneration, critical damage |
| Fortune | critical chance, evasion, proc rate, bounty |

---

## Knowing the board

The board has to be read at a glance, mid-fight, without a tooltip or a spreadsheet.

- **Star level is shown above the unit.** A glance at a board tells you which pieces are merged.
- **Clicking a unit opens its card.** The card shows all four abilities: the passive with its star
  level, and the three combos each with the condition it needs and whether that condition is met right
  now. Locked abilities are greyed but *visible*, so the card is also the "what would I gain from my
  next building" screen.
- **Both directions read the same way.** You can tell what creeps a zone is sending from its towers,
  and what its towers must be from its creeps, because a creep's body says which class sent it.
- **The build menu can filter.** It only needs to show choices that would switch something on, so a
  large roster does not become a scroll bar. Nothing is hidden from a player who wants the full list.
- **full vision** - Scouting is free, the strategy elements must work without hiding information

---

## Game Start
- **Game Start** - You start with 1 random tower built in the center of your maze. You have enough resources (food) to
	build one more tower. You start by fighting the 'passive' creeps created by your enemy's starting building.

## The round

- **A new round starts on a fixed clock**, roughly a minute (tunable). The round does not wait for the
  previous one to be cleared.
- **The spawn happens continuously until unspawned creeps that round are exhausted**
- **There is no build phase and no pause.** You build, upgrade and re-equip whenever you like,
  including in the middle of a fight. Whether you are actively fighting depends on how fast you
  cleared the last wave, not on a phase timer.

---

## Losing: too many creeps alive

- **The only failure state is overflow:** more live creeps in your zone than your limit allows. No
  base health, no lives counter, no attacking buildings.
- **The limit is a small multiple of the wave arriving in your zone** — Probably 2.5x the current spawn count (tunable) with a minimum threshold of ~ 25 (tunable) to prevent early loss.
  Meaning overflow happens through **accumulation**. Count is done by the creeps currently in your zone, meaning in a FFA a 
  creep that teleports to the next zone would no longer count against you (but incoming teleports would). For team-based your numbers are counted cumulative.
- **Consequence for upgrades and items:** they may change *what* a building sends, never *how many*.
  Quantity only goes up with stars, which is what keeps the limit from ever having to shrink.
- **No second chances.** No forgiveness window that changes the rules, no difficulty change by stage
  of the match, no restarts. Every round follows the same rules for everybody. (A short scramble back
  under the limit is a different thing from a second chance)
- **Warning:** Approaching the limit should warn you in color-coded text. Yellow for 50% overrun, Orange for 75% overrun, Red for 90% overrun. 100% is instant loss.

---

## Teams: you win or die together

- **A team is one player for the purposes of losing.** Their total living creeps is compared against their total overflow threshold and they are eliminated as a whole team.
- **Losing removes everything that team owns:** its buildings, and every creep it ever sent, wherever
  those creeps happen to be standing. The board gets smaller and cleaner at that moment.
- **Last team standing wins.** Teams are ranked as a team, in reverse order of elimination.

---

## Leaks

- **A leak is a creep leaving your zone alive.** It does not cost you health or points directly.
- **The creep's owner gets a small bonus bounty when it leaks** — Gold, shared bounty split between allied team.

---

## The shrine

- **A neutral shrine exists**, in the style of Enfo's spell shrine: a fixed set of useful spells, each
  for a different situation.
- **Spells cost mana and have cooldowns**, so the skill is in when and how you use them. Mana gained slowly over time based on the shrine's Mana regen stat.
- **Open:** the spell list, what they can target

---

## Possible players and modes

- Specified in Match Settings in Lobby before game start
- **One to four players**, in free-for-all, teams, or co-op. Every rule above is written for any
  number of zones; player count only changes the seating.
- **AI plays by exactly the same rules as a person.** It is a normal opponent, not a special mode.
- **Co-op is the same game against AI** instead of against humans. No rule changes.
- **Open:** the exact mode list and how teams are seated.

---

## Winning, and ending a match

- **Last team standing wins.** Everyone else is ranked by reverse order of elimination: the last team
  to overflow finishes highest. That ordering is the whole result.
- **A match must not run long past about thirty minutes.** The game is expected to produce a decided
  ending shortly after that mark rather than allowing a stalemate. The current plan is that all creeps gain +1 HeroLevel per round after round 30 infinitely until game over, which should quickly outpace tower upgrades and force an overrun scenario for both teams.

---

## Open questions

**How a combo names its partner** — by specific unit, by class, or by a class count, and the rule
   that stops a mono-class board unlocking itself. This decides whether the roster can grow for years
   without the web being rewritten.
**Roster size and growth** — whether the set of buildings grows over the years, and how big the pool
   needs to be for a fifteen-slot board.
6. **Classes** — how many, and what the readable strengths and weaknesses of a creep are.
**The neutral objective** — the dragon-equivalent swing, still undesigned.
**Resource numbers** — the stipend, the streak curve.

---

## Tunable dials

| Dial | Starting thought |
|---|---|
| Match length | ~30 min target |
| Round length | ~60 s |
| Spawn speed | ~500ms per unit |
| Towers per player at the end | ~15 |
| Build spots per zone | ~20–25 |
| Abilities per building | 4 — one passive, three combos |
| Creeps per wave, per player, wave 30 | ~50 |
| Live creeps when everyone is overrun | ~500 total, ~125 per zone at the limit |
| Ceiling if everything unlocked | 4 kinds per building, ~60 kinds at 15 buildings |
| Overflow limit | a small multiple of the incoming wave, ~ 2.5x |