# Webinar Graphics Builder

A self-contained, browser-based tool for producing Western Alternatives webinar graphics
(Zoom registration banner, featured sections, LinkedIn post, Zoom cover slide, waiting room,
and newsletter) from a single form. Edit the webinar name, date/time, and speakers, preview
every format live, then download all graphics as a ZIP of PNGs.

## Run it locally

It's plain HTML/CSS/JS — no build step, no dependencies to install. But because it loads the
template files in iframes, you must serve it over **http://** (not by double-clicking the file,
which uses `file://` and blocks iframe access).

From this folder, start any static server, e.g.:

```bash
# Python 3
python3 -m http.server 8000
```

Then open <http://localhost:8000/> in your browser.

## Deploy to GitHub Pages

1. Create a new GitHub repository and push the contents of this folder to it.
2. In the repo: **Settings → Pages → Build and deployment**.
3. Set **Source** to "Deploy from a branch", pick your branch (e.g. `main`) and the `/ (root)` folder.
4. Save. After a minute, your app is live at
   `https://<your-username>.github.io/<repo-name>/`.

`index.html` redirects to the app automatically.

## File layout

```
index.html                          → redirects to the Builder
Western Alternatives/
  Webinar Graphics Builder.html      → the app (open this)
  Zoom Registration Banner.html
  Featured Section - Register.html
  Featured Section - Watch Now.html
  LinkedIn Post.html                 (1200×1600)
  Zoom Cover Slide.html              (2048×1152)
  Zoom Waiting Room.html             (1280×400)
  Newsletter.html                    (600×400)
  assets/                            → fonts, logo, portraits, background
```

## Notes

- Third-party libraries (html-to-image, JSZip) load from a CDN at runtime, so the export
  feature needs an internet connection.
- All brand fonts, the logo, portraits, and the background image are bundled under
  `Western Alternatives/assets/`.
