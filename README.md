# DUDE Mod SDK: Perfected Doom 3 (`perfected` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**Perfected Doom 3** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/perfected) (GPLv3; the mod by
VGames), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `perfected` (`perfected.dll` / `perfected.so`, built from `game/`)
- `perfected_roe` (`perfected_roe.dll` / `perfected_roe.so`, built from `d3xp/`): the Resurrection of Evil version, needs `d3xp/` data too

No game data is included. You need Perfected Doom 3 game data (ModDB); folders must be named perfected/ and perfected_roe/ (lowercase), plus your own Doom 3 (and Resurrection of Evil for the RoE version).

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`perfected-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/perfected/perfected.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=ON` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

# Perfected Doom 3

The source code to build the game DLLs for both Perfected Doom 3 and Perfected Doom 3 RoE for dhewm3.

Thanks to *VGames* for releasing the source under GPL!

You can download the mod itself at https://www.moddb.com/mods/perfected-doom-3-version-500/downloads

**Note** that you should **rename the `Perfected/` game directory to `perfected/`**, and **`Perfected_ROE` to `perfected_roe`**, because Doom3 doesn't like upper-case characters in mod directories, especially on operating systems that are case-sensitive, like Linux.
