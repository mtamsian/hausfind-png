# HausFind PNG v2 — upgrade instructions for Android phone

## What's new
- Search and filter property records
- Add owner/agent property submissions (pending review)
- Owner contact book with phone and WhatsApp links
- Viewing request form and appointment register
- Agency review queue to verify/reject submitted properties
- Appointment statuses: pending, confirmed, completed, cancelled
- CSV exports for property and appointment records
- Responsive mobile layout and updated offline cache

## Update the GitHub Pages website
1. Open the `hausfind-png` repository on GitHub.
2. Open `web/index.html` only if your published site uses the `web` folder. If you originally uploaded the four files from the `web` folder into the repository root, open the root `index.html` instead.
3. Edit the existing `index.html` and replace its entire contents with the contents of the matching `index.html` in this package. On GitHub, use the pencil/Edit button, select all old text, paste the new contents, and tap Commit changes. For large files, use Add file → Upload files and upload the replacement file.
4. Also replace `sw.js` in the same published folder with this package's `web/sw.js` to force the browser to refresh its cached version.
5. Open your published website and refresh it. If it still shows the old version, in Chrome open site settings for the website, clear stored data/cache, then reopen it.

## Important prototype limitations
This is still a browser-local prototype. Property submissions and appointments are saved in the current browser's local storage; they are not shared with other users or devices, and they are not automatically sent to landlords. The owner contact book only contains contacts entered through the app. Facebook search/import, user accounts, secure staff roles, hosted database, notifications, and real booking confirmations require a backend and authorised integrations. Do not use this prototype to store sensitive documents, payment details, or private identity information.

## Existing Android Studio project
The Android source project now includes the updated local app page, but this ZIP does not include a compiled APK or Play Store AAB. Building those requires a compatible Android build environment.
