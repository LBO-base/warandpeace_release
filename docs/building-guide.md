# Builder's guide — settlement buildings

*Полная русская версия (каноническая): [building-guide.ru.md](building-guide.ru.md)*

Buildings you design can appear in **every settlement of the world** — the mod
stamps them when towns are generated, grow or rebuild after wars.

## Quick start
1. Install the mod (see the main README) — the builder kit includes everything.
2. In game press **F7** — the Layout Studio: free build mode, boundary rings,
   template tools.
3. Build a hut inside the ring. Keep the footprint compact; either bake proper
   support poles under the floor or build directly from the ground.
4. Put a **sign** on the building that names its role (kitchen, mill, storehouse,
   barracks, smithy, house, trade stall…) — the mod reads signs to type the
   building. A buying post needs a chest with a "supply/buy" sign near it.
5. Save via the Studio — the template lands in
   `BepInEx/config/WarAndPeace/layouts/` as a `.wapx` file. Send that file in.

## Requirements per building
- Each role has a required "station" inside (kitchen: fire + cooking stand, or a
  cauldron on higher tiers; mill: a windmill; smithy: a forge; house: beds…).
- Make tier variants where it matters: outpost / village / town / capital.
- Roofs may overhang, but walls should sit on the floor plan — the mod places
  support poles and ground fill under the floor line automatically.

## How your template lives
- The mod picks templates by faction kind (civilised / raider), biome and tier.
- Damaged buildings are repaired by the settlement's economy; razed towns are
  rebuilt in the conqueror's style — with the conqueror's template set.
- Missing roles are reported in the server log as
  `PROGRAM: <town> lacks a '<role>' building` — that's the wishlist.

## Putting your building on a server
Drop the `.wapx` into the **server's** `BepInEx/config/WarAndPeace/layouts/`
and restart it — worldgen is server-side, players need nothing extra.
