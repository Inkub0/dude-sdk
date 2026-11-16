# DUDE Mod SDK: Classic Doom 3 (`cdoom` branch)

The Classic Doom 3 game library (`cdoom.so` / `cdoom.dll`) for [DUDE](https://github.com/Inkub0/dude),
built from the `cdoom` branch of [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk) - the dhewm3
project's GPLv3 port of Flaming Sheep Software's **Classic Doom 3** (the first episode of the original
Doom, remade in the Doom 3 engine).

## Licence

GPLv3 (`COPYING.txt`), the same licence as dhewm3 and DUDE. Classic Doom 3's game code was released
by its authors under the GPL and is carried as a branch of the dhewm3 Mod SDK; this branch of the
[DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) forks it. It talks to DUDE only across the game-library boundary (`GetGameAPI`), and no DUDE code
is copied in here.

You need your own copy of the Classic Doom 3 game data (and Doom 3) to play; **no game data is
included** - the pak files are the mod authors' and are not redistributed here.

Doom and Doom 3 are trademarks of id Software / ZeniMax Media; Classic Doom 3 is the work of Flaming
Sheep Software. This is an independent community project, not affiliated with or endorsed by any of
them.

## Layout

- The source tree is the dhewm3 Mod SDK `cdoom` branch as the dhewm3 project ships it: `game/` (the
  Classic Doom 3 game code, built as the `cdoom` library), `d3xp/`, `idlib/`, and the engine-interface
  headers (`framework/`, `renderer/`, `sound/`, `cm/`, `ui/`, `sys/`).
- `MinGW-x86_64.cmake` and the win64 handling in `CMakeLists.txt` are the DUDE Mod SDK's additions, so
  the library can be cross-compiled 64-bit for Windows (upstream ships no win64 build).

## Building

The game library and the engine exchange C++ objects, so the library must be built with the same
compiler and ABI as the DUDE binary it runs in (DUDE uses the dhewm3 game API, version 9). Classic
Doom 3 is a base-game mod, so it builds from `game/` with `-DBASE=ON -DD3XP=OFF`, producing the
`cdoom` library.

Linux (native):

```
cmake -S . -B build-linux -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=OFF
cmake --build build-linux -j$(nproc)        # -> build-linux/cdoom.so
```

Windows, cross-compiled from Linux with MinGW like DUDE's `dude.exe`:

```
cmake -S . -B build-win -DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=OFF
cmake --build build-win -j$(nproc)          # -> build-win/cdoom.dll
```

## Installing

DUDE loads `<fs_basepath>/cdoom/cdoom.{so,dll}`. Put the library next to the Classic Doom 3 game
data, which you supply yourself:

```
<game>/
  base/      Doom 3 pak files (from your Doom 3 install)
  cdoom/     Classic Doom 3 pak files
    cdoom.so  /  cdoom.dll     <- this library
```

Then run DUDE with `+set fs_basepath <game> +set fs_game cdoom`. A DUDE build with mod auto-download
can also fetch this library for you when the Classic Doom 3 mod is selected and the library is
missing; it verifies the download against a known checksum before use.

## Releases

Built libraries are published as releases of the DUDE Mod SDK tagged `cdoom-vX.Y.Z`:
`cdoom-win64.dll` and `cdoom-linux-x86_64.so`, plus an archive per platform with the library,
`COPYING.txt` and this README. No game data. The release line follows the game interface (dhewm3
API 9), not DUDE's version.

## Provenance

The source is the `cdoom` branch of github.com/dhewm/dhewm3-sdk, the dhewm3 project's GPLv3 port of
Flaming Sheep Software's Classic Doom 3. The original Classic Doom 3 game assets are not part of this
branch.
