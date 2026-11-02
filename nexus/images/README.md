# Nexus images

Rendered with the nexus-mod-images skill from `content.json` and the screenshot in `src/`, with the fonts and colors of the Permafrost mods (`MOD-IMAGES.md` of the workspace). No image uses a UE4SS logo: UE4SS has no official logo.

| File | Size | Role | Content |
|---|---|---|---|
| `00-thumbnail.jpg` | 1920x1080 | Gallery, first (Nexus uses it as the mods-grid thumbnail) | The word "UE4SS" in gold at title size 420, in the center, and under it the game logo (`UI/Credits/Textures/T_Mainmenu_logo`, the `titleImage`) at the same width, 920 px. The form follows other "UE4SS for <game>" pages on Nexus, such as the one for Subnautica 2. The background is a crop of the main menu (`src/main-menu.jpg`, game 0.44.5.4788), the player at the fire barrel with the dog, under an even dark layer of 65 % so that the logo reads at the smallest card size. The user's pick of 2026-11-03, over the word alone, a larger word, a smaller logo, and a dark oval. |
| `01-console.jpg` | 1920x1080 | Gallery, second | A working install: the main menu (`src/main-menu-console-run.jpg`, a Steam screenshot of 2026-11-03) with the UE4SS GUI console window (`src/gui-console.png`, a capture of that window) over its right half, scaled up to 860 px high so the text reads, with a soft shadow. The console shows the top of the log: the line `UE4SS - v3.0.1 Beta #0 - Git SHA #1ceefac8`, the mod start, and the scan. The value of the `Timezone` line is painted over with the log background (the user's location). The GUI console was on only for this capture (`GuiConsoleEnabled` and `GuiConsoleVisible` in `UE4SS-settings.ini`); the player zip has it off. Composed with a Pillow script, not with the image tool. |
| `background.jpg` | 1300x372 | Page background | The red moon of the main menu, cropped right of the game logo, darkened on the left and at the bottom. |

`src/main-menu.jpg` is a 3840x2160 screenshot of the main menu of a clean install of this pack (2026-11-02). The game logo comes from the game files through the icon extract of `MOD-IMAGES.md` into the gitignored `game/icons/` of the workspace, so it is not in this repo.
