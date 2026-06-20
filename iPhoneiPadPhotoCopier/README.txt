# iPhone iPad Photo Copier - Instructions

This standalone utility copies photos and videos from your connected iPhone or iPad to your Windows PC over USB. It tracks what has already been copied, ensuring only new files are transferred.

## Features
* **Double Device Support**: Full support for both iPhones and iPads (and iPod Touch).
* **Automated iTunes Setup**: Automatically checks if iTunes (Apple Mobile Device Support drivers) is installed. If missing, it offers to download and launch the official installer directly from Apple's server on your behalf.
* **Auto-Detection**: Dynamically detects when iTunes installation is complete in the background and unlocks the application features without needing a restart.
* **Chunk-Based File Streaming**: Transfers media in 64KB blocks to prevent memory spikes or system crashes when copying large 4K videos.
* **Roll-Over Protection**: Checks duplicates using the full relative device path (e.g. `/DCIM/100APPLE/IMG_0001.JPG`), preventing rolled-over photo names (e.g. identical `IMG_0001.JPG` in different DCIM folders) from being skipped.
* **Multi-Device Isolation (UDID Tracking)**: Prefixes every entry in the history log (`copied_files.txt`) with the connected device's unique hardware identifier (UDID/Serial). This isolates backups from multiple phones or iPads and prevents files from being skipped.
* **Backup Mode Selection**:
  * **Incremental Backup**: Only copies new files since the last backup (relying on `copied_files.txt`).
  * **Fresh Backup**: Ignores history and copies all media files from scratch (useful when backing up to a new folder).
* **Dual Progress Bars**: Smoothly displays both overall folder progress and current file copying progress (in MBs).
* **Graceful Cancellation**: Cleanly abort transfers mid-way via the "Cancel Copy" button.
* **Expanded File Formats**: Full support for standard formats, Apple ProRAW (`.DNG`), sidecar edit files (`.AAE`), `.GIF`, and `.WEBP`.
* **Active USB Connection Monitoring & Device Name Display**: Instantly detects and displays connection status (e.g., `Disconnected` or `Connected - Kumud's iPhone`) in the header. Controls are automatically locked unless an iPhone or iPad is connected, preventing empty connection exceptions from occurring.

## Prerequisites
1. **iTunes Drivers**: The Apple Mobile Device Support drivers are required for Windows to communicate with iOS/iPadOS devices over USB. The app will help you install them if they are missing.
2. **Trust Computer**: Unlock your connected iPhone/iPad and tap **"Trust This Computer"** when prompted on your device screen.

## How to Use
1. Connect your iPhone or iPad via USB.
2. Double-click `iPhoneiPadPhotoCopier.exe` to run.
3. If prompted that iTunes is missing, click **Yes** to automatically download and run the setup, then complete the installer prompts.
4. Click **Browse...** to select the target backup folder on your computer.
5. Choose your backup mode: **Incremental Backup** (default) or **Fresh Backup**.
6. Click **Start Copy** to run.
7. Click **Cancel Copy** at any time to safely halt the transfer.

## Diagnostics & Logs
Detailed logs are saved to your local Windows user directory:
`C:\Users\<YourUsername>\AppData\Local\iPhonePhotoCopier\iphone_copier.log`

## Support & Feedback
For support, bugs, or feature suggestions, reach us at:
📧 **Email**: [kry.home.entertainment@gmail.com](mailto:kry.home.entertainment@gmail.com)

---
© 2026 KRY Soft Solutions. All rights reserved.
