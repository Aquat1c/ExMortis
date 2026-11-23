# ExMortis

A mod for the Steam version of **Nitroplus Blasterz: Heroines Infinite Duel**. It adds rollback netplay, rooms with spectating, its own Ranked mode, replays of online matches, training tools and custom colours. Everything is in the game's own menus, in English and Japanese. There is no launcher.

Version: `[beta-6]`

- **Download:** the newest zip is on the [Releases page](https://github.com/Aquat1c/ExMortis/releases/latest). It holds `dinput8.dll` and the manuals.
- **Manual:** [ExMortis-Manual.pdf](ExMortis-Manual.pdf). Japanese manual (日本語マニュアル): [ExMortis-Manual.ja.pdf](ExMortis-Manual.ja.pdf). The manual covers every menu in detail.

## Contents

1. [What it adds](#what-it-adds)
2. [Requirements](#requirements)
3. [Install, update, uninstall](#install-update-uninstall)
4. [First time online](#first-time-online)
5. [Player Match](#player-match)
6. [Ranked](#ranked)
7. [Training](#training)
8. [Replays](#replays)
9. [Custom colours](#custom-colours)
10. [Controls](#controls)
11. [FAQ](#faq)
12. [Reporting a problem](#reporting-a-problem)
13. [Known issues](#known-issues)
14. [Credits and licences](#credits-and-licences)

## What it adds

- **Rollback netplay** in Player Match: up to 20 frames of rollback for everyone, and an Input Delay setting with Auto.
- **Rooms** for 2 to 6 players with a set score (first to N), rotation, Auto Pass, passwords, quick comments, join links and Steam or Discord invites.
- **Practice rooms:** train with another player online.
- **Spectating:** waiting players watch the room's matches live, can join one that is already running, and see what each player picks on the result screen.
- **Ranked:** a shared lobby for up to 240 players, first-to-2 sets, VP, grades, monthly seasons and its own leaderboards.
- **Replays** of online matches in the Replay Theater, with a position bar, speed, frame steps and Take Control.
- **Training tools:** save states, frame step, slow motion, rewind, hitboxes, a frame meter, reversals, longer dummy recordings and Al Azif Ex Mortis.
- **Custom colours:** the game's five unused colours plus up to 59 of your own for every fighter, made in an editor inside the game and shown to other players.
- **Controls:** keyboard keys can be changed, Start included. Menus have their own keys, and pads get menu buttons and L3 / R3. Choose which pad is Controller 1 or 2, put Start on any button, and bind a whole list in one go with Assign All.
- **Music:** pick the fight's track on the stage select, by soundtrack title, or Random for a new track every game.
- **Window:** resize it freely, maximize it or use Borderless. Alt+Enter swaps Windowed and Borderless.
- **Discord:** status, pictures and invites.
- **Fixes** to the original game: an even 60 frames per second, no screen going dark in a long fight, no stall from streamed music, Training recordings that no longer stop at 30 seconds, and startup logos you can skip.

## Requirements

- The current Steam version of the game, on Windows 10 or 11. On any other version the mod's menus, netplay and controls stay off.
- Everyone you play with needs the same `dinput8.dll`, byte for byte. The version is in the window title: `+ExMortis [beta-6]`.
- Players without the mod cannot play with you. They see your room in the list, but they are asked to leave it.
- The game itself is not included.

## Install, update, uninstall

### Install

1. Download the zip from the [Releases page](https://github.com/Aquat1c/ExMortis/releases/latest) and unpack it.
2. Close the game.
3. In Steam, right-click the game and choose **Manage > Browse local files**.
4. Put `dinput8.dll` next to `Nitroplus Blasterz.exe`.
5. Start the game from Steam as usual.

The window title now shows `+ExMortis [beta-6]`. A `dinput8.dll` from another mod cannot be used with this one. Keep a copy of it before you replace it.

The mod keeps everything in an `exmortis` folder next to the game, including its own copy of your save. The game's own save is never written. To start the copy again from the game's save, close the game and delete `exmortis\SaveData.dat`.

### If the file is blocked

A browser or an antivirus tool may warn about a new mod file. That is a caution about files of this kind, not a finding about this one.

- **Chrome:** Ctrl+J, the three dots on the file, **Download unverified file** (or **Keep**).
- **Edge:** Ctrl+J, **Keep** on the entry, then **Show more > Keep anyway** if a window opens.
- **Firefox:** the downloads arrow, the arrow next to the file, **Allow download**.
- **Windows Security** removed it: add the game's folder under **Virus & threat protection > Manage settings > Exclusions** first, then put the file back.

Check the file before you put it in the game's folder. The manual's section 3 has the full steps.

To check that your `dinput8.dll` is the one from the `[beta-6]` release, compare its SHA-256:

```text
83AAA2EFD0B630641FD86716D4FEEDD428AF479E52E0B1DA469BC3269A483C1B  dinput8.dll
```

In PowerShell: `Get-FileHash dinput8.dll`

### Update

Once per launch the mod checks for a newer release. If one exists, the window title adds `(UPDATE AVAILABLE)`. Nothing is downloaded by itself. Close the game, replace `dinput8.dll` with the new one and keep the `exmortis` folder: it holds your settings, replays, colours and rating.

### Uninstall

Delete `dinput8.dll`. The original game is back, with your save as it was before the mod first ran. The `exmortis` folder and a few small traces stay. The manual's section 3 lists them and how to remove them.

## First time online

The first time you open the **Network** menu, a fight starts by itself. This is the **Performance Test**, about 40 seconds long. It shows how well your PC handles rollback and limits nothing. To skip it, press Start and answer Yes. It needs V-Sync off (**Options > Display**).

## Player Match

Every online fight uses rollback, up to 20 frames, the same for everyone. There is nothing to set up. The bottom line in a fight shows `Delay N / Ping Nms`.

- **Create a room:** **Network > Player Match > Create Room**. A room takes 2 to 6 players. **Room Type** is Match or Practice, and **Password** is optional.
- **Join a room:** **Network > Player Match > Search Room**, a join link, or a Steam or Discord invite. A link, an invite or Join Game skips the password only for the host's Steam friends.
- **Join link:** press Reset on the room's command list (Left Shift, or Share / Back on a pad) and paste the link in a chat.
- **FIRST TO** (top left of the room page) is the set length: `1` to `9`, or `-` for no limit. The host changes it with LB / RB.
- **ROOM OPTIONS:** ROOM TYPE, ROUNDS, TIME, ROTATION and PASSWORD. Only the host changes them, between fights.
- **ROTATION** sets who plays after a set: STANDARD, WINNER STAYS, LOSER STAYS, BOTH OUT, FIXED or RANDOM.
- **AUTO PASS** (under PASS) is your own. While it is On, your turn goes to the next player in the queue, as long as someone waiting wants to play.
- **Your turn passes after 15 seconds** if you have not pressed READY and someone waiting wants to play.
- A player whose game stops responding shows a crossed link icon on the host's room page after 10 seconds, and is removed after 30 seconds.
- **Practice rooms** have no round timer and refill health, power and partner meter after each combo. Start opens a pause window on your PC only. No replay is saved.
- After a match both players choose **Rematch**, **Character Selection** or **Return** within 30 seconds.
- During an online match the window cannot be dragged or resized. Maximize, minimize, close and Alt+Tab still work.

### Spectating

- With **Options > Game > Watch Matches** on (the default), your game follows each match while you wait. With it off, use the **Spectate** row.
- Up to four waiting players can watch. If you enter a room during a match, your watch starts within a few seconds.
- To leave a watch, press Start and answer Yes.
- Watchers never affect the players. The one exception: at the end of a set, the next fight waits up to about 10 seconds for watchers still on their way back.

### Input Delay

**Options > Game > Input Delay**: `0` to `5`, or `Auto` (the default), which picks the delay from your ping. More delay means less rollback on a slow connection. The delay is yours alone.

| Where | Pad | Keyboard |
| --- | --- | --- |
| Room page, INPUT DELAY block | LT / RT | `E` / `Q`, or `-` / `=` |
| Result screen | LT / RT | `-` / `=` |
| During your own online match | (none) | `-` / `=` |

A delay you step with these keys is remembered for that opponent.

## Ranked

Open **Network > RANKED MATCH**. Everyone on the same mod build shares one lobby for up to 240 players. It takes the place of the game's Ranked Match while the mod is installed. Your original Ranked VP stays untouched.

- **PLAYERS:** everyone who is free. Confirm on a player challenges them. They have 20 seconds to accept. Confirm on your own row starts Ranked Training while you wait.
- **MATCHES:** the sets being played. Confirm watches one.
- **HISTORY:** your rated games on this PC, newest first, with opponent, both fighters, result and VP change.
- **SETTINGS:** Input Delay, Nicknames, Allow Spectating, Max Ping, Character and Sort by Rank. The **Leaderboard** row opens the mod's rankings.

A set is first to 2 games, 2 rounds each, with the same fighters. A win in a set gives +1,000 VP, or +2,000 if you also won the game before it. Seasons are calendar months: in a new month your VP is halved. Start does not open the Leave box during a Ranked game. Your rating is kept in `exmortis\giga\`, with one copy in Steam Cloud.

### Leaderboards

After each set your result goes to the mod's own Steam leaderboards. See them in **Network > RANKING** under **ExMortis** (the last entry on the top bar): All Time keeps your highest VP, and each month has its own board. If the set's last game was saved as a replay, press Replay on that row to download it into the Theater's Ranked tab.

## Training

Press Start in Training. The **Practice** and **Display** tabs are new: save states, slow motion, hitboxes, a frame meter and move data. The tools work in Training from the main menu, in a room's Training and in Ranked Training.

- **Al Azif Ex Mortis** is on the Fighters tab in Training from the main menu, for you and for the dummy. She starts with her own two partners, and you can change them like anyone's. Save State is not available while she is in the fight.
- **Reversals:** **Opponent** tab > **Reversal**. Pick a moment, tick moves and set a **Delay** of 0 to 10 frames.
- **Dummy recordings** can be 99 seconds long and come back the next time you start the game.
- The Display tab's switches also work in replays, BATTLE LOG and LEGACY included.

| Key | Action |
| --- | --- |
| F5 | Save State |
| F9 | Load State |
| F6 | Pause on / off |
| F7 | Frame Step |
| F8 (hold) | Rewind through the last 10 seconds |

The keys can be changed in **Keyboard Config > Battle Controls**, where a **Show Hitboxes** row waits for a key of your choice.

## Replays

- **Save every match:** **Options > Game > Save Replays** (off by default).
- **Save one match:** press Start on the **Save Replay** line of the online result screen.
- Watch them in **Network > Replay Theater**, with a position bar, speed control, frame steps and **Take Control** (play one fighter on from any frame).
- The files are in `exmortis\replays`. To add one, drag a `.nbreplay` file onto the game window.
- A replay from another mod build still plays, but it is not checked and can play differently from the real match.

## Custom colours

Every fighter gets the five colours the game never shows as `Color 22` to `Color 26`, and up to 59 of your own from `Color 27`. Pick them on Character Selection after the stock colours. Other players with the mod see them online, in watches and in replays. **Options > Game > Player Colours** hides one player's colours on your screen.

- **Palette Editor:** Training pause menu > General > **Palette Editor**.
- **From other tools:** with the editor open, drop a `.png`, `.act`, `.pal` (Fighter Factory's too), `.gpl` (GIMP), `.bmp`, `.gif` or `.pcx` file on the game window, or paste one with Ctrl+V in the Hex field. One Undo takes it back.
- **To other tools:** **Copy preview** saves the pose as an indexed PNG in `exmortis\palettes\export`, with the bank's 256 colours in a grid in its corner. Tools such as Fighter Factory can edit it, and the editor reads it back.
- Each colour is one `.nbpal` file in `exmortis\palettes`. Share it by sending the file. Add one by dragging it onto the game window.

## Controls

- **Keyboard Config** (Options, or the pause menu in Training and Versus) has two lists: **Battle Controls** and **Menu Controls**. Menus never read the battle keys, so changing your battle layout does not move Confirm or Back.
- Two players can change their keys at the same time, each in their own column.
- **Button Config** gives pads their own menu buttons, which fixes Confirm and Back on PlayStation pads. L3 and R3 can be bound.
- The default keys are in the manual's section 12.

## FAQ

| Question | Answer |
| --- | --- |
| The window title does not show `+ExMortis` | `dinput8.dll` must be next to `Nitroplus Blasterz.exe`, it must be this one and not another mod's, and the game must be the current Steam version. |
| The download is blocked, or `dinput8.dll` disappears | Your browser or antivirus flagged a new file. See [If the file is blocked](#if-the-file-is-blocked). |
| A fight started by itself in the Network menu | The Performance Test. Let it finish, or press Start to skip it. |
| I cannot see my friend's room, a room refuses me, or my friend is not in the Ranked lobby | You do not have the same mod file. Both of you install the same `dinput8.dll`. |
| Can I play with people who do not have the mod? | No. They see your room in the list but are asked to leave it. |
| The delay number is yellow | Your connection needs more than 5 frames. Expect more rollback. |
| My settings, replays or colours are gone after an update | They are in the `exmortis` folder. Keep it when you replace the DLL. |
| My unlocks are missing | The mod uses its own copy of your save, taken the first time it ran. |
| Alt+Enter does nothing | It is refused during online matches, watches, replays, loading and in Fullscreen. |
| How do I stream it with OBS? | Use Game Capture, or Window Capture with Capture Method set to "Windows 10 (1903 and up)". |
| `The games fell out of sync. The match was stopped.` | A desync. Please report it. |
| How do I go back to the original game? | Delete `dinput8.dll`. |

## Reporting a problem

Logging is always on. After a problem, **before** you start the game many more times, copy the files below from the `exmortis` folder.

### What to send

1. `exmortis.log` and `exmortis.log.1` to `exmortis.log.5`.
2. `bootstrap.log`. If it is missing, the newest `exmortis-bootstrap-*.log` in your `%TEMP%` folder.
3. `exmortis.ini`.
4. From `diagnostics\`: the folder of the problem and `exits.log`. If you are not sure, send the whole folder.
5. For a desync: the `state-...-desync-...` files with their `.spans.txt` and `.inputs.txt`. Ask your opponent for theirs too.
6. For a replay problem: the `.nbreplay` file.

Zip them and add the time, what you were doing, whether you were playing or watching, and the window title. A screenshot or a short video helps. These files can hold Steam ids, player names and game memory, so send them privately to the person who looks into it.

## Known issues

- **The game may still freeze occasionally.** If it happens, send us the logs listed under [What to send](#what-to-send).
- **Practice rooms with three or more players** still need more testing. Tell us if Leave, the refill options or the rotation behave oddly there.

## Credits and licences

- **Aquatic**: main developer and maintainer of ExMortis.
- **Armonté and the AH3 mod developers**: their mod was the model for much of this one, and they helped during development.
- **The GekkoNet developers** (Jamie Meyer and contributors): GekkoNet is the rollback netcode library ExMortis is built on.

The full list of included work and the licence texts are in sections 19 and 20 of the manual.

ExMortis is an unofficial, fan-made mod. It is not made, endorsed or supported by EXAMU, Nitroplus, Marvelous or XSEED Games. It contains no part of the game.
