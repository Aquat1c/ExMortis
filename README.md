# ExMortis

Rollback netplay, rooms with spectators, a Ranked lobby, training tools, online replays and custom colours for the Steam PC version of **Nitroplus Blasterz: Heroines Infinite Duel**.

Version: `[beta-1]`

The game itself is not included. You need the Steam version of the game.

Everything is in the game's own menus, in English and Japanese. There is no launcher and no settings program. The full manual, with pictures, is [ExMortis-Manual.pdf](ExMortis-Manual.pdf).

**Download:** the newest zip is on the [Releases page](https://github.com/Aquat1c/ExMortis/releases/latest). It holds `dinput8.dll` and the manual.

## Contents

1. [What it adds](#what-it-adds)
2. [Requirements](#requirements)
3. [Install, update, uninstall](#install-update-uninstall)
4. [The first time online](#the-first-time-online)
5. [Playing online](#playing-online)
6. [Practice rooms](#practice-rooms)
7. [Spectating](#spectating)
8. [Ranked](#ranked)
9. [Training](#training)
10. [Replays](#replays)
11. [Colours](#colours)
12. [Controls](#controls)
13. [Settings and files](#settings-and-files)
14. [If the file is blocked](#if-the-file-is-blocked)
15. [Troubleshooting and reporting a problem](#troubleshooting-and-reporting-a-problem)
16. [Known issues](#known-issues)
17. [Credits and licences](#credits-and-licences)

## What it adds

| Area | What you get |
| --- | --- |
| Online | Rollback in Player Match, Input Delay 0 to 5 or Auto, Match and Practice rooms, first-to-N sets, rotation, room passwords, join links |
| Spectating | Waiting players watch live, late join, catch-up |
| Ranked | An own lobby with challenges, first-to-2 sets and its own VP |
| Replays | Online matches in the Replay Theater, position bar, speed, frame steps, Take Control |
| Training | Save states, frame step, slow motion, rewind, hitboxes, frame meter, reversals, 99 s recordings |
| Colours | 64 custom colours per fighter, an editor in Training, shown online |
| Controls | Keyboard remapping, separate menu keys, pad menu buttons, L3 / R3 |
| Window | Resizable window, Borderless, Alt+Enter, an even 60 fps |
| Discord | Status, pictures and invites |

It also fixes a few things in the original game:

- An even 60 fps. The original ran near 58.8 fps with uneven frames.
- The screen no longer goes dark in a long fight, watch or replay.
- No short stall every few seconds from streamed music.
- Training recordings no longer stop at 30 seconds or vanish at restart.
- Cancel on Character Selection in Local Versus and Training steps back one pick.
- Local Versus results give each player their own choice.
- Press Confirm to skip the startup logos.

## Requirements

- **The current Steam version of the game.** The mod checks the game's file. On any other version its menus, netplay and controls stay off.
- **Windows 10 or 11.**
- **The same `dinput8.dll` for everyone you play with**, byte for byte. Two files with the same version name but from different builds refuse each other.
- **Players without the mod cannot play with you.** They see your room in the list, but they are asked to leave it.

## Install, update, uninstall

### Install

1. Download the zip from the [Releases page](https://github.com/Aquat1c/ExMortis/releases/latest) and unpack it.
2. Close the game.
3. In Steam, right-click the game and choose **Manage > Browse local files**.
4. Put `dinput8.dll` next to `Nitroplus Blasterz.exe`.
5. Start the game from Steam as usual.

The window title now ends with `+ExMortis [beta-1]`. If it does not, the mod is not running (see [Troubleshooting](#troubleshooting-and-reporting-a-problem)).

If a `dinput8.dll` from another mod is already there, the two cannot be used together. Keep a copy of the other file before you replace it.

On the first launch the mod makes an `exmortis` folder next to the game. It holds your settings, replays, colours, Training recordings, Ranked rating and the mod's own copy of your save. Keyboard keys and pad buttons you set in the original game are taken over.

### Your save

The game's own save is never written.

- On the first launch the mod copies `SaveData\SaveData.dat` to `exmortis\SaveData.dat`. While the mod is in, the game reads and writes only that copy.
- What you unlock with the mod is only in the copy. Steam Cloud does not carry it to another PC.
- What you unlock later without the mod does not flow into the copy. The copy is taken once.
- To start the copy again from the game's save, close the game and delete `exmortis\SaveData.dat`.

### Update

Close the game and replace `dinput8.dll` with the one from the newest zip on the [Releases page](https://github.com/Aquat1c/ExMortis/releases/latest). Keep the `exmortis` folder.

### Uninstall

Delete `dinput8.dll`. The original game is back, with your save as it was before the mod first ran. The `exmortis` folder stays until you delete it. A few small traces stay too (a copy of your Ranked rating in Steam Cloud, the Performance Test's record and Discord's launch entry in your user's registry). The manual's section 3 lists them and how to remove them.

## The first time online

The first time you open the **Network** menu, a fight starts by itself. This is the **Performance Test**. It measures how well your PC handles rollback.

- It is an automatic fight of about 40 seconds (`Performance Test N/100`).
- At the end a box shows `Performance OK` or `Test failed`, three scores (`FPS`, `Online`, `CPU`, each out of 10) and one line of advice.
- **It limits nothing.** Every match allows the same 20 frames of rollback.
- To skip it, press Start and answer Yes.
- It runs once per PC and per mod file, so it runs again after an update.
- It only runs with V-Sync off (**Options > Display**). With V-Sync on it waits until your next Network menu visit with V-Sync off.

## Playing online

Everything online starts in the **Network** menu. Every Player Match fight uses rollback, with up to 20 frames for everyone. There is no switch. The bottom line in a fight shows `Delay N / Ping Nms` (hide it with **Options > Game > Delay / Ping**).

### Input Delay

**Options > Game > Input Delay**: `0` to `5`, or `Auto` (the default).

- **Auto** picks the delay from your ping at the start of each match.
- **A number** is used as it is. If the connection needs more, it is raised when the match starts. If even 5 is not enough, the number shows in yellow and you get more rollback.
- The delay is yours alone. Your opponent has their own.

| Where | Pad | Keyboard |
| --- | --- | --- |
| Room page, INPUT DELAY block | LT / RT | `E` / `Q`, or `-` / `=` |
| Result screen | LT / RT | `-` / `=` |
| During your own online match | (none) | `-` / `=` |

A delay you step with these keys is remembered for that opponent (up to 64 players). Against anyone else the Options value applies.

### Rooms

**Network > Player Match > Create Room.** The rows are Name (up to 20 characters, Japanese input works), Players (2 to 6), Reserved Slots, Number of Rounds (1 to 5), Connection Status, **Room Type** (Match or Practice) and **Password**.

The room page shows the two fighters, the queue, and a header with ROOM, RESERVED, ROUNDS, TIME, QUALITY and TOP VP. A status line shows `ROLLBACK: CHECKING...`, then `ROLLBACK: CONNECTING...`. READY waits until the link is good.

| Row | What it does |
| --- | --- |
| READY | Ready to fight. While the pair fights it is **Spectate**. Alone in the room it is **Training Mode**. |
| PASS | Give up your turn. A waiting guest in a room of three or more gets **Training Mode** here. |
| SET A COMMENT | A quick comment: the game's ten, plus `GG`, `One more?`, `Thanks`, `Brb` |
| ROOM OPTIONS | ROOM TYPE, ROUNDS, TIME and PASSWORD. Only the host changes them, between fights. |
| PLAYER DATA | The selected player's card |
| INVITE TO ROOM | Host only: Steam's invite window |
| KICK / LEAVE | The host kicks, a guest leaves |

- **Join link:** press Reset on the command list (Left Shift, or Share / Back on a pad). Paste the link in a chat. A friend who opens it lands in your room, even with the game closed.
- **ROUNDS** is 1 to 5, **TIME** is 30, 60 or 99. Both count from the next fight.
- If the game is behind other windows, its taskbar button flashes when someone joins, when it is your turn and when your opponent is ready.

### First to N and rotation

**FIRST TO** (top left of the room page) is `1` to `9`, or `-` for no limit. The host changes it with LB / RB.

- **Two players:** you keep playing each other. The sides never swap.
- **Three or more, with FIRST TO N:** the pair plays until one has N wins. The set winner goes to the back of the queue.
- **Three or more, with `-`:** the loser leaves after every game, as in the original game.

After a match both players choose **Rematch**, **Character Selection** or **Return** within 30 seconds. Both on Rematch gives a rematch. Any Character Selection gives Character Selection. Return, or no choice, goes back to the room page. When the set is over the screen says `Win Limit reached: returning to room`.

### Room passwords

- Set one on Create Room's **Password** row, or later in **Room Options > PASSWORD**. It is 1 to 12 letters and digits. Capital and small letters count as the same.
- With a pad: Up and Down pick the letter, Right adds the next one, Left deletes, Confirm keeps it.
- A room with a password says `Yes` in the **Lock** column. Confirm on it asks for the password.
- **Join links, Steam invites, Join Game and Discord invites skip the password.** Send those only to people you want in.
- The password is not kept: your next room starts without one. It keeps random players out. It is not strong protection.

### Room search

**Network > Player Match > Search Room** opens the search conditions:

| Row | Values |
| --- | --- |
| Number of Rounds | `Any`, or 1 to 5 |
| Connection Status | `Anybody`, `3 or More`, `4 or More` |
| Password | `Any`, or `None` |
| Rooms | `This Version` (your build) or `All` (other builds and the original game too) |

The list shows **Lock**, **Delay** (connection bars) and **Type** (`Match` or `Practice`). A grey row is a room you cannot join. Confirm says why. If a friend's room is missing, the two of you do not have the same file: search with **Rooms** on `All` and Confirm on the grey row to see both versions.

## Practice rooms

A Practice room is a Player Match room for training together online. Make one with **Create Room > Room Type > Practice**, or switch in **Room Options > ROOM TYPE**.

- There is no round timer.
- After each combo both fighters get back health, power and partner meter, each while its option is on.
- **Start opens a pause window over the running fight**, on your PC only. Your fighter stands still. The fight does not stop.

| Pause row | Who | What |
| --- | --- | --- |
| Recover Health, Power Meter, Partner Meter | Creator, or 1P | The refill options |
| Show Hitboxes | You | Hitboxes on your screen only |
| Display | You | Frame Meter, Gauge Values, Distance, Blast Time, Move Names |
| Return to Room | Either fighter | End the fight for both, no result |
| Leave | You | Leave the room |

A Practice fight saves no replay, gives no achievements and writes nothing to Player Data. With Recover Health off, a knockout ends the fight like a normal match.

## Spectating

Up to four waiting players can watch a room's matches live.

- **Automatic:** with **Options > Game > Watch Matches** on (the default), your game follows each match while you wait.
- **By hand:** with it off, use the **Spectate** row while the pair is fighting.
- **Joining late:** `Joining the match in progress...` with a progress bar. Cancel keeps you in the room.
- **Falling behind** by more than about 10 seconds jumps ahead: `Catching up with the match...`.
- **Leaving:** press Start and answer Yes.
- You see the players' custom colours.

Watchers never affect the players. The one exception: at the end of a set, the next fight waits up to about 10 seconds for watchers still on their way back.

## Ranked

**Network > RANKED MATCH** opens the ExMortis Ranked lobby. It replaces the game's own Ranked Match while the mod is in. **Network > RANKING** is still the game's own leaderboard.

One lobby holds everyone on your mod build, up to 100 players. Change tab with LB / RB.

| Tab | Shows | Keys |
| --- | --- | --- |
| PLAYERS | Everyone who is free | Confirm: challenge (or Ranked Training on your own row). X: Player Data. Reset: shuffle. Back: leave. |
| MATCHES | Sets being played | Confirm: watch. X: Player Data. |
| SETTINGS | Input Delay, Nicknames, Allow Spectating, Max Ping (Off, 50 to 300 ms), Character, Sort by Rank | Changes save by themselves |

- **Challenge:** Confirm on a free player and choose Yes. They have 20 seconds to accept. Then both games go straight to Character Selection.
- **A set** is first to 2 games, each game 2 rounds to win. Between games both pick **Rematch** or **Back to Ranked Lobby**. A draw counts for nobody.
- **At the end:** **Go to Player Room** (both must pick it, no rating) or **Back to Ranked Lobby**.
- **Ranked Training:** Confirm on your own row. You stay listed as free, and a challenge takes you straight into the set.

### VP and grade

- Your first rating is your best original Ranked VP of any fighter, halved. Your original Ranked VP is never changed.
- Every game both PCs confirmed counts. Player Room games do not.
- **Set bonus:** a win in a set gives +1,000 VP, or +2,000 if you also won the game before it in that set.
- **Same opponent:** the first four wins in a row count in full, then each counts less, down to 10% from the 13th. Only the last 24 hours count.
- **Seasons** are calendar months. In a new month your VP is halved.
- Your rating is kept in `exmortis\giga\`, with one copy in Steam Cloud. Player Data shows your Ranked VP, grade and season record.

## Training

The tools work in **Training** from the main menu, in a room's Training, and in Ranked Training. Not in Versus, Arcade or online fights.

Press Start for the Training menu. It has six tabs. **Practice** and **Display** are new. Change tab with L1 / R1, or `K` / `L`. The General tab also opens the **Palette Editor**.

| Practice row | Values |
| --- | --- |
| Pause | Off, On |
| Frame Step | Advance one frame |
| Speed | 100%, 75%, 50%, 25% |
| Input Delay | 0 to 9, to practise for online play |
| Playback Timing | Off, Wake-up, After Block, After Hit, Air Tech |
| Slot, Save State, Load State | Four state slots |
| Auto Load | Off, After Combo |

A saved state lasts until the next Reset or a change of fighters or most settings. Nothing is written to disk.

| Key | Action |
| --- | --- |
| F5 | Save State |
| F9 | Load State |
| F6 | Pause on / off |
| F7 | Frame Step |
| F8 (hold) | Rewind up to 10 seconds. While paused, a tap goes one frame back. |
| Hold Left or Right + Reset | Both fighters start in that corner |

The keys can be changed in **Keyboard Config > Battle Controls**, where a **Show Hitboxes** row waits for a key of your choice.

**Display tab:** Show Hitboxes (with a Configure list for box kinds, players and fill), Frame Meter, Gauge Values, Distance, Blast Time and Move Names. The Damage panel also gets a **Meter Gain** row. The frame meter shows each frame's state by colour, the startup / active / recovery of the last move, frame advantage and gaps in blockstrings. The manual's section 9 explains every colour and number.

**Reversals:** **Opponent** tab > **Reversal**. Pick a moment (On wakeup, On hit, After block, After vanishing guard), tick moves, and set a **Delay** of 0 to 10 frames. With several ticked, the dummy picks one at random.

**Dummy recordings** can be 99 seconds long, each slot keeps its own length, and they are kept per dummy lineup in `exmortis\training`.

## Replays

Player Match and Ranked games can be saved and watched in the game's Replay Theater.

- **Save every match:** **Options > Game > Save Replays** on (off by default).
- **Save one match:** on the online result screen, press Start on the **Save Replay** line.
- Practice room fights and matches you only watched are never saved.

**Network > Replay Theater** opens on PLAYER MATCH. Your newest 100 replays per tab stay. **Keep** stores up to 100 more per tab for good. To add a replay, drag a `.nbreplay` file onto the game window.

| Theater list | Pad | Keyboard 1 |
| --- | --- | --- |
| Open Details | Cross / A | `U` |
| Previous / next page | D-pad Left / Right | `A` / `D` |
| Keep, or stop keeping | Options / Start | Tab |
| Delete (asks first) | Share / Back | Left Shift |
| Copy the file to the clipboard | Square / X | `J` |
| Sort | L2 / R2 | `E` / `Q` |
| Leave | Circle / B | `I` |

| Watching | Pad | Keyboard 1 |
| --- | --- | --- |
| Play / pause | Cross / A | `U` |
| Step one frame (tap) or scrub at 2x, 4x, 8x (hold) | D-pad Left / Right | `A` / `D` |
| Start of this round / next round | L1 / R1 | `K` / `L` |
| Speed up (1x, 2x, 4x, 8x) | R3 | `H` |
| Speed down | not set | `G` |
| Take Control | L3 | `T` |
| Pause menu | Options / Start | Tab |
| Jump | Mouse on the position bar | |

**Take Control** lets you play one fighter from the frame on screen with your player 1 battle controls, after a one-second countdown. Press it again or F9 to retry from the same frame. Pause menu > **Return to Replay** goes back to watching.

A replay from another mod build still plays, but it is not checked and can play differently from the real match.

## Colours

Every fighter can have up to 64 colours of your own, numbered 22 to 85.

- On Character Selection, step past the stock colours with Left and Right to `Color 22`, `Color 23` and so on.
- A custom colour is offered only if the stock colour it was made from is unlocked.
- Custom colours change the fighter only. Partners keep their own.
- Online, each PC shows both players' colours. Only the colours are sent, no file is written on the other PC. A colour you make in a room shows up two Character Selection visits later.
- To hide one player's colours on your screen, use **Options > Game > Player Colours**.

**The palette editor:** Training pause menu > General > **Palette Editor**. Pick a ramp, then a shade, and change it with HSV or RGB sliders, a colour wheel or a Hex field. A mouse works too. The **Animation** row picks any move by name for the preview. **Save > Save as new** gives the colour the lowest free number.

Each colour is one `.nbpal` file in `exmortis\palettes`. Share it by copying it (Start on the Palettes page) or sending the file. Add one by dragging it onto the game window, or by putting it in the folder and pressing **Rescan**.

## Controls

**Keyboard Config** (Options, or the pause menu in Training and Versus) has two lists: **Battle Controls** and **Menu Controls**. Menus never read the battle keys, so changing your battle layout does not move Confirm or Back. Press Confirm on a row, then the new key within 5 seconds. **Start** saves, **Back** undoes this visit. It is not available during an online match.

| | Keyboard 1 | Keyboard 2 | Pad |
| --- | --- | --- | --- |
| Move | W A S D | Arrow keys | D-pad and left stick |
| Battle A B C D E | J O I L U | Num 4 9 8 6 7 | Button Config |
| Battle AD, BD, ABC | K, E, Q | Num 5, Num 2, Num 1 | Button Config |
| Battle Back, Start | Left Shift, Tab | Right Shift, Enter | Share / Back, Options / Start |
| Menu Confirm, Back | U, I | Num 7, Num 8 | Cross / A, Circle / B |
| Menu Previous Tab, Next Tab | K, L | Num 5, Num 6 | L1, R1 |
| Menu Player Data 1P, 2P | J, O | Num 4, Num 9 | Square / X, Triangle / Y |
| Menu Reset | Left Shift | Right Shift | Share / Back |
| Menu Prev. / Next Category | E, Q | Num 2, Num 1 | L2, R2 |
| Replay: Take Control, Speed Up, Speed Down | T, H, G | Num 0, Num 3, Num . | L3, R3, not set |

**Button Config** (pads) also has two lists. Battle Controls can now bind **L3 and R3**. Menu Controls sets the menu buttons, which fixes Confirm and Back on PlayStation pads.

With the keyboard as player 1, press Confirm on a pad in the Network menu or a room to make it player 1's pad.

## Settings and files

**Options > Game** gets seven new rows:

| Row | Default | What it does |
| --- | --- | --- |
| Input Delay | Auto | Your input delay online |
| Player Colours | On for everyone | Show or hide each player's custom colours |
| Save Replays | Off | Save every online match |
| Watch Matches | On | Follow the room's matches while you wait |
| Nicknames | On | Player names in the fight. Off also keeps names out of Discord. |
| Delay / Ping | On | The delay and ping line in online fights |
| Discord Status | On | Off: the mod does not talk to Discord at all |

**Options > Display > Borderless** fills the screen with no window frame (with Display mode on Windowed). You can also drag the window's edges, maximize it, and press **Alt+Enter** to swap Windowed and Borderless for this run. Its place and size are remembered.

**Discord:** your status shows the mode, fighters and set score. In a Player Match room Discord offers **Invite to Play** and **Ask to Join**.

The `exmortis` folder:

| File or folder | What it holds |
| --- | --- |
| `exmortis.ini` | All settings. The menus write it. You never need to edit it. |
| `SaveData.dat` | The mod's copy of your save |
| `replays\` | Replays, with a `keep\` folder for kept ones |
| `palettes\` | Your colours. Deleted ones go to `palettes\deleted\`. |
| `training\` | Dummy recordings |
| `giga\` | Your Ranked rating |
| `exmortis.log`, `bootstrap.log` | Logs of this launch and the five before it |
| `diagnostics\` | One folder per problem, and `exits.log` |

`exmortis.ini` holds the Steam ids of players you have met. Keep that in mind before you share it.

## If the file is blocked

A browser or an antivirus tool may warn about a new mod file. That is a caution about files of this kind, not a finding about this one.

- **Chrome:** Ctrl+J, the three dots on the file, **Download unverified file** (or **Keep**).
- **Edge:** Ctrl+J, **Keep** on the entry, then **Show more > Keep anyway** if a window opens.
- **Firefox:** the downloads arrow, the arrow next to the file, **Allow download**.
- **Windows Security** removed it: add the game's folder under **Virus & threat protection > Manage settings > Exclusions** first, then put the file back.

Downloading a file does not run it. `dinput8.dll` runs only when the game starts with it in the game's folder, so check it before you install it. The manual's section 3 has the full steps.

To check that your `dinput8.dll` is the one from the `[beta-1]` release, compare its SHA-256:

```text
A18D443E6BAC8CD84184120F7C2BB9A3F965DF79E5209E010539FF6CBF7E3998  dinput8.dll
```

In PowerShell: `Get-FileHash dinput8.dll`

## Troubleshooting and reporting a problem

| Problem | Answer |
| --- | --- |
| The window title does not show `+ExMortis` | `dinput8.dll` must be next to `Nitroplus Blasterz.exe`, it must be this one and not another mod's, and the game must be the current Steam version. |
| A fight started by itself in the Network menu | The Performance Test. Let it finish, or press Start to skip it. |
| I cannot see my friend's room, a room refuses me, or my friend is not in the Ranked lobby | You do not have the same mod file. Both of you install the same `dinput8.dll`. |
| The delay number is yellow | Your connection needs more than 5 frames. Expect more rollback. |
| My settings, replays or colours are gone after an update | They are in the `exmortis` folder. Keep it when you replace the DLL. |
| My unlocks are missing | The mod uses its own copy of your save (see [Your save](#your-save)). |
| Alt+Enter does nothing | It is refused during online matches, watches, replays, loading and in Fullscreen. |
| `The games fell out of sync. The match was stopped.` | A desync. Please report it. |

### What to send

Logging is always on. After a problem, **before** you start the game many more times, copy these from the `exmortis` folder:

1. `exmortis.log` and `exmortis.log.1` to `exmortis.log.5`.
2. `bootstrap.log`. If it is missing, the newest `exmortis-bootstrap-*.log` in your `%TEMP%` folder.
3. `exmortis.ini`.
4. From `diagnostics\`: the folder of the problem and `exits.log`. If you are not sure, send the whole folder.
5. For a desync: the `state-...-desync-...` files with their `.spans.txt` and `.inputs.txt`. Ask your opponent for theirs too.
6. For a replay problem: the `.nbreplay` file.

Zip them and add the time, what you were doing, whether you were playing or watching, and the window title. A screenshot or a short video helps. These files can hold Steam ids, player names and game memory, so send them privately to the person who looks into it.

## Known issues

- **Practice rooms with three or more players** changed late in this build and had little testing. Tell us if Leave, the refill options or the rotation behave oddly there.

## Credits and licences

- **Aquatic**: main developer and maintainer of ExMortis.
- **Armonté and the AH3 mod developers**: their mod was the model for much of this one, and they helped during development.
- **The GekkoNet developers** (Jamie Meyer and contributors): GekkoNet is the rollback netcode library ExMortis is built on.

The full list of included work and the licence texts are in sections 19 and 20 of the manual.

ExMortis is an unofficial, fan-made mod. It is not made, endorsed or supported by EXAMU, Nitroplus, Marvelous or XSEED Games. It contains no part of the game.
