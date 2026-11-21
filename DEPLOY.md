# Deploy / Update Your Portfolio

Live site: **https://nkyonline0.github.io/portfolio-nky/**

```
portfolio-nky/
├── index.html                          ← the whole website
├── DEPLOY.md                           ← this guide
└── assets/
    ├── nabin.jpg                       ← your photo
    └── Nabin_Kumar_Yadav_Resume.pdf    ← resume (download button)
```

## Push this update (Git on your PC)

```bash
git clone https://github.com/nkyonline0/portfolio-nky.git
cd portfolio-nky

# optional: keep a backup of the current site
git checkout -b backup-nov-2026 && git push origin backup-nov-2026 && git checkout main

# copy index.html, DEPLOY.md and the assets folder from the zip into this folder (overwrite)

git add -A
git commit -m "Portfolio update: match new resume, static project cards, SEO"
git push origin main
```

## Or without Git (GitHub website)

1. Open https://github.com/nkyonline0/portfolio-nky
2. **Add file → Upload files** → drag in `index.html`, `DEPLOY.md` and the whole `assets` folder.
3. Commit message: `Portfolio update` → **Commit changes**.
4. Wait 1–2 minutes, then open the site and press **Ctrl + F5**.

## Add or edit a project

Projects are plain HTML now, so recruiters and link previews see them even without JavaScript.
Open `index.html`, find `<div class="grid" id="grid">`, copy one `<article class="card" ...>` block and edit it:

- `data-cat="product app"` → which filter tabs it shows under: `product`, `app`, `react`, `ecom`, `health`, `realestate`, `business`
- the `<img src=...>` is an automatic screenshot of the site (`https://s0.wp.com/mshots/v1/<encoded-url>?w=800&h=500`). Use `assets/your-image.jpg` instead if you prefer.
- update the "Live projects" number in the hero stats and the "All projects" subtitle if the count changes.

## Update resume or photo

Upload to `assets/` with the **same file names**: `Nabin_Kumar_Yadav_Resume.pdf`, `nabin.jpg` (portrait 4:5).

## Check GitHub Pages is on

Repo → **Settings → Pages** → Source: **Deploy from a branch**, Branch: **main**, Folder: **/ (root)**.
