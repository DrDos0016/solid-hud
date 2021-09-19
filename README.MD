# Solid HUD

Solid HUD is a drop-in alternative to ZZT v3.2 which changes the information displayed on the sidebar
better suited to those familiar with ZZT's controls and iconography. It is intended to make ZZT
worlds easier to navigate and show a lot of information in a limited space making it easy to embed
a small portion of the sidebar onto a scene for a live stream, lessening the need to use a considerable
amount of space on including the entire sidebar.

In addition, Solid HUD aims to provide cheats and adjustments to the standard ZZT experience which
make things smoother while not breaking compatibility.

## HUD Changes

Solid HUD presents the standard ZZT sidebar's information in a more limited space by using a two
column layout for basic information.

The left column displays the player's health, gems, torches, and collected keys (with uncollected keys
displayed using an empty silhouette). The right column displays ammo and score with two additional rows
of new information.

## New Information

The upper portion of the HUD displays energizer cycles remaining, revealing a normally hidden counter. The
double exclamation character displays the time remaining on boards with a time limit.

The lower half is entirely new information:

* The bullet shows the maximum number of shots the player is allowed to have on screen for the board.
* The passage shows the number of passages (with stats) on the board.
* The silhouetted arrows are used to indicated boards that connect to the current board.
* The inverted smiley face is used to show the total number of stat elements on the current board.
* The gamma symbol is used to show the current number of flags set.
* The musical notes are used to show the size of the sound buffer.

## Dynamic Icons

A few of the icons on the HUD will change to indicate additional information:

* The smiley icon by the player's health will become a flashing red exclamation point on boards where the "Re-Enter When Zapped"
property is set.
* The torch icon will fade as the torch cycles remaining decreases. The fade looks as follows: "█░▒▓ ".
* The musical notes will change from white to dark gray when sound is disabled with "B".

## Cheats

Several cheats have also been added to make it easier to deal with harsh game design.

Note that all cheats that use '+' and '-' minus to toggle state also set/clear flags with those names. Setting flags can be avoided by simply omitting the '+'.
Clearing flags can be avoided by using '/' instead. This means `?/DARK` is a valid cheat to turn off darkness without activating anti-cheat measures used in
certain worlds. (`?/DEBUG` is an exception as the debug check uses the flag being set or not to determine debug status).

* `?TELEPORT` and `?PASSAGE` - Opens the board selection menu from the editor allow you to change boards during gameplay.
* `?SPEED` - Opens the speed selection prompt during gameplay.
* `?+/-VISIBLE` toggles the display of invisible walls.
* `?+/-NOCLIP` allows the player to walk on any element. WARNING, you still touch the element you're blocked by and can currently escape the board with this enabled.
* `?+/-FREEZE` prevents all stats except the first (the player) from getting a chance to tick.
* `?FLAGS` lists all currently set flags.
* `?AMMO`, `?TORCHES`, and `?GEMS` now give 50, 30, and 50 of each counter.

## Additional Modifications

Other modifications have been made to make some aspects of ZZT easier to work with.

* The built-in ZZT editor will now open worlds locked with the `SECRET` flag as well as renamed save files

## Known Bugs

* The audio buffer length is frequently non-zero when launching ZZT resulting in the buffer being "stuck" at one number until
sound is toggled or a sound is played.
* The new HUD will update the entire display when any of its information changes. This can be flickery on more active boards.
* Something is off with the editor so that you can't just make a change to a title screen and hit escape without saving. Always manually save a world.

## Changelog

**v05 (2021-09-19)**

* `?AMMO`, `?TORCHES`, and `?GEMS` now give 10x their standard amounts
* Object shooting now tracks if the shoot noise has been added to the sound queue recently making for quieter action sequences

**v04**

* Removed sound effects from the player moving. I'm sorry they bug me when I can hear them!
* The most recently restored save file will be duplicated on top of the list of saves.

**v03**

* ZZT automatically starts in Keyboard + Color mode. Use `/c` to show the configuration screen.
* The "About ZZT" window no longer opens automatically.
* Added `?FLAGS` cheat.
* `#put`, `#become`, and `#change` result in HUD updates for more accurate stat counts.
* HUD updates are called in various stat creation/destroying functions.
* `#set` and `#clear` result in HUD updates for more accurate flag counts.

**v02**

* Message windows no longer close when holding shift and a direction (unless joystick mode is enabled).
* Implemented Asie's `?TELEPORT` cheat from [OpenZoo](https://github.com/asiekierka/OpenZoo/blob/master/Patches/Cheats/Cheat-Passage.patch).
* Implemented Asie's `?SPEED` cheat from [OpenZoo](https://github.com/asiekierka/OpenZoo/blob/master/Patches/Cheats/Cheat-Passage.patch).
* Recreated Asie's "Unpause on P" patch from [OpenZoo](https://github.com/asiekierka/OpenZoo/blob/master/Patches/Tweaks/Flexible-unpausing-behaviour.patch).
* ZZT's editor no longer checks if the world is a save or locked.

## Credits

Solid HUD is based off of [The Reconstruction of ZZT](https://github.com/asiekierka/reconstruction-of-zzt) by Asie, without whom
this project would not be possible.
