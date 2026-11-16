# DUDE Mod SDK: ELDOOM (`eldoom` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**ELDOOM** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/eldoom) (GPLv3; the mod by
Ez0n3), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `eldoom` (`eldoom.dll` / `eldoom.so`, built from `game/`)

No game data is included. You need ELDOOM game data (ModDB), plus your own Doom 3.

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`eldoom-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/eldoom/eldoom.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=OFF` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

# ELDOOM

A singleplayer campaign for Doom3 with lots of action.  
A full story from beginning to end. High quality portal skies. Large custom quality maps.
Always run with no stamina (toggleable on/off). Slightly modified weapons (toggleable on/off).
Classic nightmare mode (toggleable on/off). New custom cinematics and animations and much more...

You can download it at https://www.moddb.com/mods/eldoom/downloads/eldoom-v09b

After compiling the source, you can start the game with  
  `./dhewm3 +set fs_game eldoom`
  
A big THANK YOU to "Ez0n3" (and the rest of the ELDOOM Team) for releasing this mod under GPL
and porting it to dhewm3 :)
