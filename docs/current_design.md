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
- **The teammate.** Splitting offence and support with an ally (shared win condition).

---

## Resources
- **Gold** - Granted for creep kills and spent on equippable items. 25 gold granted per round split evenly between all spawned units, leaking grants the attacking player a small bounty. Each equipped item costs 100 gold (same cost means they need to be balanced between each other).
- **Wood** - Granted by neutral bosses and spent on tower hero-level upgrades. 100 wood per upgrade. Each tower has per-level RPG stat increase modifiers.
- **Food** - Granted on a logarithmic timer and spent on tower purchases. Cadence is additional towers early and slow towers later, with 15th tower unlocking near the 30 minute mark.
- **Your income never depends on what your enemies build.** Nothing is paid to you per creep they send,
  so an enemy cannot starve you by building small or inflate you by building big.
- **Streak** A bonus gold bounty each round for being leak free, multiplied by the length of the streak (resets if you leak a creep)
- **Interest** A bonus % periodic bounty for unspent resources (gold and wood, not food)
- **Allies have separate wallets and cannot share resources or bounties** 

## Neutral Encounters
- **Triggered on a repeated timer as a modulus of wave counts** Every 5 waves (tunable). Next boss is always known (start of game & re-randomized after each boss terminates).
- **Bounty** Non-killable DPS calculator, copy of same boss sent to all zones simultaneously and only takes 1 trip around circuit (no leak or teleport). Chosen randomly from a list of possible bosses so stats are well-known to players in advance (strengths/weaknesses) - Essentially chosen from list of all possible creeps but with all its abilities active, no items, and its level matching the wave number. Towers focus-fire boss 1st (before other low-health enemies). Total available bounty of 150 wood per player and each reward is split based on each player's damage % of the total.

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

- **Every creep is tagged by its spawn owner and designated enemy.** Players attack-left and defend-right, skipping allied (no friendly fire) or empty zones (or eliminated players).
	That tag is fixed for the creeps whole life. Kill bounty goes to defending player even if ally landed the killing blow.
- **Eliminated players have their zone cleared (towers and creeps) and no longer spawn attacking creeps** This changes the assigned attacker and defender designations.
- **A creep repeats the circuit until killed** It spawns at the start of the maze, walks the entire path, teleports, and continues the circuit infinitely until death.
	In FFA, the teleport is back to the start of the maze. In team-based, it teleports to the start of the next ally's maze.
- **All creeps in a match come from players' buildings.** The game does not spawn authored waves and
  there is no wave table anywhere.
- **Creep variety comes from what people build.** A good unit has a clear identity and well-known
  strengths and weaknesses an opponent can see and answer.

---

## Food spend (Buildings and Creeps: one purchase, two jobs)

- **Every food spent is both defence and offence.** Towers defense your maze, spawned creeps walk an enemy's maze
- **There is a 1:1 mapping between towers and creeps**
- **There is no separate "send" system.** The creeps spawned by your towers are the waves your enemy needs to clear.
- **Many build paths must exist.** A building may be a bruiser that fights and soaks, a dedicated
  carry, a support piece, or a hybrid — the same way a MOBA lets one character fill two roles
  depending on how it is built. Designers are free to be creative here.
- **No single choice is forced to be strictly attack or strictly defence.** What must hold is that the
  options stay balanced against each other, not that every decision is a coin-flip between two pure
  halves.

---

## What a building is, and how it grows

**Every building has exactly four abilities: one passive and three combos.**

- **Free passive ability** It is an ability that unlocks without needing a combo with another 'named' synergies. It also defines the associated creep that spawns. Spawn requires no additional resources.
- **Each ability is switched on by a matching tag from another building on the board.** An unlocked ability grants a defined bonus to the tower and its associated spawned creep.
	Abilities may require mana to cast causing a unit to become less effective with insufficient mana regen.
- **Every ability unlock is defence and offence at once.** Scaling can be assymetrical as long as total power is balanced
- **A building can switch on several partners at once.** One well-chosen building could satisfy the
  conditions of several others simultaneously, which is part of the planning puzzle.
