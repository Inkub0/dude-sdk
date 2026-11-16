# DUDE Mod SDK: Blood Mod (`bloodmod` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**Blood Mod** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/bloodmod) (GPLv3; the mod by
ALord7), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `bloodmod` (`bloodmod.dll` / `bloodmod.so`, built from `game/`)
- `bloodmod_roe` (`bloodmod_roe.dll` / `bloodmod_roe.so`, built from `d3xp/`): the Resurrection of Evil version, needs `d3xp/` data too

No game data is included. You need Blood Mod game data (ModDB), plus your own Doom 3 (and Resurrection of Evil for the RoE version).

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`bloodmod-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/bloodmod/bloodmod.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=ON` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

# Blood Mod 1.8

Thanks to *ALord7* for giving me the mods source code for porting!

You can download the game data at https://www.moddb.com/mods/blood-mod
