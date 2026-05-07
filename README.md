# vu3esv.github.io

Static site for amateur-radio station **LB9KJ** (Haugesund, Norway) and its sister
callsign **VU3ESV** (Bangalore, India).

Two files, no build step: `index.html`, `styles.css`.

## Things to edit before publishing

Open `index.html` and search for `data-edit` — placeholders that couldn't be
filled from the public QRZ page (login was required):

- `<em data-edit>your name</em>` — operator name
- `<em data-edit>JOxxxx</em>` — Maidenhead grid locator for Haugesund

The ITU/CQ zone numbers (18 / 14) are correct for southern Norway, but double-check
anyway. Everything else (FlexRadio 6600, Kenwood TS-990S, LOTW-only QSL, project
list) was taken from the public QRZ images and the GitHub repos.

## Local preview

```sh
cd ~/Projects/vu3esv.github.io
python3 -m http.server 8000
# open http://localhost:8000
```

## Publishing

The repo name `vu3esv.github.io` is the GitHub Pages user-site convention, so it
deploys to the apex automatically.

1. Make sure the repo is **public** on GitHub (Pages on private repos requires a paid plan).
2. Push `main` to GitHub:
   ```sh
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages** → Source: *Deploy from a branch*, Branch: `main`, Folder: `/ (root)` → **Save**.
4. Site goes live at `https://vu3esv.github.io` within a minute.
