# DUDE Mod SDK: Denton's Enhanced Doom 3 (`dentonmod` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**Denton's Enhanced Doom 3** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/dentonmod) (GPLv3; the mod by
Clone JC Denton), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `dentonmod` (`dentonmod.dll` / `dentonmod.so`, built from `game/`)

No game data is included. You need Denton's Enhanced Doom 3 game data (ModDB); the folder must be named dentonmod/ (lowercase), plus your own Doom 3.

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`dentonmod-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/dentonmod/dentonmod.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=OFF` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

*The original README of this port is `README.txt`.*
