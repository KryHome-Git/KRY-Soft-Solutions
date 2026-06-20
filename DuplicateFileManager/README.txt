# Duplicate File Manager - Instructions

This standalone utility helps you scan folders, detect duplicate files using two-pass hashing, isolate duplicates into a separate folder, and delete them permanently.

## Features
* **Double-Pass Hashing**: Scans file sizes first, runs a fast-hash (1KB) pre-screen, and only calculates a full SHA-256 hash for identical matches. Extremely fast.
* **Background Threading**: Heavy scans and deletions run in background threads to keep the UI completely responsive.
* **Safe Isolation**: Identified duplicates are moved to a temporary `_duplicates/` directory first for you to verify, preventing accidental deletions.
* **Log Console**: Details, scanned filenames, and errors are printed directly to an in-app scrollable console.
* **Dark Mode**: Switch themes dynamically in the top-right corner.

## How to Use
1. Double-click `DuplicateFileManager.exe` to run.
2. Click **Browse Folder...** to select your target folder.
3. Click **Find Duplicates** to start the scan.
4. Verify files in the `_duplicates` subdirectory inside your folder.
5. Click **Delete Duplicates** to permanently remove them.

## Diagnostics & Logs
Detailed logs are saved to your local Windows user directory:
`C:\Users\<YourUsername>\AppData\Local\DuplicateFileManager\duplicate_finder.log`

---
© 2026 KRY Soft Solutions. All rights reserved.

