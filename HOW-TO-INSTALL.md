# Overload — Install on your phone

This is a Progressive Web App (PWA): a real installable app, but delivered as files
instead of through the Play Store. Once installed it has its own icon, opens full-screen
with no browser bar, and works completely offline. All your workout data is stored only
on your phone (localStorage) — nothing is sent anywhere.

## Recommended: host it free on GitHub Pages (~5 minutes, no coding)

1. Go to github.com and create a free account if you don't have one.
2. Click **"+"** → **New repository**. Name it e.g. `overload-app`. Make it **Public**. Create it.
3. On the new repo page, click **"Add file" → "Upload files"**.
4. Drag in all the files from this folder (`index.html`, `manifest.json`,
   `service-worker.js`, and the `icons` folder with its 3 files). Commit the upload.
5. Go to the repo's **Settings → Pages**. Under "Build and deployment", set
   **Source: Deploy from a branch**, branch **main**, folder **/(root)**. Save.
6. Wait ~1 minute, then GitHub will show your live URL, something like
   `https://yourusername.github.io/overload-app/`.
7. On your phone, open that URL in **Chrome**. Tap the **⋮** menu → **"Add to Home screen"**
   (Chrome may also just prompt you automatically with "Install app").
8. Open it from your home screen icon — it now runs like a native app, and works with
   your phone in airplane mode.

## Fallback: no hosting, just open the file

If you'd rather skip GitHub, you can transfer the `liftapp` folder to your phone (e.g. via
Google Drive or email yourself the zip, then extract it with a file manager app) and open
`index.html` in Chrome directly. You can still tap **"Add to Home screen"** for a launcher
icon. Data storage still works. The only downside: without hosting over https, the offline
service worker can't register, so you'll want a live connection the first time you open it
in a given session, and background caching is skipped.

## Using the app

- **Home** — pick Chest / Legs / Back / Upper Body to start logging a session.
- Tap **"+ Add Exercise"** to pick a lift (or type a new one — it's saved for next time).
- Enter the weight and your reps for each of the 3 sets. The app shows you live whether
  that's an Increase / Maintain / Decrease result as you type.
- Tap **Finish Workout** to save the session.
- **Progress** tab — browse any exercise to see your volume-over-time chart, with each
  point colored green (increase), orange (maintain), or red (decrease). Tap a point for
  the full detail of that session. The stat strip up top always shows your suggested
  next weight, calculated automatically from your most recent set of that lift.
- **Exercises** tab — add, remove, or review the lifts in each category, and see the
  weight increment used for suggestions (default ±5 lbs per exercise — you can add new
  exercises with a custom increment by editing the `increment` value directly if you
  want finer control later).
