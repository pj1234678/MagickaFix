New in V1.1 - Controller Fixes, Matchmaking fixes, More Crash fixes.

2. Added Controller support to patch 2 in function "ControllerA" - Credit to Racz

17. Patched "ControllerB" in "SubmenuCharacterSelect" to allow player to back out of character and color selection
    -Allows player to back out of robe and color selection. 

18. Patched "ControllerDown" and "ControllerUp" to have correct 0-based index of name selection menu.
    -Fixes name selection using controller when pressing down or up after unjoining then joining.

19. Patched "ControllerLeft" to prevent level selection until player has joined.
    -Fixes menu confusion if you select a level prior to joining on controller.

20. Optimized Main Function checks to improve load times 10-20%.

21. Add a check to EffectsManager so that duplicates don't get duplicates added to dictionary and cause a crash.
    -Fixes rare crash when window is moved. Credit to  w!z@rD

22. Fix Read function in "waveActions" to not crash if RANDOM is used.
    -During scripted events if random is used in xml the game crashes. credit to w!z@rD

23. Patched "OnEnter"  in class "SubMenuCharacterSelect" SteamAppID check to use the paradox robes.
   -The default robe would be selected when a level is started if the user had the wrong AppID. Credit to Racz

24. Patched "CanStart" check to see if all players are ready before starting the game.
   - Massive fixes applied to the Ready and matchmaking system.
   - To play a hosted game you must have 2 or more players that are both ready and have selected a robe, color, and level.
   - Host can't force start the game when everybody was not ready.

25. Patched "SpawnMagick" to add a null check for bookOfMagick to prevent multiplayer crash on trigger.
   - Fix crash on multiplayer game start because magickbook handle isn't valid.

26. Patched "DrawDepth" in PolygonHead to check if vertexbuffer is not disposed before drawing.
   - Fix crash in several instances when vertexbuffer  is disposed in scene changing.

27. Patched "Discover" in the NAT class to not error if service url is blank
   - Causes an error if another broadcast is observed on the network. Not a hard crash.

[RELEASE] Magicka Fixes v1.1 GitHub Repository

Quality of life/Magicka Multiplayer Fixes.

Dear Paradox Interactive,

I am disappointed that this game has been neglected, leading to frequent crashes and an unacceptable user experience on Steam. A group of friends and I purchased this game, expecting it to be in a playable and functional state. However, I have taken it upon myself to address these issues by using dnspy to patch various bugs and broken components in the game.

Please note that the following patches are designed specifically for the latest Steam version, 1.10.4.2.

Instructions:

1. Extract the contents of the ZIP file to the following folder, replacing the existing files:
   C:\Program Files (x86)\Steam\steamapps\common\Magicka

This effort took me more than 12 hours to accomplish, and it should significantly reduce crashes by over 90%+.

Support the developers and buy this awsome game.

List of Fixes:

1. Patched "UpdateAvailableAvatars" from "AddLockedParadoxRobe" to "AddUnlockedParadoxRobe."
   - Removes the lock icon from the robes.Rare crash if you click a robe while holding down certain buttons.

2. Patched "SubmenuCharacterSelect" to always set "me.setrobeused" to avoid using if statements.
   - Enables robe selection on an invalid Paradox login.
   

3. Patched "Program main" to  not hash check for "steam_api.dll."
   - Allows the use of a newer steam_api.dll to prevent achievement glitches.

4. Patched "Gamesparks.dll" to override the "open()" and "terminate()" functions to prevent web system exceptions.
   - Resolves issues when accessing the Paradox website to download textures due to TLS-related problems.

5. Patched "CheckSteamDLCs" to do nothing.
   - Disables the check for Steam DLCs via a broken TLS connection.

6. Patched "UpdateParadoxItems" to do nothing.
   - Bypasses the download from an invalid link caused by TLS issues.

7. Patched "Remove DownloadData" from "GetTexture."
   - Removes the attempt to download a texture from an invalid link to prevent issues.

8. Patched "Start" in Achievement Manager to "worker."
   - Downloads achievements, but this is unnecessary if you are using Steam.

9. Patched "OpenSteamWallet" to remove the "WebRequest" to a broken link.
   - Fixes errors during the download of the Steam wallet.

10. Patched the "ComputeSleepPeriod" function to address arithmetic issues with the "attempt" variable.
    - Resolves crashes in multiplayer mode.

11. Patched "GetCharacters" to subtract 1 from the count when the list of entities is called from "get()."
    - Fixes rendering crashes.

12. Patched "SharedContentManager.dispose" to double-check the existence of objects before disposing of them.
    - Prevents random crashes.

13. Patched "GameScene.dispose" to double-check the existence of objects before disposing of them.
    - Prevents random crashes.

14. Patched "SimpleFileFromURL" to prevent the download of XML.
    - Fixes random crashes caused by the site being moved.

15. Patched 3 "DrawShadows" functions in "PolygonHead.dll" to ignore disposed objects and check variables are not null.
    - Fixes crashes that occur when quitting the game immediately after being defeated and other random crashes.

16. Patched "IconRenderer.Update"  escape if statement at end of function GameStateManager.Instance.CurrentState.Scene.AddRenderableGUIObject(iDataChannel, renderData);
    - Fixes Spell Wheel not showing up on random levels.



Please be aware that these patches are provided as-is and are specifically intended for the mentioned Steam version.