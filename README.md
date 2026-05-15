Gym Progression Tracker — PWA
===============================

FILES IN THIS FOLDER
─────────────────────
  index.html      Main app (open this in a browser)
  manifest.json   PWA metadata (name, icons, display mode)
  sw.js           Service worker (offline caching)
  icon-192.png    App icon (home screen, small)
  icon-512.png    App icon (home screen, large / splash screen)

RUNNING LOCALLY
───────────────
Just open index.html in Chrome. All features work, data saves to
localStorage. NOTE: The service worker only activates over HTTPS or
localhost — for local testing open via a local server:

  # Python (run in this folder):
  python3 -m http.server 8080
  # Then open: http://localhost:8080

DEPLOYING FREE WITH GITHUB PAGES (recommended)
────────────────────────────────────────────────
1. Create a free account at github.com
2. Click "New repository" — name it anything (e.g. "gym-tracker")
3. Upload all 5 files in this folder to the repo
4. Go to Settings → Pages → Source: "Deploy from branch" → main → / (root)
5. Save. Your app will be live at:
     https://YOUR-USERNAME.github.io/gym-tracker/
6. Bookmark that URL on your phone.

INSTALLING ON YOUR PHONE
─────────────────────────
Android (Chrome):
  • Visit your GitHub Pages URL in Chrome
  • Chrome will show a banner "Add to Home Screen" — tap Install
  • OR tap the 3-dot menu → "Add to Home Screen"

iPhone (Safari ONLY — must use Safari, not Chrome):
  • Visit your GitHub Pages URL in Safari
  • Tap the Share button (box with arrow pointing up)
  • Scroll down and tap "Add to Home Screen"
  • Tap Add

The app will appear as a full-screen icon on your home screen with
no browser address bar, just like a native app. It works offline too.

UPDATING THE APP
─────────────────
Edit index.html with any changes. Upload the new version to GitHub
(same repo, same filename). The service worker will update automatically
within 24 hours, or immediately if the user closes and reopens the app.

When you update the app significantly, bump the cache version in sw.js:
  const CACHE = 'gym-tracker-v2';   ← increment this number
This forces all users to get the fresh version immediately.

DATA & PRIVACY
───────────────
All data is stored locally on the device using localStorage.
Nothing is sent to any server. Your workout data never leaves your device.
