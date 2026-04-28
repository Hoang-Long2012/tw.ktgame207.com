---
title: "Version History"
menu:
  main:
    name: "Changelog"
    weight: 5
---

# Changelog

Stay updated with the latest developments, feature additions, and bug fixes in Terra Wilds.

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
