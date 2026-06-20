# iPhone Photo Copier - Instructions

This standalone utility copies photos and videos from your connected iPhone to your Windows PC over USB. It tracks what has already been copied, ensuring only new files are transferred.

## Features
* **Chunk-Based File Streaming**: Transfers media in 64KB blocks to prevent memory spikes or system crashes when copying large 4K videos.
* **Roll-Over Protection**: Checks duplicates using the full relative device path (e.g. `/DCIM/100APPLE/IMG_0001.JPG`), preventing rolled-over photo names (e.g. identical `IMG_0001.JPG` in different DCIM folders) from being skipped.
* **Multi-Device Isolation (UDID Tracking)**: Prefixes every entry in the history log (`copied_files.txt`) with the connected iPhone's unique hardware identifier (UDID/Serial). This isolates backups from multiple phones and prevents files from being skipped.
* **Backup Mode Selection**:
  * **Incremental Backup**: Only copies new files since the last backup (relying on `copied_files.txt`).
  * **Fresh Backup**: Ignores history and copies all media files from scratch (useful when backing up to a new folder).
* **Dual Progress Bars**: Smoothly displays both overall folder progress and current file copying progress (in MBs).
* **Graceful Cancellation**: Cleanly abort transfers mid-way via the "Cancel Copy" button.
* **Expanded File Formats**: Full support for standard formats, Apple ProRAW (`.DNG`), sidecar edit files (`.AAE`), `.GIF`, and `.WEBP`.
* **Active USB Connection Monitoring**: Instantly detects and displays connection status (🔴 Disconnected / 🟢 Connected) in the header. Controls are automatically locked unless an iPhone is connected, preventing empty connection exceptions from occurring.


## Prerequisites
1. **Install iTunes**: Make sure iTunes is installed on your Windows PC (required for Apple USB connection drivers).
2. **Trust Computer**: Unlock your connected iPhone and tap "Trust This Computer" when prompted.

## How to Use
1. Double-click `iPhonePhotoCopier.exe` to run.
2. Click **Browse...** to select the target backup folder on your computer.
3. Choose your backup mode: **Incremental Backup** (default) or **Fresh Backup**.
4. Click **Start Copy** to run.
5. Click **Cancel Copy** at any time to safely halt the transfer.

## Diagnostics & Logs
Detailed logs are saved to your local Windows user directory:
`C:\Users\<YourUsername>\AppData\Local\iPhonePhotoCopier\iphone_copier.log`

---
© 2026 KRY Soft Solutions. All rights reserved.

