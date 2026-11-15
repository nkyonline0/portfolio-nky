# Deploy Your Portfolio on GitHub Pages

Your portfolio is a static site (HTML + CSS + JS). GitHub Pages hosts it for free at:

**https://nkyonline0.github.io/portfolio-nky/**

---

## What's in the folder

```
portfolio/
├── index.html                          ← the whole website
├── DEPLOY.md                           ← this guide
└── assets/
    ├── nabin.jpg                       ← your photo
    └── Nabin_Kumar_Yadav_Resume.pdf    ← resume (download button)
```

---

## Option A — Replace your existing portfolio (recommended)

You already have the repo `nkyonline0/portfolio-nky` live. This replaces the old site with the new one.

### Using the GitHub website (no Git needed)

1. Go to **https://github.com/nkyonline0/portfolio-nky**
2. **Back up the old site first:** click the branch dropdown (`main`) → type `old-portfolio` → **Create branch: old-portfolio from main**. Then switch back to `main`.
3. Delete the old `index.html`: open it → **⋯** (top right) → **Delete file** → **Commit changes**.
4. Click **Add file → Upload files**.
5. Drag in `index.html` **and** the whole `assets` folder (drag the folder itself so the path stays `assets/...`).
6. Write a message like `New modern portfolio` → **Commit changes**.
7. Wait 1–2 minutes, then open **https://nkyonline0.github.io/portfolio-nky/** and press **Ctrl + F5** to hard-refresh.

### Using Git on your PC (Windows)

Open **Command Prompt** or **Git Bash**:

```bash
git clone https://github.com/nkyonline0/portfolio-nky.git
cd portfolio-nky

# back up the old version on a separate branch
git checkout -b old-portfolio
git push origin old-portfolio
git checkout main

# copy the new files in (overwrite index.html, add the assets folder)
#   -> copy index.html and the assets folder from the zip into this folder

git add .
git commit -m "New modern portfolio"
git push origin main
```

---

## Option B — Create a brand-new repo

1. Go to **https://github.com/new**
2. Repository name: `portfolio-nky` (or `nkyonline0.github.io` to get the short URL **https://nkyonline0.github.io/**)
3. Set it to **Public** → **Create repository**
4. Click **uploading an existing file** → drag `index.html` and the `assets` folder → **Commit changes**
5. Go to **Settings → Pages**
6. Under **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: **main** / folder: **/ (root)** → **Save**
7. After 1–2 minutes the green box at the top of the Pages settings shows your live URL.

---

## Check that GitHub Pages is on

Repo → **Settings → Pages**. You should see:

> ✅ Your site is live at https://nkyonline0.github.io/portfolio-nky/

If it's not there, set **Source = Deploy from a branch**, **Branch = main**, **Folder = / (root)** and save.

---

## How to update the site later

### Add or edit a project

Open `index.html`, search for `const P = [` and add a line:

```js
{t:"Project Name", cat:["product","app"], label:"Category", url:"https://site.com", play:"https://play.google.com/store/apps/details?id=your.package", d:"One-line description.", s:["Laravel","React"]},
```

- `cat` decides which filter tab it shows under: `product`, `app`, `react`, `ecom`, `health`, `realestate`
- `url` = live website. The card picture is a **live screenshot of that site**, generated automatically.
- `play` = Google Play link (optional)
- `img:"assets/myimage.jpg"` = use your own picture instead of the automatic screenshot (optional — upload the image to `assets/` too)

### Update your resume

Upload the new PDF to `assets/` with **the same file name**: `Nabin_Kumar_Yadav_Resume.pdf`.

### Change your photo

Upload a new photo to `assets/` named `nabin.jpg` (portrait 4:5 works best).

Every commit to `main` re-publishes the site automatically in 1–2 minutes.

---

## Optional — use your own domain (e.g. nabin.hickter.com)

1. In cPanel → **Zone Editor** for `hickter.com` → add a **CNAME** record:
   - Name: `nabin`
   - Points to: `nkyonline0.github.io`
2. In GitHub → repo **Settings → Pages → Custom domain** → enter `nabin.hickter.com` → **Save**
3. When the DNS check passes (can take up to a few hours), tick **Enforce HTTPS**.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Old site still showing | Hard refresh with **Ctrl + F5**, or open in an Incognito window. Pages can take up to 10 minutes. |
| Photo or resume not loading (404) | The files must be at `assets/nabin.jpg` and `assets/Nabin_Kumar_Yadav_Resume.pdf`. File names are **case-sensitive**. |
| Project picture shows letters instead of a screenshot | The screenshot service is still generating it — refresh after a minute. If the site blocks screenshots, add your own `img:"assets/..."` for that project. |
| 404 on the whole site | Check **Settings → Pages** is set to branch `main`, folder `/ (root)`, and that `index.html` is in the root of the repo (not inside a sub-folder). |
| Want the old site back | Switch to the `old-portfolio` branch you created, or set Pages to deploy from that branch. |

---

## After it's live

- Put the link at the top of your resume and LinkedIn: **https://nkyonline0.github.io/portfolio-nky/**
- LinkedIn → **Edit intro → Website** → add the link
- Naukri → **Profile → Online profile** → add the link
