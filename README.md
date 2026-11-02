# UE4SS for Permafrost

Mods for the Steam game [Permafrost](https://store.steampowered.com/app/2254990/Permafrost/) run on the mod loader [UE4SS](https://github.com/UE4SS-RE/RE-UE4SS). UE4SS publishes builds that work with this game only as a rolling download that changes every few days and keeps no old files. This pack keeps one fixed UE4SS build downloadable. Install it once, then install any mod that lists it as a requirement.

- The files are the official UE4SS zips of build `3.0.1-1196`, byte for byte.
- UE4SS is made by the UE4SS team. This pack is not made or endorsed by them.
- This repo holds the pin of the build with its hashes, and the texts of the pack. The zips are in [Releases](https://github.com/ivmakk-pf/pf-ue4ss-pack/releases) and on [Nexus Mods](https://www.nexusmods.com/permafrost/mods/42).

**This is unofficial.** UE4SS and the mods that use it are not made or supported by the developer of Permafrost. If you find a bug in the game, remove your mods and check that the bug still happens before you report it to the developer.

## Install

Close the game. Download `UE4SS_v3.0.1-1196-g236adf26.zip` from [Releases](https://github.com/ivmakk-pf/pf-ue4ss-pack/releases) or from [Nexus Mods](https://www.nexusmods.com/permafrost/mods/42). The two files are the same. If you already have UE4SS, follow [Update an existing UE4SS](#update-an-existing-ue4ss) instead.

1. Extract the zip into the `Permafrost\Binaries\Win64` folder inside the game folder, the folder with `Permafrost-Win64-Shipping.exe`. Not into the top game folder with `Permafrost.exe`. Full path example for Steam: `C:\Program Files (x86)\Steam\steamapps\common\Permafrost\Permafrost\Binaries\Win64` *(to find the game folder in Steam: right-click Permafrost > Manage > Browse local files; in Epic Games or GOG Galaxy, open the install folder from the game's settings in the launcher)*.

Example after extraction (other game files omitted):

```text
C:\Program Files (x86)\Steam\steamapps\common\Permafrost\
├── Permafrost.exe
└── Permafrost\Binaries\Win64\
    ├── Permafrost-Win64-Shipping.exe
    ├── dwmapi.dll
    └── ue4ss\
        ├── UE4SS.dll
        ├── UE4SS-settings.ini
        └── Mods\
```

To check the install, start the game: `Permafrost\Binaries\Win64\ue4ss\UE4SS.log` appears, and its second line says `Git SHA #1ceefac8` (see [Why this build](#why-this-build) for why the number is not `1196`). Mods go into `ue4ss\Mods`.

## Update an existing UE4SS

You already have UE4SS, from an older download or from a mod manager. The zip holds the default `mods.txt`, `UE4SS-settings.ini`, and Blueprint mod load order (`load_order.txt`), which would replace yours. Keep them:

1. Close the game. In `Permafrost\Binaries\Win64\ue4ss`, copy `Mods\mods.txt`, `Mods\BPModLoaderMod\load_order.txt`, and `UE4SS-settings.ini` somewhere outside the game folder.
2. Extract the zip into `Permafrost\Binaries\Win64`, as in [Install](#install). When asked, replace the existing files.
3. Copy your `mods.txt` back into `ue4ss\Mods`, your `load_order.txt` back into `ue4ss\Mods\BPModLoaderMod`, and your `UE4SS-settings.ini` back into `ue4ss`, and replace the files from the zip.

Your mods stay in `ue4ss\Mods`. Their own settings files are not in the zip and stay as they are.

**Vortex users:** the Permafrost Vortex Extension installs UE4SS by itself, always the newest build, and replaces this one when it sets up the game. With the extension, you get its build, not this one.

## The zDEV file (for modders)

The optional file `zDEV-UE4SS_v3.0.1-1196-g236adf26.zip` is the official zDEV zip of the same build. Players do not need it. It has the same `UE4SS.dll` and `dwmapi.dll`, plus:

- `UE4SS.pdb`, the debug symbols of `UE4SS.dll`;
- the developer mods `EventViewerMod`, `KismetDebuggerMod`, `ActorDumperMod`, and `jsbLuaProfilerMod`;
- the UE4SS docs and the files for other games' configs and type dumps;
- a `UE4SS-settings.ini` with the GUI console on.

Install it with the steps of [Update an existing UE4SS](#update-an-existing-ue4ss), so your `mods.txt` and settings stay. Then turn on each developer mod that you want: add a line `<Name> : 1` to `ue4ss\Mods\mods.txt` above the `Keybinds` line, for example `EventViewerMod : 1` or `KismetDebuggerMod : 1`. For the GUI console, set `ConsoleEnabled`, `GuiConsoleEnabled`, and `GuiConsoleVisible` to `1` in your `UE4SS-settings.ini`.

## Problems

- **No `UE4SS.log` after the start.** Check the file location. `dwmapi.dll` must be in the same folder as `Permafrost-Win64-Shipping.exe` (`Permafrost\Binaries\Win64`), not beside `Permafrost.exe`. If the zip made an extra folder, move its contents up into `Permafrost\Binaries\Win64`.
- **The antivirus warns about `dwmapi.dll`.** This file is how UE4SS starts: the game loads it because of its name, and it then loads UE4SS. Some antivirus programs flag this method. The file is the same as in the official download, and [Verify the download](#verify-the-download) shows how to check.
- **A mod stopped after a game update.** A game update can break UE4SS or a mod. Check here and on the pages of your mods for an update. To play in the meantime, uninstall. Saves are not touched.
- **The game does not start at all.** Uninstall, then in Steam use Properties, Installed Files, Verify integrity of game files.

UE4SS bugs that are not about this pack belong to the [UE4SS project](https://github.com/UE4SS-RE/RE-UE4SS/issues).

## Uninstall

Close the game. To keep your mods and settings, copy `ue4ss\Mods` and `ue4ss\UE4SS-settings.ini` somewhere outside the game folder.

Delete these from the `Permafrost\Binaries\Win64` folder inside the game folder:

```text
dwmapi.dll
ue4ss\
```

Deleting the `ue4ss` folder also removes all installed mods and their settings. Keep all other files. The game then runs without mods. These steps do not delete your save files.

## Verify the download

The files of this pack are the official zips of UE4SS build 1196, byte for byte:

| File | SHA-256 |
|---|---|
| `UE4SS_v3.0.1-1196-g236adf26.zip` | `75DC8B081D324FE0598A87B26E37D13A84D3648CBB1D08EB48C514376407A11B` |
| `zDEV-UE4SS_v3.0.1-1196-g236adf26.zip` | `8C48F66ED91EAA1B60212101497918FFC108B8DBC846DE8CA8CBD09FBE4E6941` |

Open PowerShell and run this command with the path to your download:

```powershell
Get-FileHash -Algorithm SHA256 "C:\Downloads\UE4SS_v3.0.1-1196-g236adf26.zip"
```

The hash must equal the value in the table. A download from Nexus gets a longer file name, with the same contents and the same hash. The table values are the SHA-256 of the files that the [experimental-latest](https://github.com/UE4SS-RE/RE-UE4SS/releases/tag/experimental-latest) page served on 2026-11-02, also recorded in `pack.json`.

## Why this build

Permafrost runs on Unreal Engine 5.4. The last stable UE4SS release, `v3.0.1` of February 2024, is older than UE 5.4. The builds that work with this game are on the [experimental-latest](https://github.com/UE4SS-RE/RE-UE4SS/releases/tag/experimental-latest) page, which keeps only the newest build. The mods that require this pack are tested on build 1196, and the pack keeps that build downloadable after the experimental page moves on.

Build 1196 (release commit `236adf2`) changed only one built-in Lua file. The UE4SS release workflow then reuses `UE4SS.dll` and `dwmapi.dll` of the build before, from commit `1ceefac8`. So `UE4SS.log` says `Git SHA #1ceefac8`, and that is correct for this build.

A newer UE4SS build is not tested with the mods until this pack moves to it.

## For maintainers

`pack.json` is the pin: the build label, the release commit, the DLL commit (the one that `UE4SS.log` names), and for the `player` and the `zdev` zip the official file name, the official URL, and the SHA-256. The official zips stay in the gitignored `cache/` and in the GitHub release of each pinned build.

### Update the pin

The pin is the build that the mods are tested against. It moves when that build stops working with the game, or when the mods move to a newer build.

1. Download both zips of the new build from [experimental-latest](https://github.com/UE4SS-RE/RE-UE4SS/releases/tag/experimental-latest) into `cache/` at once: the page keeps no old zips. Put the build label, the release commit, the file names, the URLs, and the SHA-256 values into `pack.json`. The DLL commit comes from the test of step 3.
2. Update the component list under [Credits and license](#credits-and-license) when the bundled components changed.
3. Test on a clean install: move `dwmapi.dll` and `ue4ss\` out of `Permafrost\Binaries\Win64` (on the same drive, so links stay links), extract the new zip, start the game, and read `UE4SS.log`: put its `Git SHA` into the DLL commit of `pack.json`, and check for no error. Then put the old install back, run the update steps, and test the mods that require this pack.
4. Update the build values in this README, `nexus/`, and `CHANGELOG.md`, then release with the tag `v<build>` and both official zips as assets. Check that the digest of each asset equals its SHA-256 in `pack.json`.

### Test record

The tests below used zips with the same official files under `Permafrost/Binaries/Win64/`, extracted into the game folder. Each file that lands in the game is byte for byte the file of the official zip at the same path, so the results hold for the official zips.

- 2026-11-02, game 0.44.5.4788 (Steam build 26265449), UE 5.4.4: the player zip on a clean install (the earlier UE4SS moved out of the game folder). The zip adds 21 files and overwrites no game file. `UE4SS.log` names `Git SHA #1ceefac8`, the built-in mods of `mods.txt` start, the game reaches the main menu, and the only warning (`Failed to expose size of 'class RC::Unreal::FObjectPtrProperty'`) is also in the log of the build before. Deleting the Uninstall list leaves exactly the files of the game before the install.
- 2026-11-02, same game version: the update steps over an earlier UE4SS (`1ceefac8`, from the Permafrost Vortex Extension, with the mods of other authors and our mods installed), first with the player zip, then with the zDEV zip. `mods.txt` and `UE4SS-settings.ini` stay byte for byte the same, the Vortex hard links of the mods stay links, and `UE4SS.dll` is the same in both zips. In a world, each mod of `mods.txt` and each `enabled.txt` mod starts, also `EventViewerMod` and `KismetDebuggerMod` of the zDEV zip and a C++ test mod, and BetterWoodcutting, ProximityPickup, and FastTravelFromMap log their features with no error. The first start of this run crashed after 16 seconds in the D3D12 renderer (`FD3D12DeferredInitView::CreateViews`). The same crash came on 2026-10-31 with an earlier UE4SS build, and the DLLs of this build are the same files as that build, so it is not a change of this build. The next start ran with no crash.

## Credits and license

UE4SS is the work of the [UE4SS team](https://github.com/UE4SS-RE/RE-UE4SS) and its contributors, licensed under MIT. The zips are unmodified redistributions, and each holds the UE4SS license as `ue4ss/LICENSE`.

UE4SS bundles these components, each under its own license. Where a component offers a choice of licenses, the choice is MIT.

- UE4SS (`UE4SS.dll`, `dwmapi.dll`, the built-in mods, the docs) - MIT - https://github.com/UE4SS-RE/RE-UE4SS
- Lua 5.4.7 (in `UE4SS.dll`) - MIT, Copyright (C) 1994-2024 Lua.org, PUC-Rio - https://www.lua.org
- Unreal pseudo code (UEPseudo, in `UE4SS.dll`) - engine type layouts from the UE4SS team, derived from Unreal Engine source. It has no open license, and its source is open only to GitHub accounts linked to Epic Games - https://github.com/Re-UE4SS/UEPseudo
- glaze 6.4.0 - MIT - https://github.com/stephenberry/glaze
- {fmt} 11.2.0 - MIT with the {fmt} binary exception - https://github.com/fmtlib/fmt
- Dear ImGui 1.92.1 - MIT - https://github.com/ocornut/imgui
- ImGuiColorTextEdit 1.2.0 (UE4SS fork) - MIT - https://github.com/UE4SS-RE/ImGuiColorTextEdit
- IconFontCppHeaders - zlib - https://github.com/juliettef/IconFontCppHeaders
- GLFW - zlib/libpng - https://github.com/glfw/glfw
- glad 0.1.36 (generated OpenGL 3.3 loader) - public domain; `khrplatform.h` - Khronos MIT-style license - https://github.com/Dav1dde/glad
- Zydis 4.1.1 and Zycore - MIT - https://github.com/zyantific/zydis
- PolyHook 2 - MIT - https://github.com/stevemk14ebr/PolyHook_2_0
- AsmJit and AsmTK - zlib - https://github.com/asmjit/asmjit
- raw_pdb - BSD-2-Clause - https://github.com/MolecularMatters/raw_pdb
- moodycamel ConcurrentQueue (`EventViewerMod`, zDEV file only) - Simplified BSD or Boost Software License 1.0 - https://github.com/cameron314/concurrentqueue
- patternsleuth and patternsleuth_scanner (in `UE4SS.dll`) - MIT or Apache-2.0 - https://github.com/trumank/patternsleuth
- The Rust crates of patternsleuth (in `UE4SS.dll`):
  - MIT or Apache-2.0: anyhow 1.0.99, cfg-if 1.0.3, crc32fast 1.5.0, crossbeam-channel 0.5.15, crossbeam-deque 0.8.6, crossbeam-epoch 0.9.18, crossbeam-utils 0.8.21, either 1.15.0, flate2 1.1.2, futures 0.3.31 and its futures-* crates, hashbrown 0.14.5, heck 0.4.1, inventory 0.3.21, itertools 0.12.1, lazy_static 1.5.0, lock_api 0.4.13, object 0.32.2, once_cell 1.21.3, parking_lot_core 0.9.11, pin-project 1.1.10, pin-project-internal 1.1.10, pin-project-lite 0.2.16, pin-utils 0.1.0, rayon 1.11.0, rayon-core 1.13.0, scopeguard 1.2.0, smallvec 1.15.1, static_assertions 1.1.0, windows 0.52.0, windows-core 0.52.0, windows-targets 0.52.6, windows_x86_64_msvc 0.52.6
  - MIT: dashmap 5.5.3, futures-scopes 0.2.0, iced-x86 1.21.0, ruzstd 0.5.0, slab 0.4.11, strum 0.25.0, strum_macros 0.25.3, tracing 0.1.41, tracing-attributes 0.1.30, tracing-core 0.1.34, twox-hash 1.6.3
  - Unlicense or MIT: byteorder 1.5.0, memchr 2.7.5
  - 0BSD, MIT, or Apache-2.0: adler2 2.0.1
  - MIT, Zlib, or Apache-2.0: miniz_oxide 0.8.9
  - Build time only, no code in the DLL: derive_more 0.99.20 (MIT), paste 1.0.15, proc-macro2 1.0.101, quote 1.0.40, rustversion 1.0.22, syn 2.0.106 (MIT or Apache-2.0), unicode-ident 1.0.18 ((MIT or Apache-2.0) and Unicode-3.0)

This repo is licensed under MIT, the same license as UE4SS. See `LICENSE`.
