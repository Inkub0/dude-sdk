# DUDE Mod SDK: Real Gibs (`realgibs` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**Real Gibs** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/realgibs) (GPLv3; the mod by
darknar; dhewm3 port by ALord7), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `realgibs` (`realgibs.dll` / `realgibs.so`, built from `game/`)

No game data is included. You need Real Gibs game data (ModDB), plus your own Doom 3.

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`realgibs-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/realgibs/realgibs.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=OFF` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

# Real Gibs 1.06

This mod adds a gibbing effect to most monsters in the game.

Big thanks to *darknar* for releasing the mods source code, and to *ALord7* for porting it to dhewm3!

You can download the mod at https://www.moddb.com/games/doom-iii/addons/real-gibs-v106-for-dhewm3-32-bit
