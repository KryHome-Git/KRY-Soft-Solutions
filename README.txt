# Market-Ready Applications - User Guide

This package contains two optimized, standalone Windows utilities designed to manage your media and backups. Both applications feature modern CustomTkinter user interfaces (with Windows 11 design styling and Dark/Light mode support), automatic background execution to prevent UI freezing, and local diagnostics logging.

Applications are located in their respective folders:
- **DuplicateFileManager/DuplicateFileManager.exe**: Instantly scan folders, detect duplicates using pre-screening and full SHA-256 analysis, isolate duplicates into a separate folder, and delete them permanently.
- **iPhoneiPadPhotoCopier/iPhoneiPadPhotoCopier.exe**: Back up photos and videos from your connected iPhone or iPad to your Windows PC over USB with double progress indicators, multi-device tracking, and streaming memory protection.

---

## 1. Duplicate File Manager

### Features
* **Double-Pass Hashing**: Scans file sizes first, runs a fast-hash (1KB) pre-screen, and only calculates a full SHA-256 hash for identical matches. Extremely fast.
* **Background Threading**: Heavy scans and deletions are run in background threads to keep the UI completely responsive.
* **Safe Isolation**: Identified duplicates are moved to a temporary `_duplicates/` directory first for you to verify, preventing accidental deletions.
* **Log Console**: Details, scanned filenames, and errors are printed directly to an in-app scrollable console.
* **Dark Mode**: Switch themes dynamically in the top-right corner.

### How to Use
1. Double-click `Bin\DuplicateFileManager.exe` to run.
2. Click **Browse Folder...** to select your target folder.
3. Click **Find Duplicates** to scan.
4. Verify files in the `_duplicates` subdirectory inside your folder.
5. Click **Delete Duplicates** to permanently remove them.

---

## 2. iPhone iPad Photo Copier

### Features
* **Chunk-Based File Streaming**: Transfers media in 64KB blocks to prevent memory spikes or system crashes when copying large 4K videos.
* **Roll-Over Protection**: Checks duplicates using the full relative device path (e.g. `/DCIM/100APPLE/IMG_0001.JPG`), preventing rolled-over photo names (e.g. identical `IMG_0001.JPG` in different DCIM folders) from being skipped.
* **Multi-Device Isolation (UDID Tracking)**: Prefixes every entry in the history log (`copied_files.txt`) with the connected iPhone's unique hardware identifier (UDID/Serial). This isolates backups from multiple phones and prevents files from being skipped.
* **Backup Mode Selection**:
  * **Incremental Backup**: Only copies new files since the last backup (relying on `copied_files.txt`).
  * **Fresh Backup**: Ignores history and copies all media files from scratch (useful when backing up to a new folder).
* **Dual Progress Bars**: Smoothly displays both overall folder progress and current file copying progress (in MBs).
* **Graceful Cancellation**: Cleanly abort transfers mid-way via the "Cancel Copy" button.
* **Expanded File Formats**: Full support for standard formats, Apple ProRAW (`.DNG`), sidecar edit files (`.AAE`), `.GIF`, and `.WEBP`.
* **Active USB Connection Monitoring & Device Name Display**: Instantly detects and displays connection status (e.g., `Disconnected` or `Connected - Kumud's iPhone`) in the header. Controls are automatically locked unless a device is connected, preventing empty connection exceptions.
* **Auto iTunes Driver Setup**: Automatically checks for Apple Mobile Device Support (iTunes) on launch. If missing, it requests your consent to download and run the installer directly from Apple in a background thread with a download progress indicator.


### Prerequisites
1. **Apple Mobile Device Support**: Required to connect your device. The app will automatically detect and help install it on launch, or you can install iTunes manually.
2. **Trust Computer**: Unlock your connected iPhone and tap "Trust This Computer" when prompted.

### How to Use
1. Double-click `iPhoneiPadPhotoCopier\iPhoneiPadPhotoCopier.exe` to run.
2. Click **Browse...** to select the target backup folder on your computer.
3. Choose your backup mode: **Incremental Backup** (default) or **Fresh Backup**.
4. Click **Start Copy** to run.
5. Click **Cancel Copy** at any time to safely halt the transfer.

---

## 3. Diagnostics & Logs

If either application runs into permissions issues or connection faults, detailed logs are saved automatically to your local Windows user folder:

* **Duplicate File Manager Log**:
  `C:\Users\<YourUsername>\AppData\Local\DuplicateFileManager\duplicate_finder.log`
* **iPhone Photo Copier Log**:
  `C:\Users\<YourUsername>\AppData\Local\iPhonePhotoCopier\iphone_copier.log`

## 4. Support & Feedback

For support, feedback, or tool requests, feel free to contact us at:
📧 **Email**: [kry.home.entertainment@gmail.com](mailto:kry.home.entertainment@gmail.com)

---
© 2026 KRY Soft Solutions. All rights reserved.


