# ![isicon](../assets/is/icon.png) Infant Sol
Inspired by Crossak's Sol Battler. No, not the one modified by gbros and his boyfriend.

Best used with [Sol's Black Cock](../bbc/README.md)!

## What's New
![IS Version](https://img.shields.io/badge/IS-v0.8.3-orange) - 03-08-2020

### Fixed
- Missing RAINBOW option in `SP Quest (Fangs)` settings

![IS Version](https://img.shields.io/badge/IS-v0.8.2-orange) - 01-08-2020

### Fixed
- `Raid Event` mode does not properly check if the user has enough tokens amount to start expert/ragnarok difficulty if standard difficulty was set to be skipped

![IS Version](https://img.shields.io/badge/IS-v0.8.1-orange) - 31-07-2020

### Fixed
- Half Elixir not being used on main quest

![IS Version](https://img.shields.io/badge/IS-v0.8.0-orange) - 31-07-2020

### Added
- `Main Quest` mode
- `Raid Quest` settings

### Changed
- Compact text arrangements on some settings (less newlines)

### Fixed
- Unexpected behaviour on waiting ap/bp regeneration where it still gets triggered even when Director got a new task
- Properly show current settings panel context
- Overlooked missing `Phantom` option in preferred element settings

### Removed
- `Skip Ultimate` option in `Quest Preparation` settings in favour of `Raid Quest` settings

## ⚠️ Preface
- **Director** = the script itself
- **Hotkeys**:
  - `CTRL` + `SHIFT` + `S` - Show settings panel
  - `SHIFT` + `D` - Show current settings
  - `SHIFT` + `S` - Start/stop Director with current mode
- Settings are saved
- Before starting Director, the user must set their preferred party, on idle state (no battles ongoing), and has already cleared the mode's battle(s) at least once
  - The user can stop Director anytime but it will start *a run* anyway when it starts to propagate quest points (AP/BP)
  - **FOR EVENTS**: The user must go to the event's top page before starting Director
- Default settings:
```js
({
    ue: {
        difficulty: 'Expert',
        boss: 'seraph'
    },
    main: {
      maxRebattles: 1,
      quests: [ MAIN_QUESTS.ROTTEN, MAIN_QUESTS.SHADOW ]
    },
    daily: {
        maxRebattles: 1,
        elements: [ DAILY_QUESTS.LIGHT ]
    },
    raid: {
      difficulties: RAID_QUESTS.FIRE.concat(RAID_QUESTS.LIGHT)
    },
    advent: {
        maxRebattles: 1,
        difficulty: ADVENT_QUESTS.EXPERT
    },
    raidEvent: {
        maxMaterials: 220,
        skip: [ RAID_EVENT_QUESTS.RAGNAROK ]
    },

    seedThreshold: 300,
    heThreshold: 500,
    element: ELEMENTS.LIGHT,
    medeaIsShit: true,
    shareRaid: {
        all: false,
        friends: false,
        union: true
    },

    enabled: false,
    mode: 'DAILY' // SP Quest
})
```

## Configuring with Settings Panel
Reminder: Hotkey is `CTRL` + `SHIFT` + `S`

<center><img alt="settings" src="../assets/is/Settings.png"></center>

### Auto Modes
Described as `Quest Type` in settings panel.

<center><img alt="questtype" src="../assets/is/Auto%20Mode.png"></center>

- `Main Quest (T4 Souls Req)`: Starts battle in the check list. The max re-battles specified is **per quest** in the list
- `SP Quest (Fangs)`: Starts battle from the first element set in the list. The max re-battles specified is **per element** in the list
- `Raid Quest`: Starts battle from STD-ULT all elements
- `Advent Battle`: Starts battle with specified difficulty (default: expert)
- `Raid Event`: Starts battle from STD and stops at the max materials specified, and then jumps to higher difficulties and consume their tokens
- `Union Event`: Joins a battle that has less than 8 participants, and more than or is equal to 50% HP

### Quest Preparation

<center><img alt="questprep1" src="../assets/is/Quest%20Prep1.png"></center>

- `Preferred element` - For eidolon support picking (Priority: Hundo->Guardian->Fallback to first support)

<center><img alt="questprep2" src="../assets/is/Quest%20Prep2.png"></center>

- `Half Elixir Threshold` - Dictates Director to stop using HE and use regen'd AP once the remaining count reaches the specified threshold
- `Seed Threshold` - Dictates Director to stop using seeds and use regen'd BP once the remaining count reaches the specified threshold
- `Medea is Shit` - If enabled, Director prefers AB on easy contents (being beginner, standard, expert difficulties)
- `Raid Sharing` - Self-explanatory

### Main Quest

<center><img alt="mainquest" src="../assets/is/Main%20Quest.png"></center>

- `Max Re-battles Per Quest` - Self-explanatory
- `Quests to do` - Dictates Director to do the [quests](https://kamihime-project.fandom.com/wiki/Souls#S_Class) that drop the T4 required materials in the following checked realms

### SP Quest (Fangs)
To set the re-battle to infinite, set **re-battles to `0`** and there should be **only `one element` in elements to farm**.

<center><img alt="fangs" src="../assets/is/SP.png"></center>

- `Max Re-battles Per Element` - Self-explanatory
- `Elements to Farm in Order` - Self-explanatory

### Raid Quest (STD-ULT)
Dictates Director to do the following checked quests:

<center><img alt="raidquest" src="../assets/is/Raid%20Quest.png"></center>

### Advent Battle
To set the re-battle to infinite, set **re-battles to `0`**.

<center>
    <img alt="advent1" src="../assets/is/Advent1.png">
    <img alt="advent2" src="../assets/is/Advent2.png">
</center>

- `Difficulty` - Self-explanatory
- `Max Re-battles` - Self-explanatory

### Raid Event

<center><img alt="raidevent" src="../assets/is/Raid%20Event.png"></center>

- `Max Materials (to farm on STD)` - Director will jump to higher difficulty once the materials to farm on STD is reached
- `Difficulties to Farm` - Self-explanatory

### Union Event
This mode has built-in functionality with 2 minutes interval: reloads the game and re-joins the current battle whenever it has detected
that the user is stuck in a certain turn.

This has a caveat that it will reload anyway even if the user is still casting abilities on non-0 turns.
Using this script with BBC will likely solve this case.

<center>
    <img alt="unionevent" src="../assets/is/UE1.png">
    <img alt="unionevent" src="../assets/is/UE2.png">
</center>

- `Difficulty` - Self-explanatory
- `Boss` - Self-explanatory

## Demo

## Installation
- Battle-tested in [Google Chrome](https://www.google.com/chrome/index.html) and [Microsoft Edge (Chromium)](https://www.microsoft.com/en-us/edge)
- Requires [TamperMonkey](https://www.tampermonkey.net/) extension installed
- Download: Right in my asshole

## [Copyright](../README.md#Copyright)
