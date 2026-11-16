# DUDE Mod SDK: Scarlet Rivensin: The Ruiner (`rivensin` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**Scarlet Rivensin: The Ruiner** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/rivensin) (GPLv3; the mod by
Revility and the Rivensin team), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `rivensin` (`rivensin.dll` / `rivensin.so`, built from `game/`)

No game data is included. You need Scarlet Rivensin game data (ModDB, its dhewm3/rivensin folder), plus your own Doom 3.

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`rivensin-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/rivensin/rivensin.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=OFF` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

*The original README of this port is `README.txt`.*
