[RELEASE] Magicka Game Crash Fixes v1.0 GitHub Repository

Quality of life/Magicka Multiplayer Fixes.

Dear Paradox Interactive,

I am disappointed that this game has been neglected, leading to frequent crashes and an unacceptable user experience on Steam. A group of friends and I purchased this game, expecting it to be in a playable and functional state. However, I have taken it upon myself to address these issues by using dnspy to patch various bugs and broken components in the game.

Please note that the following patches are designed specifically for the latest Steam version, 1.10.4.2.

Download the Release Zip.

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


VirusTotal Links
https://www.virustotal.com/gui/file/611b5a44d6ab08e8afd3f51b435a5836cae1ab9c9d97d74fbfbfb57e2f84f787?nocache=1
https://www.virustotal.com/gui/file/10cf911e061adbf81e0170b12c6e9ba5385c9b5a1819324d50fa9a9bc91b9be6?nocache=1
https://www.virustotal.com/gui/file/98d629bc119909d043436f21bc91981415d708878f70471948beee94a793ed6b?nocache=1
https://www.virustotal.com/gui/file/4792c4a572db65661c0d711658dabaee5d7ab4443364386ecbe0af4f257ea1eb?nocache=1
