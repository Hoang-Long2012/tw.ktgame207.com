---
title: "Version History"
menu:
  main:
    name: "Changelog"
    weight: 5
---

# Changelog

Stay updated with the latest developments, feature additions, and bug fixes in Terra Wilds.

## Version 15.00

- New menu sound theme picker:
  - The menu navigation cues (open, move, edge, enter) can now be switched between three themes: stw (default), stw2 (a subtler variant), and old menu sounds (the legacy cues).
  - The picker lives in the Sound category of the Settings screen and is persisted across sessions.
  - Themes live in their own folders under client/sounds/menu/ and can be extended by dropping new sound files into the corresponding folder.

- Stereo panning for menu cues:
  - Menu sounds can now pan from left to right based on the position of the highlighted item -- the first item plays on the left, the middle item in the center, and the last item on the right.
  - A new toggle "pan menu sounds left to right based on position" was added to the Sound settings to enable or disable this. The toggle is off by default; flip it on if you want positional panning on menu cues.
  - The pan formula was corrected so that the leftmost and rightmost extremes are actually reachable and the exact middle item of an odd-length list lands dead center.

- Optional menu wrap-around:
  - A new toggle "wrap around at the ends of menus" was added to the Sound settings.
  - When off, arrow keys stop at the first / last item of the main menus instead of looping back around. Server-side menus, the bank menu, and the player menu were already non-wrapping and are unaffected.

- Optional left/right-only menu navigation:
  - A new toggle "use left and right arrows to move through menus" was added to the Sound settings.
  - When enabled, regular menus switch to Left and Right arrow navigation instead of Up and Down.
  - This affects menu-style screens only and does not change forms or text-entry controls.

- Map editor wall picker reads from sounds/map/walls/ folder directly:
  - The wall-type menu used by the map editor is no longer driven by a hardcoded list.
  - To add new wall sounds, drop wall*.ogg files into client/sounds/map/walls/. The picker shows them automatically next time you open it.
  - List is sorted alphabetically. Space-to-preview, Home, End, Up, Down and type-to-search behave exactly as before.
  - If the folder is empty (sounds not installed), the menu announces this and exits cleanly instead of opening an empty picker.

- Account settings 2FA: Set Telegram ID now uses a single combined window:
  - The window has the numeric ID input, the bot link, and an Open in Telegram button side by side.
  - Pressing Set submits the ID and the same window then waits for you to press Start in the bot to confirm ownership.
  - Replaces the previous two-step flow (numeric prompt then a separate confirmation window).
  - Also fixed Skip 2FA for the next N logins not opening its input form.

- Account settings: Telegram two-factor authentication submenu:
  - From the in-game account settings menu you can now manage 2FA without typing chat commands.
  - Items: set Telegram ID, open Telegram bot to link the ID, enable or disable 2FA, skip 2FA for the next N logins, and remove the linked Telegram ID.
  - The Telegram ID input is numeric only -- digits are accepted, everything else (including minus signs and letters) is dropped automatically.
  - Existing chat commands (settelegram, tglogin, removetelegram) keep working unchanged for players who prefer them.

- added realtime voice chat
  - deleted old voice chat sistem it dont needed more

- restructuring menu volume:
  - added sliders for game volume music volume and voice chat volume. press f9 key for open slider menu and read help if you dont understanding short help press h for more help.

- Added object tracking navigation:
  - A new nearby tracking system was added for locations, objects, players, items, creatures, and NPCs.
  - Press Minus Word to move to the previous entry in the current category.
  - Press Equals Word to move to the next entry in the current category.
  - Press Shift plus Minus Word to move to the previous category.
  - Press Shift plus Equals Word to move to the next category.
  - Press Backspace to track the currently selected entry after using the nearby tracking navigation.
  - Press Shift plus Backspace to stop the current local tracking target.
  - If tracking is lost because you move to another map, the client will report that tracking was lost.

- Added Numpad Enter support:
  - The Enter key on the numeric keypad now performs the same actions as the main Enter key, such as picking up objects.

- Added numeric form inputs:
  - Some forms now use numeric-only input fields for values that should only contain digits.
  - Decimal form inputs were also added for fields that need values like 0.5 or 0.75.
  - These inputs now block invalid characters more reliably, including pasted text.

