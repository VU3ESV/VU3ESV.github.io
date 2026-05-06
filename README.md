# LB9KJ — station site

A small static site for the amateur-radio callsign **LB9KJ** (and its sister VU3ESV),
modelled after [vu2cpl.com](https://vu2cpl.com/).

Just two files: `index.html` + `styles.css`. No build step.

## Things to edit before publishing

Open `index.html` and search for `data-edit` — those spans are the placeholders I
couldn't fill from the public QRZ page (login was required):

- `<em data-edit>your name</em>` — operator name
- `<em data-edit>JOxxxx</em>` — Maidenhead grid locator for Haugesund

The ITU/CQ zone numbers (18 / 14) are correct for southern Norway, but double-check
anyway. Everything else (FlexRadio 6600, Kenwood TS-990SP, LOTW-only QSL, project
list) was taken from the public QRZ images and your GitHub repos.

## Local preview

```sh
cd ~/lb9kj-site
python3 -m http.server 8000
# open http://localhost:8000
```

## Publishing on GitHub Pages

The git repo is already initialised in this directory. You have two reasonable options:

### Option A — project page at `vu3esv.github.io/lb9kj`

```sh
cd ~/lb9kj-site
# create the empty repo on github.com/VU3ESV/lb9kj first (no README, no .gitignore)
git remote add origin git@github.com:VU3ESV/lb9kj.git
git push -u origin main
```

Then on the repo's **Settings → Pages**, set *Source = Deploy from a branch*,
*Branch = main*, *Folder = / (root)*. Site will be live at
`https://vu3esv.github.io/lb9kj/` within a minute.

### Option B — custom domain `lb9kj.com` (or similar)

Same as above, then:

1. Add a file `CNAME` containing just your domain (e.g. `lb9kj.com`).
2. In Settings → Pages, set the custom domain.
3. At your DNS provider, add an `A` record (or `CNAME` for `www.`) pointing at
   GitHub Pages — see [docs](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site).
