![War and Peace](assets/banner.png)

# War and Peace — living faction wars for Valheim

*Читать по-русски: [README.ru.md](README.ru.md)*

The world lives without you: 150+ settlements of viking factions and raider clans
rise across the whole map. They run economies, trade with caravans, build roads,
muster armies, besiege and conquer each other — and you can found **your own town**,
hire viking guards, trade, wage war and redraw the map.

> ⚔ **Status: open beta.** Play on a fresh world, not your main save.
> Report bugs via GitHub Issues.

## Features
- **150+ living settlements**: economy, stockpiles, workers, tier growth
  (outpost → village → town → capital), each faction with its own map crest.
- **Total faction war**: armies march visibly across the map, clash on the road
  and at sea, besiege towns. Conquered towns are razed and rebuilt in the
  conqueror's style. Combat maths honours roster quality — a troll is worth
  more than a farmhand.
- **Your settlement**: build houses, place the **Settlement Heart** (hammer →
  Misc), name your town, hire viking guards (limit = beds; upkeep = food +
  coins). Break an enemy heart — the town is yours.
- **Trade**: sell resources into a town's buying post; donate into the gift
  chest for reputation.
- **Community buildings** are baked into the mod; save your own in-game (F7).

## Install (manual)
1. Download `releases/WarAndPeace-BuilderKit-<version>.zip`.
2. Unpack; move the contents of the `INTO-GAME-FOLDER` folder into your Valheim
   root folder (next to `valheim.exe`). This includes BepInEx.
3. Start the game. Done.

## Update
Run `UPDATE-MOD-RU.bat` in your Valheim folder **with the game closed** —
it downloads the latest build from this repository.

## In game
- **Alt+H** — the settlement panel: passport of the nearest town (economy, garrison,
  wars, buildings, faction standings). Your window into everything.
- **F7** — Layout Studio: save your own buildings as blueprints for the world.
- **F9** — battle range: call an army onto the nearest town and watch the fight.
- Hotkeys and everything else are tunable: [docs/config.md](docs/config.md).

## Multiplayer / dedicated servers
- The mod must be installed **on the server AND on every client**, same version
  (the mod warns in chat on mismatch).
- All simulation runs server-side; the server's config is authoritative.
- See [docs/server-setup.md](docs/server-setup.md). Economy explained: [docs/economy.md](docs/economy.md).
  Config reference: [docs/config.md](docs/config.md).

## For builders
Want your buildings to appear in every settlement of the world?
See [docs/building-guide.md](docs/building-guide.md).

## Credits
- **Iron Gate Studio** — for Valheim itself.
- **[RustyMods](https://thunderstore.io/c/valheim/p/RustyMods/)** — our human viking
  NPCs use the runtime Player-clone technique we studied in their
  [VikingNPC](https://thunderstore.io/c/valheim/p/RustyMods/VikingNPC/) / Norsemen
  mods (no assets or code borrowed — but the idea showed the way).
- **BepInEx & HarmonyX teams** — the modding foundation everything here stands on.
- **Our testers and builders** — the community buildings baked into the mod and
  the bug reports that shaped every battle-model fix.

## Roadmap
Order, not dates. Details may shift with beta feedback.

**Ongoing, across every version:**
- ⚔ **Faction & NPC balance is tuned continuously** — from real battle data (every clash leaves a
  forecast/result pair, and the model is corrected by numbers, not by feel). Rosters, unit strength
  and the pace of war are live-tuned build to build.
- 🏛 **Buildings for each faction keep being added** — more authored structures per faction type and
  biome ship with the mod over time; draw your own and send them in (see the builder guide).

**Milestones:**
- ✅ ~~**0.5.x — open beta**: battle-model calibration, full localization, fixes from tester reports.~~
- ✅ ~~**0.6 — Honest War**: abstract battles resolved by a **unit-level mini-simulation** — ranged/melee
  and kiting, walls and high ground, **typed losses** (mages die last, melee grind in the clash).~~
- **0.7 — Multiplayer**: polished co-op up to 5 players on dedicated servers.
- **0.8 — Your Warband**: orders to your towns (send armies, defensive stance), diplomacy through
  reputation and tribute, town growth and renaming, co-op progression.
- **0.9 — Living World+**: named commanders with perks, siege engines, caravan ambushes and robberies,
  world events, even more community buildings.
- **1.0 — Thunderstore release**: one-click install, onboarding hints, performance, final balance.
