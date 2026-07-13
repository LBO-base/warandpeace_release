# Dedicated server setup

*По-русски: [server-setup.ru.md](server-setup.ru.md)*

## Requirements
- Valheim Dedicated Server (Windows or Linux).
- BepInEx 5.4.22+ for Valheim (server install).
- The mod must be installed **on the server and on every client**, same version —
  the mod warns joining players in chat on mismatch.

## Install on the server
1. Install BepInEx into the server folder (same pack as the client; on Linux
   start via `start_server_bepinex.sh` — included in our kit).
2. Put `WarAndPeace.dll` into the server's `BepInEx/plugins/`.
3. Start the server. First run creates the config:
   `BepInEx/config/com.rarier.warandpiece.cfg`.

## How it works
- All simulation (worldgen, economy, wars, armies) runs **server-side**.
  The server's config is authoritative; client settings only affect UI.
- World state lives in `BepInEx/config/WarAndPeace/<world>.settlements.txt`.
  Back it up together with the world save.
- The file is stamped with the world seed: a foreign file with the same world
  name is set aside as `.bak` and the server starts clean.

## Updating the server
1. Stop the server.
2. Replace `BepInEx/plugins/WarAndPeace.dll` with the one from `latest/`.
3. Update the mod on every client (the updater .bat from the kit).
4. Start the server.

## Tips
- Recommended party size: up to 5 players.
- First login on a new world: the mod plans ~150 settlements in seconds;
  towns materialise as players discover them.

## Custom buildings on the server
Buildings are stamped **by the server**, so the building library lives there:

1. Take `.wapx` files (your own from the F7 Studio, or community ones).
2. Put them on the server into `BepInEx/config/WarAndPeace/layouts/`.
3. Restart the server — new templates join the pool and appear in settlements
   at generation, growth and post-war rebuilds.

Players do **not** need these files — buildings reach them as ordinary world
structures. Existing towns pick new templates up on their next growth/rebuild;
a fresh world uses them immediately.
