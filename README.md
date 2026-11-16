# DUDE Mod SDK: Hard Corps (`hardcorps` branch)

This branch of the [DUDE Mod SDK](https://github.com/Inkub0/dude-sdk) is the dhewm3 port of
**Hard Corps** from [dhewm3-sdk](https://github.com/dhewm/dhewm3-sdk/tree/hardcorps) (GPLv3; the mod by
Revility and Ivan_the_B), plus the build changes for DUDE's 64-bit Windows library. The game code is unchanged
from dhewm3's port.

Libraries:
- `hardcorps` (`hardcorps.dll` / `hardcorps.so`, built from `game/`)

No game data is included. You need Hard Corps game data (ModDB), plus your own Doom 3.

**In DUDE:** pick the mod in the **Mods** menu; DUDE offers to download the library from this
branch's release (`hardcorps-vX.Y.Z`) and checks it against a pinned SHA-256. By hand: put the library in
the mod's folder next to its pak files (`<game>/hardcorps/hardcorps.dll` or `.so`).

**Building:** `cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DBASE=ON -DD3XP=OFF` (add
`-DCMAKE_TOOLCHAIN_FILE=MinGW-x86_64.cmake` and use `build-win` for the 64-bit Windows DLL). The
Linux release libraries are built in DUDE's Ubuntu 22.04 sandbox so they load on glibc 2.35 and newer.

---

*Below: this branch's README from dhewm3-sdk.*

> This allows you to run the Hard Corps mod in dhewm3!
> 
> It's the updated/remastered version of the HardQore2 mod for Doom3.
> 
> A big thank you to Revility (and the rest of the HardQore2 team) for releasing
> the source under GPL, so I could port it to dhewm3 - and for explicitly
> developing Hard Corps for dhewm3! :-)
> 
> You can  get the game data at:
> https://www.moddb.com/mods/hardcorps/downloads
> 
> Revility's Hard Corps git repo: https://github.com/revility/hardcorps
> It only contains changed files, so it doesn't compile as it is but needs
> the dhewm3 SDK as a base. I recommend just using the code hosted here
> ( https://github.com/dhewm/dhewm3-sdk/tree/hardcorps ), it works as it is.

# DHEWM 3 HARD CORPS
Updated files for Doom 3: Harqore 2 Dhewm 3 sdk.  This is an online back up of the updated files only during development.  The original sdk with all files is over at dhewm3 sdk's hub.  They are meant to be used with Hard Corps 1.0.00 for Dhewm 3 1.5.0+ after it is released.  It will not work with the original HardQore 2012 release.

Formerly known as HardQore 2 for Doom 3;  the Dhewm 3 version features many improvements and additions to the game while running on a modern source port of Doom 3.  Doom 3: Hardqore 2 was a good start in the right direction, but was lacking many features and changes needed to turn Doom 3 into a 2.5d action sidescroller.  The main goal of the release of Hard Core for Dhewm 3 was to match the gameplay of classic 2d action platformers such as Contra, Metal Slug, Ninja Gaiden, Metroid, and Castlevania.

Potential mod makers and map authors will find a host of features to achieve many of the most common gameplay mechanics and enemies encountered in action platformers.  We kept the mapper in mind during development and tried to make it as simple as possible to add in the new features.  Many documents, tutorials and examples have been included.

# UPGRADES, ADDITIONS, FIXES & CHANGES:

+Dhewm 3 port supports modern resolutions, modern hardware, multiple OOS, updated built in editing tools and much, much more.

+Replaced D3 ROE Bloom with Denton/Rivensin's HDR lighting

+Updated Main Menu: New images, new & more options.

+New Hud . Includes read outs for all ammo types and new images.

+Upgraded Textures for many enemies

+Many updates to enemy AI and animations tweaks for more classic 2d action platformer behaviour

+Added more varients to enemies.

+Much More responsive Keyboard/Controller aiming

+New player damage feed back system. Similar to many classic side scrollers.

+Revamped Weapon Arsenal. Includes new weapons, models, new effects, animations, and ammo use

+Melee combat overhauled.  Player can instantly access a quick melee weapon

+Charge Attack in 8 directions while on the ground and in air.  Charge attacks deal massive damage and slowly recharge.

+Slide Attack improved

+New textures and map objects.

+More movable and breakable objects

+Jump through platforms added

+Improved Music system.

+Multiple Character select with custom stats support.

+New playable character added: Scarlet Rivensin

+Upgraded 2d camera system

+Many bug fixes. This includes player respawning, save points, music and the camera.

+More responsive Doors

+New Map:  Hell Rizer

+Updated Maps: Wasted Hate and Playground

+Motion Trails for Melee Weapons

+Improvements to player animations

+New input based animation and attack system added for the player.  This is similar to the Special moves and combos found in Street Fighter and Mortal Kombat.

+New Ammo Types and revamped old ones

+New items and power ups.

+Breakable item containers similar to many classic action platformers.