- **Duplicates prevented per player** You cannot build 2 copies of one tower. Purchasing a 2nd copy merges into the existing tower and increases its star level. The food is not consumed by purchasing the duplicate, so your open building slot stays available.
- **Items are the scaling factor.** Each building can be equipped with one item maximum, and the item is cloned onto its spawned creeps.
	Items are purchased with a separate resource (Gold).
- **No selling** - A placed tower and chosen upgrade is permanent. No refunds, no undo. A choice is a commitment. Purchased items can be moved between towers.
- **Star Levels** - Finding a duplicate tower that you already own increases the star level of that tower (max 3) which determines the quantity of creeps spawned each wave by that tower
- **Hero levels** - Increased by spending a separate resource (Wood) (shown as a floating # indicator above the head by the health bar).
	The base RPG stats all have per-level scaling which have different formulas per unit, which in turn makes a higher level stronger in both offense (creeps) and defense (tower attacks).
- **Damage Targeting** - Towers have a deterministic targeting formula which filters for targetable units in range and sorts by bosses 1st and then lowest current health points (not percentage).

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

## Named Synergies
** Each 'tag' grants a specific modifier and is also used in determining matching pairs for ability unlocks **
** Faction (Ability 1) **
	- Orc 1.5x Strength per level
	- Human 1.5x Intellience per level
	- Elf 1.5x Agility per level
	- Druid 1.5x Wisdom per level
	- Goblin 1.5x Fortune per level
	- Dwarf 1.5x Vitality per level
** Damage Type (Ability 2) **
	- Magic (Weak against Fortified, Strong against Cloth)
	- Siege (Weak against Flesh, Strong against Fortified)
	- Blunt
	- Pierce
** Defense Type (Ability 3) **
	- Flesh
	- Fortified
	- Heavy
	- Medium
	- Cloth

## Knowing the board

The board has to be read at a glance, mid-fight, without a tooltip or a spreadsheet.

- **Star level is shown above the unit.** A glance at a board tells you which pieces are merged.
- **Clicking a unit opens its card.** The card shows all four abilities: the passive with its star
  level, and the three combos each with the condition it needs and whether that condition is met right
  now. Locked abilities are greyed but *visible*, so the card is also the "what would I gain from my
  next building" screen.
- **Both directions read the same way.** You can tell what creeps a zone is sending from its towers,
  and what its towers must be from its creeps, because a creep's body says which class sent it.
- **The build menu is randomized.** It gives 4 random choices with a reroll button (costing Gold). Player picks 1 to build.
	It never offers a tower you already have at max star level. Reroll never shows a tower you previously viewed this round.
	Reroll adds more choices to your current build list so you can still pick the previous options if you don't like any of the reroll options.
	Tooltip must show all 3 synergy axes
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
- **No second chances.** No forgiveness window that changes the rules, no difficulty change by stage
  of the match, no restarts. Every round follows the same rules for everybody. (A short scramble back
  under the limit is a different thing from a second chance)
- **Warning:** Approaching the limit should warn you in color-coded text. Yellow for 50% overrun, Orange for 75% overrun, Red for 90% overrun. 100% is instant loss.

---

## Teams: you win or die together

- **A team is one player for the purposes of losing.** Their total living creeps is compared against their total overflow threshold and they are eliminated as a whole team.
- **Losing removes all buildings that team owns and stops future spawns:** previously spawned creeps keep walking the circuit until killed.
- **Last team standing wins.** Teams are ranked as a team, in reverse order of elimination.

---

## Leaks

- **A leak is a creep leaving your zone alive.** It does not cost you health or points directly.
- **The creep's owner gets a small bonus gold bounty when it leaks**

---

## The shrine

- **A player-owned shrine exists**, in the style of Enfo's spell shrine: a fixed set of useful spells, each
  for a different situation. Each player has their own shrine, with the same abilities, but different current mana based on their previous spell casts. Spells can be cast globally onto any zone.
- **Spells cost mana and have cooldowns**, so the skill is demonstrated by when and how you use them. Mana gained slowly over time based on the shrine's Mana regen stat.
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