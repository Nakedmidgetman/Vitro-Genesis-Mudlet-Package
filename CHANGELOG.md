# Changelog

All notable changes to the Vitro Genesis Mudlet Package will be documented in this file.

## [1.6.0] - 2026-05-24

### Added
- Added `GenesisQuestTracker` with 388 quest guide entries from the 2026 Genesis Quest Guide.
- Added `quest` command system:
  - `quest help`
  - `quest domains`
  - `quest <domain>`
  - `quest <domain> list`
  - `quest <domain> <number>`
  - `quest search <text>`
  - `quest show <number>`
  - `quest delete <number>`
  - `quest delete <domain> <number>`
  - `quest deleted`
  - `quest restore <domain> <number>`
  - `quest restore <domain> all`
  - `quest restore all`
  - `quest status`
  - `quest reload`
- Added per-character quest completion tracking.
- Added GMCP character detection for Genesis’s lowercase GMCP structure:
  - `gmcp.char.status.name`
  - `gmcp.char.login.name`
- Added separate per-character quest save files, such as:
  - `GenesisQuestTrackerDeleted_Vitrik.txt`
- Added manual quest tracker character override:
  - `quest char <name>`
  - `quest char auto`
- Added `quest importglobal` to import older shared quest completion data into the current character’s file.
- Added Speedwalk system.
- Added `sp` / `speedwalk` command for movement paths.
- Added `spback` to reverse the last remembered movement path.
- Added `spstop`, `spdelay`, `spstatus`, `sphelp`, `spon`, and `spoff`.
- Added support for mixed speedwalk paths containing movement and raw commands, such as:
  - `sp s, w, 2n, ask menerial task, accept task`
- Added Comms window for capturing Newbie channel messages.
- Added `gcomms` command system with show, hide, clear, redraw, reload, status, gag, and test options.
- Added Health Translator for examine lines, converting health descriptions into `[x/15]`.
- Added full aura/imbue translation table for item aura descriptions.
- Added numbered durability translator for weapon and armor condition lines.
- Added Lost Donk Target trigger to send `cdonk`.
- Added fountain/water highlighting.
- Added imbue alert support.
- Added herb search result trigger support.

### Changed
- Updated Quest Tracker so completed/deleted quests are no longer shared globally across all characters.
- Updated Quest Tracker to use Genesis GMCP character data automatically when available.
- Updated Comms window styling to better match Auto Hunter, Session Tracker, and Inventory Tracker.
- Changed Comms pseudo-title and border to bright green.
- Removed the Comms title-bar style in favor of a tracker-style pseudo-title.
- Updated GenesisTranslators into a self-registering translator script.
- Improved durability translation reliability by catching Genesis durability lines more broadly.
- Updated durability translations to use numbered values such as `[7/7]`, `[6/7]`, `[5/7]`, etc.
- Updated Auto Hunter and Session Tracker behavior through recent cleanup work.
- Updated Mapper Scout to support quiet/verbose behavior.
- Made GenesisMapperScout quiet by default to reduce duplicate GMCP anchor/linking spam.
- Updated `gscout` alias to support:
  - `gscout quiet`
  - `gscout verbose on`
  - `gscout verbose off`
  - `gscout loud`

### Fixed
- Fixed Quest Tracker saving completed quests globally instead of per character.
- Fixed Quest Tracker failing to detect character names because Genesis uses `gmcp.char`, not `gmcp.Char`.
- Fixed repeated Scout echo spam such as duplicate GMCP anchor/link messages.
- Fixed aura line translation for lines like:
  - `It pulses with a faint silvery aura.`
- Fixed durability translation for lines like:
  - `It looks like it is in a fine condition.`
  - `It looks like it is a little touched by battle.`
- Fixed health examine lines not showing numerical health estimates.
- Fixed Comms title color issue by using inline styled text instead of relying only on label stylesheet.
- Fixed Speedwalk so `spback` reverses only movement commands and skips raw commands like `ask menerial task`.
- Fixed Speedwalk parsing so comma-separated commands with spaces are treated as full commands instead of broken tokens.

### Notes
- Quest completion/deletion is saved outside the Lua script in the Mudlet profile folder.
- `quest delete` hides completed quests instead of physically removing them from the script, allowing them to be restored later.
- If GMCP character detection fails, use:
  - `quest char <CharacterName>`
- Use:
  - `quest status`
  to confirm the active character and save file.

## [1.5.0] - 2026-05-24

### Added
- Added Comms window for capturing Newbie line messages.
- Added `gcomms` command with show, hide, clear, reload, redraw, status, gag, and test options.
- Added health translator for examined mobs/players, showing health as `[x/15]`.
- Added aura translation support for imbued item descriptions.
- Added full aura-to-stone translation table.
- Added numbered durability translator for weapons and armor.

### Changed
- Restyled Comms window to better match Auto Hunter, Session Tracker, and Inventory Tracker.
- Updated Comms border and title color to bright green.
- Updated GenesisTranslators to self-register its own temporary triggers.
- Improved durability matching by catching Genesis durability lines more reliably.

### Fixed
- Fixed durability lines like `It looks like it is a little touched by battle.` not translating.
- Fixed aura line `It pulses with a faint silvery aura.` not translating to `[two handed combat/twinstone]`.
- Fixed translator relying too heavily on separate Mudlet triggers.

## [1.4.0] - 2026-05-24

### Added
- Added GenesisLoot auto-loot support.
- Added Inventory HUD with blacklist support.
- Added `ka` kill-all combat helper.
- Added grouped NPC tracking improvements.

### Changed
- Improved AutoHunter HUD sizing.
- Improved Session Tracker HUD sizing.
- Improved Scout and FollowFix behavior.
- Updated startup/layout support for regular Mudlet mapper.

### Fixed
- Fixed grouped NPC lines counting incorrectly in Room Tracker.
- Fixed room-description text being mistaken for mobs in some cases.
- Fixed Scout pulling old ghunt ranges automatically.
