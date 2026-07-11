# the-macOS-games-fixes-repo
a centralized list of every known fix and upgrade for native games on macOS

## Selecting an older branch on Steam

- [Garry's Mod](https://www.reddit.com/r/macgaming/comments/1ur57yo/how_to_play_garrys_mod_on_m1_macs/)
- [The Talos Principle](https://www.reddit.com/r/macgaming/comments/1urxo1p/a_fix_for_the_talos_principle/)

## Fixing codesigning issues

Several games won't launch due to codesigning issues:
- Badland
- Janosik
- Asterix & Obelix XXL Romastered

to fix it, copy the next line:  
`codesign --force --deep --sign - `  
Open the Terminal and paste the line without hitting enter.  
in Steam, click the gear icon in the game description and select "manage" > "browse local files", it'll open a Finder window containing the game. Drag and drop the icon into the Terminal window and hit enter. The game will now launch correctly.

> [!NOTE]
> there are still issues for some of these: Badland won't play any sound and Asterix & Obelix XXL Romastered will still crash when starting level 2

## Upgrading game controller support

If you have game controller issues, you can try enabling [compatibility mode](https://www.reddit.com/r/macgaming/comments/1lrt8lh/guide_use_any_controller_on_any_macos_game_macos/) in macOS' game controller settings.

Upgrading SDL2's game controller database:

[Many games use the SDL2 library](https://steamdb.info/tech/SDK/SDL/?os=macos), which allows you to update their controller support. This allows you to use controllers released after a game (like the Sony DualSense)

- [download gamecontrollerdb.txt](https://github.com/mdqinc/SDL_GameControllerDB/blob/master/gamecontrollerdb.txt)
- in Steam, click on the gear icon in the game description and select "Manage" > "Browse local files", it'll open a Finder window where you game is installed
- look for gamecontrollerdb.txt file (it might be located inside the game's application bundle, right click the icon and select "display contents" and navigate to Contents/Resources/) and replace it with the updated version
- if you can't find it, just place the gamecontrollerdb.txt file in the same folder as the application

> [!NOTE]
> Incidentally, many [Mac Source Ports](https://www.macsourceports.com/) use SDL2 but do not have the gamecontrollersdb.txt file, just drop it in the same folder to add controller support!
