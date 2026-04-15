Client Demo — Quick Instructions

What this package contains
- A ZIP containing the full static website (HTML, CSS, JS, assets).
- A single folder you can extract on the phone and open `index.html`.

Recommended simple ways for the client to run it on a phone

Option A — Quick, no apps needed (Android is easiest)
1. Unzip `yourbusiness-client.zip` into the phone storage (e.g., Downloads).
2. In your phone file manager, tap the `index.html` file and choose your browser (Chrome, Firefox).
3. The site should load and basic interactivity (forms, cookie banner) will work.

Notes: Some mobile browsers restrict local-file JavaScript (particularly older iOS versions). If parts of the demo don't run, use Option B.

Option B — Run a local HTTP server (recommended, most reliable)
- Android (Termux) or iOS (iSH / a-Shell) users can run a tiny HTTP server and open `http://localhost:8000`.

Commands (run from the folder where `index.html` is):

```bash
# If Python 3 available
python3 -m http.server 8000
# or with Python 2
python -m SimpleHTTPServer 8000
```

Then open: http://localhost:8000

Option C — Upload to temporary hosting (fast if they don't want to install apps)
- Upload the ZIP or extracted files to any static host (GitHub Pages, Netlify Drop, Vercel, or a simple file-sharing link) and open the URL in mobile browser.

Important for you (pre-send checklist)
- Replace placeholder contact info (phone, emails, address) in the files before sending to the client.
- If you need the client to test form submissions, set up an endpoint (the demo shows a simulated success message).

If you want, I can:
- Create a single self-contained HTML file (all CSS/JS inlined) for the absolute easiest distribution.
- Or create the ZIP here and place it on your Desktop for you to send — tell me which you prefer.

