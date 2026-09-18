University Study System — v2 (deployment-ready)
================================================

Offline-first personal university study organizer, packaged as an
installable Progressive Web App (PWA).

Included
--------
- Subjects and chapters, with a full subject detail view
- Manual lecture/material entry with multi-file attachments (PDF,
  Office, images, audio, video, ZIP, text, etc.)
- Files are now actually stored on-device (IndexedDB), not just their
  metadata — open/download them again any time, fully offline
- Chapter status (Not Started / Studying / Completed), editable inline
- Automatic spaced-revision scheduling: completing a chapter schedules
  revision reminders at 1, 3, 7, 16 and 35 days later; manual revisions
  can also be added
- Study timer (15/25/45/60 min) and study-session history
- Semester/subject progress tracking
- Delete/rename for subjects, chapters, lectures and sessions
- Backup & restore: export everything (including attached files) to a
  single JSON file, and restore it on any device/browser
- Editable semester label, "erase all data" option
- Installable PWA: web app manifest with real icons, a service worker
  that caches the app shell so it opens and works with no network
  connection after the first visit, and iOS/Android install support

Files
-----
index.html                 the entire app (HTML/CSS/JS, no build step)
manifest.json               PWA manifest (name, colors, icons)
sw.js                        service worker (offline caching)
icon-192.png                 app icon, 192×192
icon-512.png                 app icon, 512×512
icon-512-maskable.png        maskable app icon (Android adaptive icons)
apple-touch-icon.png         180×180 icon for iOS home-screen

How to deploy
--------------
This is a fully static site — any static host works. Upload all the
files above to the same folder (keep them together, same level) and
open index.html through the host's URL. Examples:

  * Netlify / Vercel / Cloudflare Pages: drag-and-drop this folder
  * GitHub Pages: push these files to a repo and enable Pages
  * Any web server (nginx, Apache, S3 + static hosting, etc.): copy
    the files into the public/web root

Requirements: the site must be served over HTTPS (or http://localhost
for local testing) — browsers only allow service workers and PWA
installation on secure origins.

After deploying, open the URL on a phone or desktop browser and use
the browser's "Install app" / "Add to Home Screen" option (or the
in-app Settings → Install app button) to add it as a standalone app.

Data & privacy
---------------
All data (subjects, chapters, notes, sessions, revisions and the
files you attach) stays only in the browser on each device — nothing
is uploaded anywhere. Because of that, data does not sync between
devices automatically: use Settings → Export backup on one device and
Import backup on another to move your data across.

Browser storage can be cleared by the OS/browser under storage
pressure, so it's worth exporting a backup occasionally, especially
before switching browsers, phones, or clearing site data.
