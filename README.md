# VESPERA V4.2

A separate, local-first VESPERA build. This update restores physical activity tracking as a dedicated section while preserving the V4.1 task and player systems.

## Files
- `index.html` — complete app UI and local logic.
- `manifest.webmanifest` — installable PWA metadata.
- `sw.js` — app-shell cache for offline use (cache version bumped for this update).
- `icon.svg` — local app icon.

## Update the existing V4.1 GitHub Pages repository
1. Open `ukvvls/vespera-v4.1` on GitHub.
2. Choose **Add file → Upload files**.
3. Upload the updated `index.html`, `sw.js`, and `manifest.webmanifest`, replacing the existing files with the same names.
4. Commit the changes to `main`.
5. Open `https://ukvvls.github.io/vespera-v4.1/` and refresh. If the old version remains, close the installed app/browser tab and reopen it so the updated service-worker cache is used.

Do not upload these files to the V3 repository.

## Restored activity section
- Dedicated Fitness page accessible from the home dashboard and bottom navigation.
- Weekly schedule with explicit Sunday-to-Saturday labels in Arabic and English.
- Activity logging with type, duration, date, and optional note.
- Last-seven-days activity summary and daily minutes.
- Activity history with delete controls.
- Existing V4 fitness logs are retained; older log records remain readable.

## Local-only behavior
- No Worker, Cloudflare AI binding, remote AI API, external font, CDN, or external script is used.
- The assistant is a local command/context assistant, not a full generative LLM.
- Tasks, rank, language, accent, activity logs, and settings are stored in this browser's `localStorage`.
- The V3 migration remains read-only: the V3 key is not deleted or overwritten.
- Export a JSON backup before switching browsers or devices.

## Notifications limitation
Browser notifications require HTTPS and permission. While the app is open, V4.1 checks due tasks periodically and can show local notifications. Browsers may suspend background pages, so reminders are not guaranteed after the app/browser is fully closed.

## Privacy
There is no sign-in, telemetry, or network call in the application code. The service worker only caches the local app shell for offline use.
