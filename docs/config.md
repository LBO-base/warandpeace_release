# Configuration guide

*Читать по-русски: [config.ru.md](config.ru.md)*

## The config file

The mod writes its config on first launch to:

```
<Valheim>/BepInEx/config/com.rarier.warandpeace.cfg
```

Edit it **with the game (or server) closed** — BepInEx reads the file at startup.
Every entry in the file carries its own comment; this page covers the settings
people actually tune, section by section.

**Multiplayer:** the whole simulation runs on the server (or the host in co-op) —
the **server's config is authoritative** for the world: settlement counts, wars,
economy. Client-side entries (HUD, map pins, panel hotkey) stay personal.

Upgrading from *WarAndPiece* 0.4.x? The old `com.rarier.warandpiece.cfg` and the
`config/WarAndPiece` data folder are migrated automatically on first launch.

## Hotkeys

| Key | What it opens | Config entry |
|-----|---------------|--------------|
| **Alt+H** | Settlement panel — passport of the nearest town: economy, garrison, wars, buildings, factions | `[HUD] SettlementPanelKey` |
| **F7** | Layout Studio — save your own buildings as blueprints for the whole world ([building guide](building-guide.md)) | `[Debug] LayoutStudioKey`, host only |
| **F9** | Battle range — call an army of any faction onto the nearest town and watch the prediction vs the live fight | `[Debug] CalibPanelKey`, host only |

F7/F9 also require `[Debug] EnableAdminPanel = true` (default).

## [World] — how much world

| Entry | Default | Meaning |
|---|---|---|
| `EnableWorldSpawning` | true | Master switch: no new settlements at all when off. |
| `MaxSettlements` | 120 | Hard cap on settlements in the world. |
| `PlanWholeWorld` | true | Plan the whole map at world load (settlements exist "on paper" and materialize when you approach). Off = settlements only appear near explored zones. |
| `PlanSpacing` | 450 | Minimum distance between planned settlements, meters. Bigger = sparser world. |
| `MinDistanceFromWorldCenter` | 700 | Protected radius around spawn — no NPC towns there. |

**Denser world:** `PlanSpacing 350`, `MaxSettlements 160`.
**Sparser world:** `PlanSpacing 600`, `MaxSettlements 80`.

## [Settlement] — how towns are built

| Entry | Default | Meaning |
|---|---|---|
| `FriendlyChance` | 0.68 | Share of civilized (viking) settlements vs raider camps. |
| `EnableTraders` | true | Traders at civilized town flags. |
| `LevelTerrain` | true | Terraforming: terraces, earth pads, ramps. Off = houses adapt to raw ground only. |
| `AdaptivePlacement` | true | Houses pick their own stands on natural relief (recommended). Off = flat stamped terraces. |
| `AdaptiveWalls` / `AdaptivePaths` | true | Perimeter palisade rings and painted walkways between houses. |
| `SettlementHeartPrefab` | crystal_wall_1x1 | The capturable "heart" object of civilized towns. |

## [War] — how much war

| Entry | Default | Meaning |
|---|---|---|
| `EnableWars` | true | Live raids on settlements near players. |
| `EnableWarSim` | true | The map-wide abstract war: armies, sieges, conquests everywhere. |
| `WarSimTickSeconds` | 45 | Pace of the world war. Bigger = slower campaigns. |
| `WarSimMobilizeThreshold` | 50 | Muster strength a town needs before it marches. Higher = fewer, bigger wars. |
| `WarCooldownMinutes` | 18 | Breather between raids on the same town. |
| `EnableSeaBattles` | true | Armies crossing water can be intercepted at sea. |
| `WaveCapOutpost/Village/Town/Capital` | 4/6/8/10 | Max attackers materialized per assault wave near players (performance guard). |

**Peaceful world:** `EnableWarSim false` keeps economies and caravans running with no conquests.
**Slower war:** `WarSimTickSeconds 90`, `WarSimMobilizeThreshold 80`.

## [Economy], [Buildings], [Workers]

| Entry | Default | Meaning |
|---|---|---|
| `EcoTickSeconds` | 60 | Economy heartbeat: production, hiring, repairs. |
| `ProductionMultiplier` | 1.0 | Global multiplier on all settlement production. |
| `ConquestLootFraction` | 0.6 | Share of a sacked town's treasury carried off by the victor. |
| `[Buildings] *` | — | Per-role bonuses (farm food, mine metal, barracks muster…). Numbers behind the Buildings tab of the H panel. Damaged buildings grant proportionally less; ruins grant nothing until restored. |

## [Capture] — your towns

| Entry | Default | Meaning |
|---|---|---|
| `EnableCapture` | true | Breaking an undefended enemy heart flips the town to you. |
| `AllowSettlementLoss` | true | NPC armies can take **your** towns. Off = your towns can lose a battle but never the flag. |
| `ForcePvP` | false | Leave off — PvP capture is intentionally unsupported. |

## [Roads] — roads and caravans

| Entry | Default | Meaning |
|---|---|---|
| `EnableRoads` | true | Towns fund real roads between each other. |
| `EnableCaravans` | true | Trade caravans with real cargo (they can be raided — by you too). |
| `RoadPainting` / `RoadGrading` | false | Terrain-touching road finish; off by default to keep the world pristine. |

## [HUD], [Map], [Performance]

| Entry | Default | Meaning |
|---|---|---|
| `EnableHUD` | true | The faction/settlement bar at the top of the screen. |
| `EnableMapPins` | true | Settlement crests, army/caravan/worker pins on the map. |
| `MaxLiveNpcs` | 250 | Global cap on live mod NPCs — lower it on weak machines. |

## [Reputation]

How towns judge you: hitting settlement pieces or NPCs costs local and faction
reputation (`RepLossPerHit*`), killing raiders near a town earns it
(`RepGainPerRaiderHit`), reputation below `RepHostileThreshold` (−20) makes
guards attack on sight. Donations into the gift chest raise it back.

## Useful console commands (F5, host)

| Command | Effect |
|---|---|
| `wap_settlements` | Dump every settlement to `settlements.txt` (with the world seed). |
| `wap_reset` | Full simulation reset: wipe mod objects, keep player towns, replan the world. |
| `wap_terrainfo` | Stand in a terrain tear — prints which zone holds the edits. |
| `wap_terrareset [radius]` | Reset terrain around you to natural (heights + paint). |
| `wap_prefabs <filter>` | Search spawnable prefab names (e.g. for `SettlementHeartPrefab`). |
