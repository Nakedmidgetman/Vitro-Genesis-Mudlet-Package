# Changelog

All notable changes to the Vitro Genesis Mudlet Package will be documented in this file.

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