- Added microwaves:
  - Microwaves can now be found in the world and used for simple cooking.
  - Press Alt+Space with an empty hand near a microwave to open or close its door.
  - With the door open, use a raw food item on the microwave to place it inside.
  - Press Space with an empty hand while the door is closed to start cooking.
  - If there is nothing inside, the game will tell you that there is nothing to cook.
  - When cooking is finished, open the door with Alt+Space and press Space with an empty hand to take the cooked food out.
  - Already cooked food inside a microwave cannot be cooked again until you remove it.

- Improved private message composition:
  - Replaced the old text prompt with a dedicated form for private messages.
  - You can now type your message in an editor with Send and Cancel buttons.

- Reworked the settings screen into categories:
  - Settings are now grouped into Categories for easier navigation.
  - You can move through categories with the arrow keys and use Tab to jump into the controls of the selected category.

- Improved sound settings:
  - The jumping sound is now shown directly as a list inside the Sound category instead of opening a separate selector.
  - Moving through the jumping sound list now plays a live preview of the currently selected sound.

- Improved player menu navigation:
  - Fixed issues with hotkey conflicts by preventing alphabetical navigation when Ctrl or Alt keys are pressed.
  - Ensured that the Enter key now functions correctly for selecting players in the menu.
  - Resolved an Index out of bounds error that occurred during alphabetical navigation.

## Version 14.04

### bug fix
- fix Out of range in form(next_line_silent).
- Fixed a bug in the player menu where letter-based navigation was not working correctly. Users can now jump to players in the list by typing the first letter of their name, regardless of case.

## Version 14.03

### Security Enhancements
- **Two-Factor Authentication (2FA)**: Implemented 2FA via Telegram to bolster account security.
  - `tglogin`: Toggle 2FA on/off. (Requires Telegram ID linkage via `settelegram`).
  - `tglogin <number>`: Set a specific number of "grace logins" to bypass the code prompt.
  - Verification codes are 6-digits and valid for 10 minutes.

### UI & User Experience
- **Auction Interface**: Completely refactored the item auction UI, replacing fragmented dialogs with a unified, modern form for a streamlined experience.
- **Auction Hotkey**: Added **Shift + B** for rapid bidding.
- **Connection Feedback**: Implemented dynamic sound feedback (variable pitch beeps) during the login sequence.
- **Connection Settings**: Introduced an `enable_connection_beeps` setting in the options menu.

### Gameplay & Stability
- **Auto-Reconnection**: The client now automatically attempts to reconnect if the server restarts, eliminating blocking message dialogs.
- **Auto-Login**: Added an `autologin` feature to bypass the main menu on startup, configurable via the options menu.
- **Technical Fixes**: Resolved "Out of Range" errors during text processing and fixed coordinate display issues across various maps.

---

## Recent Updates

### February 18, 2026
- **Real-time Maintenance Intel**: Players can now monitor the countdown until the next server reboot and garbage collection cycle using the `time` command.

### February 17, 2026
- **Developer Security**: Enhanced protocols to prevent unauthorized modifications or deletions of administrator accounts.
- **Account Safeguards**: Integrated Telegram verification for account deletion requests. Link your account via the [Official Bot](https://t.me/privattwbot).

### January 18, 2026
- **Audio Optimization**: Refined the sound effects for pot crafting to prevent audio overlapping ("double sound" issue).

---

## Version 14.02

- **Game Rebranding**: Officially transitioned to the new project identity.
- **Administrative Control Panel**: Introduced a new backend dashboard for developers with dedicated keyboard shortcuts.
- **Core Refactoring**: Rewrote the server log system and administrative help management for improved efficiency.

---

## Historical Changes (Late 2025)

- **Library Migration**: Removed legacy BGT audio libraries in favor of the modern **NVGT** library, moving the project closer to HRTF support.
- **Update System**: Split client updates and sound assets into separate versions for optimized downloads.
- **Auto-Update Toggle**: Users can now enable/disable automatic update checks on startup.
- **Gameplay Fixes**:
  - Smoothed respawn timers for animals.
  - Added **Bicycles** to the Daily Wheel and Gift Shop.
  - Resolved "safe zone" bugs related to abrupt tent removal.
  - Fixed audio issues for fish slicing.
  - Implemented anti-spam systems for global messaging.
  - Auction system added.
  - Survival Store inventory updated with Paper.
  - Persistence fixes for Coffee Machines during server restarts.
