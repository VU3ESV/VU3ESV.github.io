# vu3esv.github.io

Static site for amateur-radio station **LB9KJ** (Haugesund, Norway) and its sister
callsign **VU3ESV** (Bangalore, India). Modelled after [vu2cpl.com](https://vu2cpl.com/).

Three files, no build step: `index.html`, `styles.css`, `CNAME`.

## Things to edit before publishing

Open `index.html` and search for `data-edit` — placeholders that couldn't be
filled from the public QRZ page (login was required):

- `<em data-edit>your name</em>` — operator name
- `<em data-edit>JOxxxx</em>` — Maidenhead grid locator for Haugesund

The ITU/CQ zone numbers (18 / 14) are correct for southern Norway, but double-check
anyway. Everything else (FlexRadio 6600, Kenwood TS-990SP, LOTW-only QSL, project
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

1. Push `main` to GitHub:
   ```sh
   git push -u origin main
   ```
2. **Settings → Pages** → Source: *Deploy from a branch*, Branch: `main`, Folder: `/ (root)`.
3. Site goes live at `https://vu3esv.github.io` within a minute.

## Custom domain (vu3esv.com)

The repo already contains a `CNAME` file with `vu3esv.com`, and the custom domain
is set in **Settings → Pages**.

DNS at the registrar:

- Apex `vu3esv.com` — four `A` records:
  ```
  185.199.108.153
  185.199.109.153
  185.199.110.153
  185.199.111.153
  ```
- `www.vu3esv.com` — `CNAME` to `vu3esv.github.io.`

Once DNS propagates, enable **Enforce HTTPS** in Settings → Pages. See the
[GitHub docs](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)
for details.
