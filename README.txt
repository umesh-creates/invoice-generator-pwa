INVOICE PWA - FILES
====================
index.html         - the app (edit COMPANY_NAME / CITY / DISCOUNT / item table near the top of the <script>)
manifest.json       - app name, colors, icons (edit "name" and "short_name" if you change the shop name)
sw.js               - service worker; makes the app open even with no internet, after first visit
icons/icon-192.png
icons/icon-512.png
icons/icon-maskable-512.png

WHY IT NEEDS HOSTING (not just double-clicking the file)
----------------------------------------------------------
A PWA's "Install app" option and offline mode only work when the files are served over
http(s):// (a real or local web address), not opened as file:///. Any of the free options
below give you that.

EASIEST FREE HOSTING (pick one)
---------------------------------
1) GitHub Pages
   - Create a GitHub repo, upload these files (keep the "icons" folder as is).
   - Repo Settings -> Pages -> Deploy from branch -> main -> / (root) -> Save.
   - Your app opens at https://<username>.github.io/<repo>/

2) Netlify Drop (no account needed)
   - Go to https://app.netlify.com/drop and drag this whole "pwa" folder onto the page.
   - You get a live https:// link immediately.

3) Cloudflare Pages / Vercel
   - Both have a "drag and drop a folder" deploy option similar to Netlify.

INSTALLING ON A PHONE
------------------------
Android (Chrome): open the link -> either tap the "Install app" button in the toolbar,
or Chrome's menu (⋮) -> "Add to Home screen" / "Install app".

iPhone (Safari): open the link -> Share icon -> "Add to Home Screen".
(iOS does not show the in-page Install button; this Share step is required by iOS.)

Once installed, the app opens full-screen from the home screen icon, like a normal app,
and keeps working without internet after the first open.

UPDATING THE APP LATER
--------------------------
If you edit index.html (e.g. change the price list or company name), also bump the
CACHE name at the top of sw.js (e.g. 'invoice-pwa-v1' -> 'invoice-pwa-v2') and re-upload
everything. That tells phones that already installed the app to fetch the new version.
