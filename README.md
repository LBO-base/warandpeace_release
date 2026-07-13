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

## Multiplayer / dedicated servers
- The mod must be installed **on the server AND on every client**, same version
  (the mod warns in chat on mismatch).
- All simulation runs server-side; the server's config is authoritative.
- See [docs/server-setup.md](docs/server-setup.md). Economy explained: [docs/economy.md](docs/economy.md).

## For builders
Want your buildings to appear in every settlement of the world?
See [docs/building-guide.md](docs/building-guide.md).
