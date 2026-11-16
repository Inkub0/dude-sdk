# DUDE Mod SDK: Desolated - The Crying Fate (`desolated` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**Desolated - The Crying Fate** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/desolated) (GPLv3; the mod by
DaveTheFreak and team), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `desolated` (`desolated.dll` / `desolated.so`, built from `game/`)

No game data is included. You need Desolated game data (ModDB); the folder must be named desolated/ (lowercase), plus your own Doom 3.

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`desolated-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/desolated/desolated.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=OFF` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

# Desolated - The Crying Fate

Desolated - The Crying Fate is a Total Conversion based on Doom 3.
It comes with a complete new storyline about the shade between good and evil plus two other gamemodes.
A quest-, rpg- and moneysystem are just a few of the many new game mechanics that will await you.
If you want to see everything you'll need at least 7-8 hours... but let the game speak for itself,
download and have fun playing!

You can download the gamedata at https://www.moddb.com/mods/desolated-the-crying-fate

**NOTE:** *Especially if you're not using Windows, make sure to rename the gamefolder
from the download to `desolated` (all lower-case)!*

Thanks a lot to the *Desolated team* for releasing the source code!

**This is still a work-in-progress.** It seems like I didn't get the latest code so some features (esp. the skillbook) are missing. Apart from that it seems generally playable though.
