# Nexus page

- Title: UE4SS Pack for Permafrost
- Game domain: `permafrost` (add-mod page: https://www.nexusmods.com/permafrost/mods/add)
- Mod id and URL: not published yet. Record them here after the page exists.
- Category: Utilities (id 13, from `tools/nexus_categories.py permafrost`)
- Version: `3.0.1-1196` (the label of the pinned UE4SS build: the official asset name without its `g<sha>` part)
- Main file under Manage Files: `UE4SS Pack 3.0.1-1196`, the official zip `UE4SS_v3.0.1-1196-g236adf26.zip` from `cache/`, category Main files. It is the same file as the GitHub Release asset. Also mark it with "Set as primary file for download": the top Manual download button of the page gives the primary file. Turn "Allow mod manager download" off: the Permafrost Vortex Extension manages UE4SS by itself. File description (plain text, at most 255 characters):

```
The official UE4SS zip of build 3.0.1-1196, byte for byte. Extract into Permafrost\Binaries\Win64 inside the game folder. Already have UE4SS? Follow the Update steps on the Description tab to keep your mods.txt and settings.
```

- Optional file under Manage Files: `UE4SS Pack 3.0.1-1196 zDEV`, the official zip `zDEV-UE4SS_v3.0.1-1196-g236adf26.zip` from `cache/`, category Optional files, version `3.0.1-1196`. Turn "Allow mod manager download" off. File description:

```
For modders only. The official zDEV zip of the same build: UE4SS.pdb, the developer mods, and the docs. Install with the Update steps, then turn on the developer mods in mods.txt.
```

- A new pinned build: upload its 2 zips as the new main and optional files, and move the files of the old build to Old files. Do not delete them: players can go back to an older build.
- Requirements: none.
- Do not post the page in the game's Steam forum or Discord.

## Permissions

The files are the UE4SS team's work under MIT, so the page does not claim them, and grants what MIT grants.

- Other users' assets: yes, all the loader files belong to the UE4SS team. Credit them in the credits field.
- Upload to other sites: allowed, with credit to the UE4SS team.
- Modification and reuse: allowed under MIT, with credit.
- Conversion to other games: allowed.
- Use in paid mods or for donation points: not allowed. Keep donation points off for this page.
- Credits field (plain text, no BBCode):

```
UE4SS is made by the UE4SS team and contributors: https://github.com/UE4SS-RE/RE-UE4SS
It is licensed under MIT, which permits this unmodified redistribution. The license text is in each zip (ue4ss/LICENSE).

All files in this pack are the official UE4SS build 3.0.1-1196 (UE4SS_v3.0.1-1196-g236adf26.zip and zDEV-UE4SS_v3.0.1-1196-g236adf26.zip) from https://github.com/UE4SS-RE/RE-UE4SS/releases, unchanged. I made none of them.

UE4SS bundles these components, each under its own license: Lua (MIT), Dear ImGui (MIT), {fmt} (MIT), glaze (MIT), GLFW (zlib), Zydis and Zycore (MIT), PolyHook 2 (MIT), AsmJit (zlib), raw_pdb (BSD-2-Clause), patternsleuth and its Rust crates (MIT or Apache-2.0), and the UE4SS team's Unreal pseudo code. The full list: https://github.com/ivmakk-pf/pf-ue4ss-pack#credits-and-license
```
