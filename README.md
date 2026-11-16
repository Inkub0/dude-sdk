# DUDE Mod SDK: Doom 3: Phobos (`tfphobos` branch)

The Doom 3: Phobos game library (`tfphobos.so` / `tfphobos.dll`) for [DUDE](https://github.com/Inkub0/dude),
built from the `tfphobos` branch of [TwelveEyes/dhewm3-sdk](https://github.com/TwelveEyes/dhewm3-sdk) -
a community compatibility patch that runs Team Future's **Doom 3: Phobos** on the dhewm3 game API.

## Licence

GPLv3 (`COPYING.txt`), the same licence as dhewm3 and DUDE. The dhewm3 Mod SDK this derives from
replaced the original Doom 3 SDK licence with GPLv3, so this code is GPLv3 throughout. That is why,
unlike the Quake 4 library, it can share DUDE's licence; it still talks to DUDE only across the
game-library boundary (`GetGameAPI`), and no DUDE code is copied in here.

This is **not** official Team Future work and is not endorsed by them - it is the community
compatibility patch by TwelveEyes (see Provenance). You need your own copy of the Doom 3: Phobos
game data (and Doom 3) to play; **no game data is included** - the pak files are Team Future's and
are not redistributed here.

Doom and Doom 3 are trademarks of id Software / ZeniMax Media; Doom 3: Phobos is the work of Team
Future. This is an independent community project, not affiliated with or endorsed by any of them.

## Layout

- The source tree is the dhewm3 Mod SDK `tfphobos` branch as TwelveEyes shipped it (initial commit,
  unmodified): `game/` and `d3xp/` (the Phobos game code, built as the `tfphobos` library), `idlib/`,
  and the engine-interface headers (`framework/`, `renderer/`, `sound/`, `cm/`, `ui/`, `sys/`).
- `MinGW-x86_64.cmake` and the win64 handling in `CMakeLists.txt` are the DUDE Mod SDK's additions,
  so the library can be cross-compiled 64-bit for Windows (upstream ships only a 32-bit DLL).
- Later commits adapt the build to DUDE: one change per commit, each saying what it changes and why.

## Building

The game library and the engine exchange C++ objects, so the library must be built with the same
compiler and ABI as the DUDE binary it runs in (DUDE uses the dhewm3 game API, version 9).
`D3XP=ON` builds the `tfphobos` library from `d3xp/` (Phobos is a d3xp-based mod); `BASE=OFF`
skips the plain `base` game.

Linux (native):

```
cmake -S . -B build-linux -DCMAKE_BUILD_TYPE=Release -DD3XP=ON -DBASE=OFF
cmake --build build-linux -j$(nproc)        # -> build-linux/tfphobos.so
```

Windows, cross-compiled from Linux with MinGW like DUDE's `dude.exe`:

```
cmake -S . -B build-win -DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake -DCMAKE_BUILD_TYPE=Release -DD3XP=ON -DBASE=OFF
cmake --build build-win -j$(nproc)          # -> build-win/tfphobos.dll
```

## Installing

You need your own Doom 3, Resurrection of Evil and Doom 3: Phobos; no game data is included.
Phobos is the work of Team Future, and it runs on top of Resurrection of Evil.

1. Take `tfphobos.dll` (Windows) or `tfphobos.so` (Linux) out of the release archive for your
   system. The bare `tfphobos-win64.dll` / `tfphobos-linux-x86_64.so` release assets are the same
   files; rename them to `tfphobos.dll` / `tfphobos.so` if you use those.
2. Put the library in the Phobos folder, next to its pak files. DUDE loads
   `<fs_basepath>/tfphobos/tfphobos.{so,dll}`, so the game folder looks like this:

   ```
   <game>/
     base/        Doom 3
     d3xp/        Resurrection of Evil
     tfphobos/    Phobos pak files + z_pak000_dhewm3.pk4, autoexec.cfg
       tfphobos.so  /  tfphobos.dll     <- this library
   ```

   The GOG release of Doom 3: Phobos already comes laid out this way. If your Phobos install is
   separate, copy its `tfphobos` folder next to your Doom 3 `base/` and `d3xp/`.
3. Start DUDE with that folder as its game data (the folder it finds `base/` in), open **Mods** in
   the main menu and pick Phobos. DUDE loads Resurrection of Evil underneath it by itself.

DUDE versions after 0.9.9 can do steps 1 and 2 for you: pick Phobos in the Mods menu and DUDE
offers to download the library from this branch's release, checks it against a known checksum
and installs it.

To start it from the command line instead: `dude +set fs_basepath <game> +set fs_game tfphobos`
(`dude.exe` on Windows). Leave out `fs_basepath` when DUDE already runs from `<game>`.

## Releases

Built libraries are published as releases of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk)
tagged `tfphobos-vX.Y.Z`, never inside DUDE's: `tfphobos-win64.dll` and `tfphobos-linux-x86_64.so`,
plus an archive per platform with the library, `COPYING.txt` and this README. No game data.

## Versions

This branch has its own release line and is not tied to any particular DUDE version. The only
compatibility requirement is the dhewm3 game API: this library targets **API version 9**, a frozen
ABI, so it loads into any engine that exposes it (DUDE 0.9.x and later). Releases are tagged
`tfphobos-vX.Y.Z` on their own schedule; the branch tracks the latest work.

## Provenance

The source is the `tfphobos` branch of github.com/TwelveEyes/dhewm3-sdk (a fork of
github.com/dhewm/dhewm3-sdk), a community compatibility patch that reimplements Doom 3: Phobos on
the dhewm3 game API, licensed GPLv3. The original Doom 3: Phobos is the work of Team Future; its
game assets are not part of this branch. The patch's own notes record what it does and does
not reproduce (the biohelmet, a 1:1 clickable item GUI, camera blur and bloom are not implemented).
