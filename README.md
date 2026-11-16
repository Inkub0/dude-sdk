# DUDE Mod SDK: LibreCoop (`librecoop` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**LibreCoop** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/librecoop) (GPLv3; the mod by
Stradex), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `librecoop` (`librecoop.dll` / `librecoop.so`, built from `game/`)
- `librecoopd3xp` (`librecoopd3xp.dll` / `librecoopd3xp.so`, built from `d3xp/`): the Resurrection of Evil version, needs `d3xp/` data too

No game data is included. You need LibreCoop game data (ModDB), plus your own Doom 3 (and Resurrection of Evil for the RoE version).

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`librecoop-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/librecoop/librecoop.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=ON` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

# LibreCoop for Dhewm3

Open source coop mod for the Dhewm3 source port. It supports Doom 3 and Doom 3 resurecction of evil.

(modification)

You can download the gamedata at https://www.moddb.com/mods/librecoop-dhewm3-coop/downloads
(currently Alpha 1.5)

Furthermore, this repo contains a `librecoop2.pk4` that contains an updated stringtable for both
`librecoop/` and `librecoopd3xp/` - the ones contained in Alpha 1.5 are incomplete.
